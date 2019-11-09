cmake_minimum_required(VERSION 3.4.1)

project("hello-world-pack" C)

#add subdirectory, so they will be build before this
add_subdirectory("hello-pack")

#we want this to be exposed as a shared lib, so we decalre this as shared and its name will be helloworld
add_library("${PROJECT_NAME}" SHARED "hello-world.c")

#now to build this lib we will need to include the headers and libs files
#include headers
target_include_directories("${PROJECT_NAME}" PRIVATE "include")
target_include_directories("${PROJECT_NAME}" PRIVATE "hello-pack/include")

#to create links for linker use link libraires
target_link_libraries("${PROJECT_NAME}" "hello-pack")

#we need to tell cmake where this link libs will be found using:
target_link_directories("${PROJECT_NAME}" PRIVATE "hello-pack")
