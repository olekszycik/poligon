cmake_minimum_required(VERSION 3.15)
set(CMAKE_CXX_STANDARD 17)
set(CXX_STANDARD_REQUIRED ON)

project(poligon
	LANGUAGES CXX
)

add_executable(poligon main.cpp)

if(WIN32)
	add_compile_options(poligon PRIVATE /W4 /WX)
elseif(UNIX)
	add_compile_options(poligon PRIVATE -Wall -Wextra -Wpedantic -Werror)
else()
	message(WARNING "Building on unsupported configuration.")
endif()
