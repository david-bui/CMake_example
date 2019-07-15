add_library( lib1 STATIC )

target_sources( lib1 PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/oui1.h>
  $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/oui1.cc>
  )

target_include_directories( lib1 PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}>
  $<INSTALL_INTERFACE:include>
  )

set_target_properties( lib1 PROPERTIES
  PUBLIC_HEADER ${CMAKE_CURRENT_LIST_DIR}/oui1.h
  )

add_executable( mon_exe vide.cc )

target_link_libraries( mon_exe PUBLIC lib1 lib2 )
