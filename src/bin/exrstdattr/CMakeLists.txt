# SPDX-License-Identifier: BSD-3-Clause
# Copyright Contributors to the OpenEXR Project.

add_executable(exrstdattr main.cpp)
target_link_libraries(exrstdattr OpenEXR::OpenEXR)
set_target_properties(exrstdattr PROPERTIES
  RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
install(TARGETS exrstdattr DESTINATION ${CMAKE_INSTALL_BINDIR})
if(WIN32 AND (BUILD_SHARED_LIBS OR OPENEXR_BUILD_BOTH_STATIC_SHARED))
  target_compile_definitions(exrstdattr PRIVATE OPENEXR_DLL)
endif()
