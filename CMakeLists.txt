cmake_minimum_required(VERSION 3.14)

# Set the project name and version
project(HelloWorld VERSION 1.0)

# Specify the C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add the executable
add_executable(hello_world src/main.cpp)

# --- GoogleTest (for integration tests that run the built binary) ---
include(FetchContent)
FetchContent_Declare(
	googletest
	URL https://github.com/google/googletest/archive/refs/tags/release-1.12.1.zip
)
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

enable_testing()

# Test that runs the built binary. The test source will launch the binary by path.
add_executable(test_binary tests/test_binary.cpp)
target_link_libraries(test_binary PRIVATE GTest::gtest)

# Provide the path to the built executable to the test via a compile definition.
if (WIN32)
	# Visual Studio places executables in configuration subfolders (Debug/Release)
	set(EXE_SUBDIR $<CONFIG>)
else()
	set(EXE_SUBDIR "")
endif()

add_test(NAME run_hello_binary COMMAND test_binary $<TARGET_FILE:hello_world>)
