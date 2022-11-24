# ------------------------------------------------------------------------------
#
# Copyright 2016 The Arken Platform Authors.
#
# All rights reserved.
# Use of this source code is governed by a CPOL
# license that can be found in the LICENSE file.
#
# ------------------------------------------------------------------------------

include_directories(.)
include_directories(${PROJECT_SOURCE_DIR}/include)
include_directories(${PROJECT_SOURCE_DIR}/deps/include)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/clib/arken/doc)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/clib/arken/doc)

add_library(
  Excel SHARED excel.cpp
)

set_target_properties(Excel PROPERTIES PREFIX "")

target_link_libraries(Excel arken excel)
