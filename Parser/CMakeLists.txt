cmake_minimum_required (VERSION 3.4)

set(parser_src
    acceler.c
    bitset.c
    firstsets.c
    grammar.c
    grammar1.c
    intrcheck.c
    listnode.c
    metagrammar.c
    myreadline.c
    node.c
    parser.c
    parser.h
    parsetok.c
    printgrammar.c
    tokenizer.c
    tokenizer.h
)

include_directories(Include)
add_library(parser STATIC ${parser_src})
message(STATUS "Parser Macro" ${TPYCORE_DEF})
target_compile_definitions(parser PRIVATE ${TPYCORE_DEF})

set_target_properties(
parser
PROPERTIES 
ARCHIVE_OUTPUT_DIRECTORY_DEBUG "${CMAKE_CURRENT_SOURCE_DIR}../../"
ARCHIVE_OUTPUT_DIRECTORY_RELEASE "${CMAKE_CURRENT_SOURCE_DIR}../../"
ARCHIVE_OUTPUT_DIRECTORY_MINSIZEREL "${CMAKE_CURRENT_SOURCE_DIR}../../"
ARCHIVE_OUTPUT_DIRECTORY_RELWITHDEBINFO "${CMAKE_CURRENT_SOURCE_DIR}../../"
)
