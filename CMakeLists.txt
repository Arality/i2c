# Cmake version
cmake_minimum_required(VERSION 3.0.0)

# Set c++ standard
set(CMAKE_CXX_STANDARD 20)

# Project name/version
project(Template VERSION 0.1.0)

include(CTest)
enable_testing()

# Including optional directories
include_directories(include)

# Adding SYSTEM keyword to supress librarys warnings
include_directories(SYSTEM lib/boost_1_74_0)

# Scan for files in src/ and include/
file(GLOB SOURCES
    src/*.cpp)

# Debugger options
add_compile_options(-Weverything)


add_executable(Template ${SOURCES})

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
