cmake_minimum_required (VERSION 3.5)
project (Tutorial)
add_executable(Tutorial main.cpp
               src/physics.cpp
               src/burrito.cpp)
target_compile_features(Tutorial PRIVATE cxx_std_11)
target_include_directories(Tutorial PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)