cmake_minimum_required(VERSION 3.5)

project(TestProject)

set(TESTPROJECT_SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/Source)
set(TESTPROJECT_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/Include)
set(TESTPROJECT_SOURCE_FILES ${TESTPROJECT_SOURCE_DIR}/Main.cpp)

add_subdirectory(TestLib)

add_executable(TestProject ${TESTPROJECT_SOURCE_FILES})
target_include_directories(TestProject PRIVATE ${TESTPROJECT_INCLUDE_DIR})
target_include_directories(TestProject PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/TestLib/Include)
target_link_libraries(TestProject TestLib)