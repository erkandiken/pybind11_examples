cmake_minimum_required(VERSION 3.19.0)
project(example)

set(Python3_FIND_VIRTUALENV FIRST)
find_package(PythonLibs)
find_package(PythonInterp)

add_subdirectory(pybind11)
pybind11_add_module(example example.cpp)
