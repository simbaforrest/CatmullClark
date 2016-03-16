cmake_minimum_required(VERSION 2.8 FATAL_ERROR)
set(PROJECT_OUTPUT_FOLDER "C:/project/test/CatmullClark/bin")
set(CMAKE_INSTALL_PREFIX ${PROJECT_OUTPUT_FOLDER} CACHE PATH ${PROJECT_OUTPUT_FOLDER})
set(CMAKE_CONFIGURATION_TYPES "Release;Debug" CACHE STRING "Release;Debug")

project(CatmullClark)

find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
include_directories(${GLUT_INCLUDE_DIR})

add_executable(catmullclark catmullclark.c)
target_link_libraries(catmullclark ${OPENGL_LIBRARIES} ${GLUT_LIBRARY})
install(TARGETS catmullclark DESTINATION ".")

set_target_properties(catmullclark PROPERTIES RUNTIME_OUTPUT_DIRECTORY_RELEASE ${PROJECT_OUTPUT_FOLDER})
set_target_properties(catmullclark PROPERTIES RUNTIME_OUTPUT_DIRECTORY_DEBUG ${PROJECT_OUTPUT_FOLDER})
set_target_properties(catmullclark PROPERTIES DEBUG_POSTFIX "_d")

message(STATUS "added project: catmullclark")