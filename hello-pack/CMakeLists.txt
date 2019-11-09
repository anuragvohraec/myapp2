cmake_minimum_required(VERSION 3.4.1)
project("hello-pack" C)

add_library("${PROJECT_NAME}" SHARED hello.c)
target_include_directories("${PROJECT_NAME}" PRIVATE "./include")