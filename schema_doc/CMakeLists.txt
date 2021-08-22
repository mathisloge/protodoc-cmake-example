find_package(protodoc CONFIG REQUIRED)

include(protodoc_generate)
protodoc_generate("${CMAKE_CURRENT_SOURCE_DIR}/protodoc.json" "generate_doc")
