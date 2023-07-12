cmake_minimum_required(VERSION 3.10)
project(example_null)
set(EXECUTABLE_NAME example_null)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

file(
    GLOB
    core_headers
    *.h*
)

file(
    GLOB
    core_sources
    *.c*
)

set(NO_LIBDEXFILE_SUPPORT)
include_directories(
    ${CMAKE_SOURCE_DIR}
    ${CMAKE_CURRENT_BINARY_DIR}
    ${CMAKE_SOURCE_DIR}/..
    ${CMAKE_SOURCE_DIR}/../..
    ${CMAKE_SOURCE_DIR}/libs/glfw/include

)

link_directories( 
    ${CMAKE_SOURCE_DIR}/
    ${CMAKE_SOURCE_DIR}/..
    ${CMAKE_SOURCE_DIR}/../..
    ${CMAKE_SOURCE_DIR}/../../build
    )

set_property(TARGET ${LIBRARY_NAME} PROPERTY POSITION_INDEPENDENT_CODE ON)

add_executable(${EXECUTABLE_NAME} ${core_headers} ${core_sources} )


target_link_libraries(
    ${EXECUTABLE_NAME}
    ${CMAKE_THREAD_LIBS_INIT}
    imgui
)

