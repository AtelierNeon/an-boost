# Copyright 2019 Peter Dimov
# Distributed under the Boost Software License, Version 1.0.
# See accompanying file LICENSE_1_0.txt or copy at http://www.boost.org/LICENSE_1_0.txt

cmake_minimum_required(VERSION 3.5...3.16)

project(Boost VERSION 1.75.0 LANGUAGES CXX)

set(BOOST_SUPERPROJECT_VERSION ${PROJECT_VERSION})
set(BOOST_SUPERPROJECT_SOURCE_DIR ${PROJECT_SOURCE_DIR})

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/tools/cmake/include)

option(BOOST_WITH_SHARED_LIBRARIES "Build shared version of the Boost libraries." OFF)
option(BOOST_WITHOUT_APPS "Build Boost without apps." OFF)

set(BOOST_ENABLE_CMAKE ON)
if(BOOST_WITH_SHARED_LIBRARIES)
  set(BUILD_SHARED_LIBS ON)
else()
  set(BUILD_SHARED_LIBS OFF)
endif()

include(BoostRoot)
