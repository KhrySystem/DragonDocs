cmake_minimum_required(VERSION 3.24)

option(Dragon_DOCS_LANG "The Language in which Dragon builds its documentation." "en")

doxygen_add_docs(${Dragon_DOCS_LANG}_dg_docs 
	${Dragon_SOURCE_DIR}/headers/include/graphics/DgWindowCreateParams.hpp
	${Dragon_SOURCE_DIR}/headers/include/internal/exception.hpp
	${Dragon_SOURCE_DIR}/headers/include/internal/platform.hpp
	${Dragon_SOURCE_DIR}/headers/include/internal/string.hpp
	${Dragon_SOURCE_DIR}/headers/include/dg_backend.hpp
	${Dragon_SOURCE_DIR}/headers/include/dgEngine.hpp
	${Dragon_SOURCE_DIR}/headers/include/dragon.hpp
	${Dragon_SOURCE_DIR}/headers/include/dragon.hpp
	${Dragon_SOURCE_DIR}/src/dg/dgEngine.cpp
	${Dragon_SOURCE_DIR}/src/dg/init.cpp
	${Dragon_SOURCE_DIR}/src/dg/internal.cpp
)