cmake_minimum_required(VERSION 3.16)

project("OpenGl")

set(CMAKE_CXX_STANDARD 14)

set(BIN_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin)

add_executable(OpenGl scr/main.cpp) 

target_include_directories(OpenGl PRIVATE src)

# GLFW
add_subdirectory(vendor/glfw)

target_link_libraries(OpenGl glfw)
target_include_directories(OpenGl PRIVATE vendor/glfw/include)

# GLAD
add_subdirectory(vendor/glad)

target_link_libraries(OpenGl glad)
target_include_directories(OpenGl PRIVATE vendor/glad/include)

# GLM
add_subdirectory(vendor/glm)

target_link_libraries(OpenGl glm)
target_include_directories(OpenGl PRIVATE vendor/glm)

# STB_IMAGE
add_subdirectory(vendor/stb_image)

target_link_libraries(OpenGl stb_image)
target_include_directories(OpenGl PRIVATE vendor/stb_image)

# imgui
add_subdirectory(vendor/imgui)

target_link_libraries(OpenGl imgui)
target_include_directories(OpenGl PRIVATE vendor/imgui)

# set output directories for all builds (Debug, Release, etc.)
foreach( OUTPUTCONFIG ${CMAKE_CONFIGURATION_TYPES} )
    string( TOUPPER ${OUTPUTCONFIG} OUTPUTCONFIG )
    set_target_properties(OpenGl
        PROPERTIES
        RUNTIME_OUTPUT_DIRECTORY_${OUTPUTCONFIG} ${BIN_DIRECTORY}
    )
endforeach( OUTPUTCONFIG CMAKE_CONFIGURATION_TYPES )