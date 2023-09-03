cmake_minimum_required(VERSION 3.16)

project(CppProjectTemplate VERSION 1.0.0 LANGUAGES C CXX)

# to create a new target that is not an executable --> use add_library()
add_library(Library STATIC my_lib.cc)

add_executable(Executable main.cc)

# linking Library to the Executable
# 'hey, I have this Executable and it will use
# this Library! You need to make sure that this Library
# gets linked with this Executable!'
target_link_libraries(Executable PUBLIC Library)
