cmake_minimum_required( VERSION 3.15 )

project( "simple-boost-serial-port"
    VERSION 1.11
    DESCRIPTION "A set of C++ classes to easily handle serial ports across different platforms, built on top of boost.asio"
)

find_package( Boost 1.40.0 REQUIRED )

set( CMAKE_CXX_STANDARD 11 )

add_library( ${PROJECT_NAME} STATIC)

target_sources( ${PROJECT_NAME}
    PRIVATE
        src/AsyncSerial.cpp
        src/BufferedAsyncSerial.cpp
        src/SerialStream.cpp
        src/TimeoutSerial.cpp
)

target_include_directories( ${PROJECT_NAME}
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

target_link_libraries( ${PROJECT_NAME}
    PRIVATE
        Boost::boost
        pthread
)
