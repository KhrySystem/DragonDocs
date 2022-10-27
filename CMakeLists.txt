cmake_minimum_required(VERSION 3.20)

file(GLOB_RECURSE Dragon_Docs_Source ${Dragon_SOURCE_DIR}/docs/res)
file(GLOB_RECURSE Dragon_Main_Docs_SOURCE ${Dragon_SOURCE_DIR}/headers/include)
file(GLOB_RECURSE Dragon_Firebreath_Docs_SOURCE ${Dragon_SOURCE_DIR}/extensions/firebreath/include)
file(GLOB_RECURSE Dragon_Ironbreath_Docs_SOURCE ${Dragon_SOURCE_DIR}/extensions/ironbreath/include)
file(GLOB_RECURSE Dragon_Lightbreath_Docs_SOURCE ${Dragon_SOURCE_DIR}/extensions/lightbreath/include)
file(GLOB_RECURSE Dragon_Streambreath_Docs_SOURCE ${Dragon_SOURCE_DIR}/extensions/streambreath/include)
file(GLOB_RECURSE Dragon_Thunderbreath_Docs_SOURCE ${Dragon_SOURCE_DIR}/extensions/thunderbreath/include)

set(Dragon_DOXYGEN_INPUT 
	${Dragon_Docs_SOURCE} 
	${Dragon_Main_Docs_SOURCE}
	${Dragon_Firebreath_Docs_SOURCE} 
	${Dragon_Ironbreath_Docs_SOURCE}
	${Dragon_Lightbreath_Docs_SOURCE}
	${Dragon_Streambreath_Docs_SOURCE}
	${Dragon_Thunderbreath_Docs_SOURCE}
)

configure_file(Doxyfile.in Doxyfile @ONLY)

add_custom_target(Dragon_Docs ALL "${DOXYGEN_EXECUTABLE}"
	WORKING_DIRECTORY "${Dragon_BINARY_DIR}/docs"
	COMMENT "Generating Dragon HTML documentation" VERBATIM
)