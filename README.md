# hello-world

## Requirements

- Git
- C++ Compiler ...
- CMake

Installation Instructions: TODO

## Building

cmake -S . -B build
cmake --build build --config Debug
build\Debug\hello_world.exe

## Testing

[Build](#building)

ctest --test-dir build -C Debug
Add -V for verbose testing
