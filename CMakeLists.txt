cmake_minimum_required(VERSION 3.1) 
project(sort-cpp VERSION 1.0)            

# OpenCV
find_package(OpenCV REQUIRED)

file(GLOB SOURCE_FILES sort-c++/*.h sort-c++/*.cpp)
add_library(${PROJECT_NAME} ${SOURCE_FILES})
target_include_directories(${PROJECT_NAME} PRIVATE sort-c++/ ${OpenCV_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME})

install(TARGETS ${PROJECT_NAME}
  ARCHIVE DESTINATION lib
  LIBRARY DESTINATION lib
  RUNTIME DESTINATION bin
)
