# This is the counterpart to lib/Threading/CMakeLists.txt.  Any updates
# need to be reflected in both places.

list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../../cmake/modules")
include(AddSwiftStdlib)

add_swift_target_library(swiftThreading OBJECT_LIBRARY
  "${SWIFT_SOURCE_DIR}/lib/Threading/C11.cpp"
  "${SWIFT_SOURCE_DIR}/lib/Threading/Linux.cpp"
  "${SWIFT_SOURCE_DIR}/lib/Threading/Pthreads.cpp"
  "${SWIFT_SOURCE_DIR}/lib/Threading/Win32.cpp"
  INSTALL_IN_COMPONENT never_install)

# This is only used by the compatibility libraries
add_swift_target_library(swiftThreadingWithFatal OBJECT_LIBRARY
  "${SWIFT_SOURCE_DIR}/lib/Threading/C11.cpp"
  "${SWIFT_SOURCE_DIR}/lib/Threading/Linux.cpp"
  "${SWIFT_SOURCE_DIR}/lib/Threading/Pthreads.cpp"
  "${SWIFT_SOURCE_DIR}/lib/Threading/Win32.cpp"
  "${SWIFT_SOURCE_DIR}/lib/Threading/Errors.cpp"
  INSTALL_IN_COMPONENT never_install)
