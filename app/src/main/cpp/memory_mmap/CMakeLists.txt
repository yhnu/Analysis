project(sigbus_test)

file(GLOB SRC_SUB ${CMAKE_CURRENT_SOURCE_DIR}/mmap_res.c)

#add_library(${PROJECT_NAME} STATIC ${SRC_SUB})
#add_library(${PROJECT_NAME}  SHARED  ${SRC_SUB})
add_executable(${PROJECT_NAME} ${SRC_SUB})
target_link_libraries(${PROJECT_NAME}    )

target_include_directories(${PROJECT_NAME}
        INTERFACE
        $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/>
        $<INSTALL_INTERFACE:include>)
add_executable(testsigbus testsigbus.c)
add_executable(testsigsegv testsigsegv.c)