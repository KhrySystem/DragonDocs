find_package(Doxygen REQUIRED)

set(Dragon_DOXYGEN_INPUT "")

string(APPEND Dragon_DOXYGEN_INPUT " \\\n\"${CMAKE_CURRENT_SOURCE_DIR}/res\"")
string(APPEND Dragon_DOXYGEN_INPUT " \\\n\"${DragonEngine_SOURCE_DIR}/modules/core/include\"")
string(APPEND Dragon_DOXYGEN_INPUT " \\\n\"${DragonEngine_SOURCE_DIR}/modules/graphics/include\"")

configure_file(Doxyfile.in Doxyfile @ONLY)
configure_file(sphinx/conf.py.in ${CMAKE_CURRENT_SOURCE_DIR}/sphinx/conf.py)

add_custom_target(dgdocs-${DragonEngine_VERSION_MAJOR} ALL "${DOXYGEN_EXECUTABLE}"
	WORKING_DIRECTORY "${DragonEngine_BINARY_DIR}/docs"
	COMMENT "Generating Dragon HTML documentation" 
	SOURCES ${DragonDocs_SOURCE} ${DragonDocs_CORE_SOURCE} ${DragonDocs_GRAPHICS_SOURCE}
	VERBATIM
)
