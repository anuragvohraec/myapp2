cmake_minimum_required(VERSION 3.4.1)

project("myapp2" C)

add_subdirectory("hello-pack")
add_subdirectory("hello-world-pack")

add_executable("${PROJECT_NAME}" myapp2.c)
target_include_directories("${PROJECT_NAME}" 
    PRIVATE "hello-pack/include" 
    PRIVATE "hello-world-pack/include")
target_link_libraries("${PROJECT_NAME}" "hello-pack" "hello-world")
target_link_directories("${PROJECT_NAME}" 
PRIVATE "hello-pack"
PRIVATE "hello-world-pack")

