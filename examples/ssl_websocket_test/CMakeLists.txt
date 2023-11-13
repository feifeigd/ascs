
add_executable(ssl_websocket_test ssl_websocket_test.cpp)
target_link_libraries(ssl_websocket_test ${Boost_LIBRARIES} OpenSSL::SSL OpenSSL::Crypto)
