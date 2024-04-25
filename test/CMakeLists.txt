cmake_minimum_required(VERSION 3.14)

project("test" LANGUAGES CXX C)

add_executable(${PROJECT_NAME} ${PROJECT_NAME}.cpp)
target_include_directories(${PROJECT_NAME} PUBLIC ${VIENNAPS_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} PRIVATE ${VIENNAPS_LIBRARIES})
configure_file(test.gds ${CMAKE_CURRENT_BINARY_DIR}/test.gds COPYONLY)

set(VIENNAPS_PATH "/your/local/installation")
list(APPEND CMAKE_PREFIX_PATH "/your/local/installation")

find_package(ViennaPS   PATHS ${VIENNAPS_PATH})
