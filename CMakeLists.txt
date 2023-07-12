cmake_minimum_required(VERSION 3.10)
project(imgui)
set(LIBRARY_NAME imgui)
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
add_library(${LIBRARY_NAME} SHARED ${core_headers} ${core_sources})
set_property(TARGET ${LIBRARY_NAME} PROPERTY POSITION_INDEPENDENT_CODE ON)

set_target_properties(${LIBRARY_NAME} PROPERTIES  LINKER_LANGUAGE CXX)

target_link_libraries(
    ${LIBRARY_NAME}
)
