find_package(protodoc CONFIG REQUIRED)
find_program(ASCIIDOCTOR_EXE asciidoctor)

include(protodoc_generate)
protodoc_generate("${CMAKE_CURRENT_SOURCE_DIR}/protodoc.json" "generate_doc")

set(ASCIIDOC_MAIN "${CMAKE_CURRENT_SOURCE_DIR}/docs/main.adoc")
add_custom_target("site"
    COMMAND ${ASCIIDOCTOR_EXE} -D ${CMAKE_CURRENT_BINARY_DIR}/site -o index.html "${ASCIIDOC_MAIN}"
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR})
