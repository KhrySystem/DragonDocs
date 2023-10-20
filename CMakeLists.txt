find_package(Doxygen REQUIRED)

file(GLOB_RECURSE DragonDocs_Source ${CMAKE_CURRENT_SOURCE_DIR}/res)
file(GLOB_RECURSE DragonDocs_CORE_SOURCE ${DragonEngine_SOURCE_DIR}/modules/core/include)

set(Dragon_DOXYGEN_INPUT 
	${DragonDocs_SOURCE} 
	${DragonDocs_CORE_SOURCE}

)

configure_file(Doxyfile.in Doxyfile @ONLY)

add_custom_target(Dragon_Docs ALL "${DOXYGEN_EXECUTABLE}"
	WORKING_DIRECTORY "${DragonEngine_BINARY_DIR}/docs"
	COMMENT "Generating Dragon HTML documentation" VERBATIM
)