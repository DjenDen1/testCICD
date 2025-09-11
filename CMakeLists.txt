cmake_minimum_required(VERSION 3.10.0)
project(laboratory1 VERSION 0.1.0 LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Создаем версионный файл если его нет
add_custom_command(
    OUTPUT version_counter.txt
    COMMAND ${CMAKE_COMMAND} -E touch version_counter.txt
    COMMENT "Creating version_counter.txt if missing"
)

add_executable(laboratory1 main.cpp version.cpp version.h version_counter.txt)

set_target_properties(laboratory1 PROPERTIES OUTPUT_NAME "auto_version_app")