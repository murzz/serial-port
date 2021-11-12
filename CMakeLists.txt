cmake_minimum_required( VERSION 3.15 )

project( "simple-boost-serial-port"
    VERSION 1.11
    DESCRIPTION "A set of C++ classes to easily handle serial ports across different platforms, built on top of boost.asio"
)

find_package( Boost 1.40.0 REQUIRED )

set( CMAKE_CXX_STANDARD 11 )

add_library( ${PROJECT_NAME}
	src/TimeoutSerial.cpp
	src/SerialStream.cpp
	src/BufferedAsyncSerial.cpp
	src/AsyncSerial.cpp
	src/SimpleSerial.cpp
)

target_include_directories( ${PROJECT_NAME}
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

target_link_libraries( ${PROJECT_NAME}
    ${Boost_LIBRARIES}
    pthread
)
