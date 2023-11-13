
add_executable(file_server file_server.cpp file_socket.cpp)
target_link_libraries(file_server ${Boost_LIBRARIES})
