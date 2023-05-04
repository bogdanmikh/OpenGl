cmake_minimum_required(VERSION 3.16)
project(AMSTL)

set(CMAKE_CXX_STANDARD 14)

add_executable(AMSTL AMSTL/include/AMSTL/ArrayList.hpp 
AMSTL/include/AMSTL/LinkedList.hpp AMSTL/include/AMSTL/Vector2.hpp 
AMSTL/include/AMSTL/Vector3.hpp AMSTL/include/AMSTL/govnoMap.hpp
AMSTL/include/AMSTL/Map.hpp)