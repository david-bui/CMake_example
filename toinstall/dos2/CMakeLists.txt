target_sources( lib1 PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/oui4_dos2.h>
  )

set_target_properties( lib1 PROPERTIES
  PUBLIC_HEADER
"${CMAKE_CURRENT_LIST_DIR}/oui4_dos2.h;${CMAKE_SOURCE_DIR}/toinstall/dos1/oui1.h"
  )


add_library( lib2 STATIC )

target_sources( lib2 PRIVATE
  oui2.h
  oui2.cc
  )

target_link_libraries( lib2 PUBLIC lib1 )