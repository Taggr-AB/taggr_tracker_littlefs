if(CONFIG_FILE_SYSTEM_LITTLEFS)
add_library(LITTLEFS INTERFACE)

target_include_directories(LITTLEFS INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})

zephyr_library()
zephyr_library_sources(
    lfs.c
    lfs_util.c
    )
zephyr_library_link_libraries(LITTLEFS)
target_link_libraries(LITTLEFS INTERFACE zephyr_interface)

# zephyr_library_compile_options(-Werror -Wall -Wextra)
# zephyr_library_compile_options(-Wno-error=unused-parameter -Wno-error=unused-const-variable -Wno-error=sign-compare)
# zephyr_library_compile_options(-Wno-unused-variable -Wno-unused-const-variable -Wno-unused-parameter -Wunused-function)
# zephyr_library_compile_options(-fdiagnostics-color)

endif()
