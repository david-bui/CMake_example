add_subdirectory( dos1 )
add_subdirectory( dos2 )

include( GNUInstallDirs )


install( TARGETS lib1 mon_exe lib2 EXPORT testinstall
  RUNTIME DESTINATION bin
  LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
  PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
  )

install( EXPORT testinstall DESTINATION ${CMAKE_CURRENT_BINARY_DIR} )