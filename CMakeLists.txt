cmake_minimum_required (VERSION 3.6)
project(implot)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

add_library(implot implot.cpp implot_items.cpp)

target_include_directories(implot PRIVATE $<TARGET_PROPERTY:CONAN_PKG::imgui,INTERFACE_INCLUDE_DIRECTORIES>)
target_link_libraries(implot CONAN_PKG::imgui)
