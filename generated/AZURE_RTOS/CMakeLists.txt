file(GLOB CORE_SRCS 
  ${CMAKE_CURRENT_SOURCE_DIR}/App/*.c)

get_property(tmp GLOBAL PROPERTY sources_list)

foreach(source_file IN LISTS CORE_SRCS)
   set(tmp "${tmp}${source_file};")
endforeach()

set_property(GLOBAL PROPERTY sources_list "${tmp}")

get_property(tmp GLOBAL PROPERTY include_paths_list)
set(tmp "${tmp}\
${CMAKE_CURRENT_SOURCE_DIR}/App;")

set_property(GLOBAL PROPERTY include_paths_list "${tmp}")