cmake_minimum_required(VERSION 3.10)


project(contract)
set(CMAKE_CXX_STANDARD 11)
find_package(Protobuf REQUIRED)
include_directories(${PROTOBUF_INCLUDE_DIRS})
include_directories(${CMAKE_CURRENT_BINARY_DIR})
protobuf_generate_cpp(PROTO_SRCS PROTO_HDRS rx.proto)
add_library(contract ${PROTO_SRCS} ${PROTO_HDRS})
target_link_libraries(contract ${PROTOBUF_LIBRARIES})
