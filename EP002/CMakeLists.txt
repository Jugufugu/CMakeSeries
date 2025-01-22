cmake_minimum_required (VERSION 3.5)
project (Tutorial)
add_executable(Tutorial main.cpp)
target_compile_features(Tutorial PRIVATE cxx_std_11)