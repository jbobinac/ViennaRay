cmake_minimum_required(VERSION 3.4)

project("buildBoundary2D")

add_executable(${PROJECT_NAME} ${PROJECT_NAME}.cpp)
target_include_directories(${PROJECT_NAME} PUBLIC "${VIENNARAY_INCLUDE_DIRS}")
target_link_libraries(${PROJECT_NAME} PRIVATE ${VIENNARAY_LIBRARIES})

add_dependencies(buildTests ${PROJECT_NAME})
add_test(NAME ${PROJECT_NAME} COMMAND $<TARGET_FILE:${PROJECT_NAME}>)