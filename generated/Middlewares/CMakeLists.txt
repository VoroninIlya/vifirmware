file(GLOB CORE_SRCS 
  ${CMAKE_CURRENT_SOURCE_DIR}/ST/filex/common/src/*.c
  ${CMAKE_CURRENT_SOURCE_DIR}/ST/levelx/common/src/*.c
  ${CMAKE_CURRENT_SOURCE_DIR}/ST/threadx/common/src/*.c
  ${CMAKE_CURRENT_SOURCE_DIR}/ST/threadx/ports/cortex_m4/gnu/src/*.S
  ${CMAKE_CURRENT_SOURCE_DIR}/ST/threadx/utility/low_power/*.c
  ${CMAKE_CURRENT_SOURCE_DIR}/ST/usbx/common/core/src/*.c
  ${CMAKE_CURRENT_SOURCE_DIR}/ST/usbx/common/usbx_host_classes/src/*.c
#  ${CMAKE_CURRENT_SOURCE_DIR}/ST/touchgfx/framework/source/platform/driver/touch/*.cpp
#  ${CMAKE_CURRENT_SOURCE_DIR}/ST/touchgfx/framework/source/platform/hal/simulator/sdl2/*.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/ST/touchgfx/framework/source/touchgfx/containers/clock/*.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/ST/touchgfx/framework/source/touchgfx/containers/progress_indicators/*.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/ST/touchgfx/framework/source/touchgfx/containers/scrollers/*.cpp
  )

get_property(tmp GLOBAL PROPERTY sources_list)

foreach(source_file IN LISTS CORE_SRCS)
   set(tmp "${tmp}${source_file};")
endforeach()

set_property(GLOBAL PROPERTY sources_list "${tmp}")

get_property(tmp GLOBAL PROPERTY include_paths_list)
set(tmp "${tmp}\
${CMAKE_CURRENT_SOURCE_DIR}/ST/filex/common/inc;\
${CMAKE_CURRENT_SOURCE_DIR}/ST/filex/ports/generic/inc;\
${CMAKE_CURRENT_SOURCE_DIR}/ST/levelx/common/inc;\
${CMAKE_CURRENT_SOURCE_DIR}/ST/threadx/common/inc;\
${CMAKE_CURRENT_SOURCE_DIR}/ST/threadx/ports/cortex_m4/gnu/inc;\
${CMAKE_CURRENT_SOURCE_DIR}/ST/threadx/utility/low_power;\
${CMAKE_CURRENT_SOURCE_DIR}/ST/usbx/common/core/inc;\
${CMAKE_CURRENT_SOURCE_DIR}/ST/usbx/common/usbx_host_classes/inc;\
${CMAKE_CURRENT_SOURCE_DIR}/ST/usbx/ports/generic/inc;\
${CMAKE_CURRENT_SOURCE_DIR}/ST/touchgfx/framework/include;")

set_property(GLOBAL PROPERTY include_paths_list "${tmp}")