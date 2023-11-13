
add_executable(ssl_test ssl_test.cpp)
target_link_libraries(ssl_test ${Boost_LIBRARIES} OpenSSL::SSL OpenSSL::Crypto)
