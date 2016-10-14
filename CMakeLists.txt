project(chapterFirstExample)
cmake_minimum_required(VERSION 2.6)

include_directories($ENV{GMOCK_HOME}/include $ENV{GTEST_HOME}/include)
link_directories($ENV{GMOCK_HOME}/mybuild $ENV{GMOCK_HOME}/mybuild/gtest)
add_definitions(-std=c++0x)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall")

set(sources 
   main.cpp 
   SoundexTest.cpp)
add_executable(a ${sources})
target_link_libraries(a gmock)
target_link_libraries(a gtest)
target_link_libraries(a pthread)

