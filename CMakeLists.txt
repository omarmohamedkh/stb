aux_source_directory(. STB_SRC_DIR)

set(LIBRARY_NAME stb)
add_library(${LIBRARY_NAME} STATIC)

target_sources(${LIBRARY_NAME} PRIVATE ${STB_SRC_DIR})

target_include_directories(
  ${LIBRARY_NAME}
  PRIVATE $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include/${LIBRARY_NAME}>
          $<INSTALL_INTERFACE:include/${LIBRARY_NAME}>)

target_include_directories(
  ${LIBRARY_NAME} PUBLIC $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
                         $<INSTALL_INTERFACE:include>)
