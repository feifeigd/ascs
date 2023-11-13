cmake_minimum_required(VERSION 3.20)

project(ascs C CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

if(MSVC)
    add_definitions(
        -D_WIN32_WINNT=0X0601
        /bigobj
    )
endif()

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

enable_testing()

find_package(GTest CONFIG REQUIRED) 

include_directories(
    include
)

# Boost
set(Boost_USE_STATIC_LIBS ON)
set(Boost_USE_STATIC_RUNTIME ON)
# set(Boost_INCLUDE_DIR ${_VCPKG_INSTALLED_DIR}/x64-windows-static/include)
find_package(Boost COMPONENTS  system REQUIRED)
if(Boost_FOUND)
    # message(STATUS "${Boost_INCLUDE_DIR} and ${Boost_INCLUDE_DIRS}")
    # message(${Boost_LIBRARY_DIRS})
    include_directories(${Boost_INCLUDE_DIRS})
    link_directories(${Boost_LIBRARY_DIRS})
endif()

# openssl
find_package(OpenSSL REQUIRED)

add_subdirectory(examples)
