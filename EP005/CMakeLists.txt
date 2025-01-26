cmake_minimum_required (VERSION 3.5)
project (Tutorial)

#add a static library
add_library(physics STATIC src/physics.cpp)
target_compile_features(physics PRIVATE cxx_std_11)
target_include_directories(physics PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)

#add a static library
add_library(burrito STATIC burrito/src/burrito.cpp)
target_compile_features(burrito PRIVATE cxx_std_11)
target_include_directories(burrito PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/burrito/include)

#This macro is to generate the executable
add_executable(Tutorial main.cpp)
#This macro is to compile the code with c++ compiler which supports C++ 11.
target_compile_features(Tutorial PRIVATE cxx_std_11)
#This macro includes all the header files from the repo
target_include_directories(Tutorial PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)
#Now link both the above library to create a single final executable
target_link_libraries(Tutorial PUBLIC burrito physics)
