cmake_minimum_required(VERSION 3.22)

project(
    CppProjectTemplate
    VERSION 1.0.0
    LANGUAGES C CXX)

# overwrite
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# create variable and use in all cmakelists files
set(LIBRARY_NAME Library)
set(EXECUTABLE_NAME Executable)

# turn smth ON or OFF
option(COMPILE_EXECUTABLE "Whether to compile the executable" OFF)

add_subdirectory(src)  # first - libraries defined here
if (COMPILE_EXECUTABLE)
    add_subdirectory(app)  # second - libraries used here
else()
    # message to console
    message("W/o exe. compiling")
endif()

