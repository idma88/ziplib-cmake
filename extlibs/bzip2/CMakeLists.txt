cmake_minimum_required(VERSION 2.6)
project(bzip2)

set (CMAKE_CXX_STANDARD 11)
add_definitions(-std=c++11)

set(headers
	bzlib.h
	bzlib_private.h
)

set(src
	blocksort.c
	bzerror.c
	bzlib.c
	compress.c
	crctable.c
	decompress.c
	huffman.c
	randtable.c
)

set(sources
	${headers}
	${src}
)

add_library(${PROJECT_NAME} STATIC ${sources})
set_target_properties(${PROJECT_NAME} PROPERTIES COMPILE_DEFINITIONS "BZ_NO_STDIO")
set_target_properties(${PROJECT_NAME} PROPERTIES COMPILE_FLAGS " /wd4996 /wd4244")


