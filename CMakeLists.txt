cmake_minimum_required(VERSION 3.9)
project(starter_project)

if(MSVC)
	add_compile_options(/W4)
else()	
	add_compile_options(-Wall -Wextra -Wpedantic)
endif()

add_executable(intro main.cpp)
target_compile_features(intro PRIVATE cxx_lambda_init_captures)

enable_testing()
add_executable(tester tester.cpp)
add_test(Tester tester)
