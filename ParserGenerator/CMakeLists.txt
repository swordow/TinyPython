# Reference Makefile.pre.in
cmake_minimum_required (VERSION 3.4)

set(parser_src
    ../Parser/acceler.c
    ../Parser/bitset.c
    ../Parser/firstsets.c
    ../Parser/grammar.c
    ../Parser/grammar1.c
    #../Parser/intrcheck.c
    ../Parser/listnode.c
    ../Parser/metagrammar.c
    #../Parser/myreadline.c
    ../Parser/node.c
    ../Parser/parser.c
    ../Parser/parser.h
    ../Parser/parsetok.c
    ../Parser/printgrammar.c
    ../Parser/tokenizer.c
    ../Parser/tokenizer.h
)

set(pgen_src
   	../Objects/obmalloc.c
	../PythonCore/mysnprintf.c
	../PythonCore/pyctype.c
	pgenmain.c
	pgen.c
	${parser_src}
)

include_directories(Include)

add_executable(pgen ${pgen_src})

target_compile_definitions(pgen PRIVATE ${TPYCORE_DEF} -DPGEN)

#target_link_libraries(
#pgen
#${CMAKE_CURRENT_SOURCE_DIR}/../parser.lib
#)


set_target_properties(
pgen
PROPERTIES 
ARCHIVE_OUTPUT_DIRECTORY_DEBUG "${CMAKE_CURRENT_SOURCE_DIR}"
ARCHIVE_OUTPUT_DIRECTORY_RELEASE "${CMAKE_CURRENT_SOURCE_DIR}"
ARCHIVE_OUTPUT_DIRECTORY_MINSIZEREL "${CMAKE_CURRENT_SOURCE_DIR}"
ARCHIVE_OUTPUT_DIRECTORY_RELWITHDEBINFO "${CMAKE_CURRENT_SOURCE_DIR}"
)
