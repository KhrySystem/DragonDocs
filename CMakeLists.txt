find_package(Doxygen)

if(Doxygen_FOUND)
	set(DOXYGEN_EXCLUDE_PATTERNS "*.vert.hpp" "*.frag.hpp" "*/aliases.hpp")

	doxygen_add_docs(dgdocs-${DragonEngine_VERSION_MAJOR}
		${CMAKE_CURRENT_SOURCE_DIR}/res
		${DragonEngine_SOURCE_DIR}/modules/core/include
		${DragonEngine_SOURCE_DIR}/modules/graphics/include
		${DragonEngine_SOURCE_DIR}/modules/compute/include
		ALL
		WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
		COMMENT "Generating Dragon HTML documentation" 
	)

	if(Dragon_INSTALL)
		include(GNUInstallDirs)
		install(DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/html/ DESTINATION ${CMAKE_INSTALL_DOCDIR})
	endif()
endif()
