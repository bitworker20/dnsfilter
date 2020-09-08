cmake_minimum_required(VERSION 3.15)

project(dnsfilter LANGUAGES CXX)

set(Boost_USE_STATIC_LIBS ON)
find_package(Boost QUIET REQUIRED COMPONENTS program_options)

if(NOT Boost_FOUND)
    message(FATAL_ERROR "Boost Not found")
endif()

add_executable(dnsfilter dnsfilter.cpp)

target_link_libraries(dnsfilter PUBLIC Boost::program_options)
