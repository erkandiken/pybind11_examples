cmake_minimum_required(VERSION 3.19.0)
project(example)

set(Python3_FIND_VIRTUALENV FIRST)
find_package(PythonLibs)
find_package(PythonInterp)

set (CMAKE_CXX_STANDARD 14)

find_package( PkgConfig )
pkg_check_modules( EIGEN3 REQUIRED eigen3 )
include_directories( ${EIGEN3_INCLUDE_DIRS} )

add_subdirectory(pybind11)
pybind11_add_module(example example.cpp)
