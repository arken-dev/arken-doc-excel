# ------------------------------------------------------------------------------
#
# Copyright 2016 The Charon Platform Authors.
#
# All rights reserved.
# Use of this source code is governed by a BSD-style
# license that can be found in the LICENSE file.
#
# ------------------------------------------------------------------------------

include_directories(.)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
include_directories(${PROJECT_SOURCE_DIR}/include)
include_directories(${PROJECT_SOURCE_DIR}/deps/include)
include_directories(${PROJECT_SOURCE_DIR}/src/lua/json)

add_library(
    package-excel SHARED
    src/excel.cpp
    src/excelformat.cpp
)

set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/deps)

find_package(Qt5Core)
find_package(Qt5Network)

target_link_libraries( package-excel Qt5::Core lua charon curl json )
target_link_libraries( package-excel Qt5::Network )

add_subdirectory(binding)
