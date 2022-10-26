cmake_minimum_required(VERSION 3.24)

set(Dragon_Docs_SOURCE
	headers/include/internal/platform.hpp
	headers/include/internal/string.hpp
	headers/include/dg_backend.hpp
	headers/include/dgEngine.hpp
	headers/include/dragon.hpp
	headers/include/dragon.hpp
)

foreach(path IN LISTS Dragon_Docs_SOURCE)
    set(GLFW_DOXYGEN_INPUT "${GLFW_DOXYGEN_INPUT} \\\n\"${GLFW_SOURCE_DIR}/${path}\"")
endforeach()

configure_file(Doxyfile.in Doxyfile @ONLY)

add_custom_target(docs ALL "${DOXYGEN_EXECUTABLE}"
	WORKING_DIRECTORY "${Dragon_BINARY_DIR}/docs"
	COMMENT "Generating HTML documentation" VERBATIM
)