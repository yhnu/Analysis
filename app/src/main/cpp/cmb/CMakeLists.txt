project(cmb_bank)

file(GLOB SRC_CMB ${PROJECT_SOURCE_DIR}/*.cpp)
#file()
include_directories(${PROJECT_SOURCE_DIR}/)
message(STATUS "源码:${SRC_CMB}")
add_library(${PROJECT_NAME} SHARED ${SRC_CMB})
find_library(log_lib log)
target_link_libraries(${PROJECT_NAME} Utils ${log_lib} Substrate)


