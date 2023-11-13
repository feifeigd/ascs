
add_executable(debug_assistant debug_assistant.cpp)
target_link_libraries(debug_assistant ${Boost_LIBRARIES} OpenSSL::SSL OpenSSL::Crypto)
