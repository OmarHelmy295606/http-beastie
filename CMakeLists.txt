cmake_minimum_required(VERSION 3.16)
project(HTTPServer)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Boost REQUIRED COMPONENTS system)
find_package(Threads REQUIRED)

add_executable(server
	src/main.cpp
	src/utils.cpp
)

target_include_directories(server PRIVATE
	${Boost_INCLUDE_DIRS}
	include
)
target_link_libraries(server
	PRIVATE
	Boost::system
	Threads::Threads
)
