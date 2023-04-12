# ======================================================================== #
# Copyright 2018-2019 Ingo Wald                                            #
#                                                                          #
# Licensed under the Apache License, Version 2.0 (the "License");          #
# you may not use this file except in compliance with the License.         #
# You may obtain a copy of the License at                                  #
#                                                                          #
#     http://www.apache.org/licenses/LICENSE-2.0                           #
#                                                                          #
# Unless required by applicable law or agreed to in writing, software      #
# distributed under the License is distributed on an "AS IS" BASIS,        #
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. #
# See the License for the specific language governing permissions and      #
# limitations under the License.                                           #
# ======================================================================== #

cmake_minimum_required(VERSION 3.10)

if(POLICY CMP0048)
  cmake_policy(SET CMP0048 NEW)
endif(POLICY CMP0048)

project(glui VERSION 0.1.0)

#
# CMP0072 introduced in cmake 3.11
#
# Prefer using GLVND by default when available.
#
# run `cmake --help-policy CMP0072` to know more
#
if (POLICY CMP0072)
  cmake_policy (SET CMP0072 NEW)
endif(POLICY CMP0072)

find_package(GLUT REQUIRED)
find_package(OpenGL REQUIRED)

include_directories(${GLUT_INCLUDE_DIR})
include_directories(${CMAKE_SOURCE_DIR}/include)

add_subdirectory(glui)
add_subdirectory(samples)

