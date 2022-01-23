cmake_minimum_required(VERSION 3.0.0)
project(test_cmake VERSION 0.1.0)
include(CTest)
enable_testing()


find_package(wxWidgets REQUIRED)
include(${wxWidgets_USE_FILE})
add_executable(${PROJECT_NAME} main.cpp)

target_include_directories(test_cmake PRIVATE ${wxWidgets_INCLUDE_DIRS})
target_link_libraries(test_cmake PRIVATE ${wxWidgets_LIBRARIES})

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
