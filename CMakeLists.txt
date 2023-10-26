find_package(Doxygen)

if(Doxygen_FOUND)
	set(DOXYGEN_EXCLUDE_PATTERNS "*.vert.hpp" "*.frag.hpp" "*/aliases.hpp")

	doxygen_add_docs(dgdocs-${DragonEngine_VERSION_MAJOR}
		${CMAKE_CURRENT_SOURCE_DIR}/res
		${DragonEngine_SOURCE_DIR}/modules/core/include
		${DragonEngine_SOURCE_DIR}/modules/graphics/include
		ALL
		WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
		COMMENT "Generating Dragon HTML documentation" 
	)
endif()
