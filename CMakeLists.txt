cmake_minimum_required (VERSION 2.8)
project (googlemock_example)

enable_testing()

# Workaround for GoogleTest std::tr1 build error in VS2017 15.5 Preview 4
# as per https://github.com/google/googletest/issues/1111
# TODO: Remove this set() once the issue is fixed in GoogleTest
add_definitions(-D_SILENCE_TR1_NAMESPACE_DEPRECATION_WARNING)

# google test config
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)

#set(CMAKE_CXX_FLAGS  "-Wall -Wno-sign-compare -g -std=c++0x -O4")

add_subdirectory(vendor/googletest)
add_subdirectory(tests)
