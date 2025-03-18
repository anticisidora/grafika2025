cmake_minimum_required(VERSION 3.11)
project(APP)
file(GLOB sources src/*.cpp)
file(GLOB headers include/*.hpp)

include_directories(${CMAKE_SOURCE_DIR}/engine/libs/glad/include)
file(GLOB glad_sources ${CMAKE_SOURCE_DIR}/engine/libs/glad/src/glad.c)

include_directories(include/)

add_executable(${PROJECT_NAME} ${sources} ${headers} ${glad_sources})
target_link_libraries(${PROJECT_NAME} PRIVATE matf-rg-engine GL)
target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_20)
set_target_properties(${PROJECT_NAME} PROPERTIES RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}")