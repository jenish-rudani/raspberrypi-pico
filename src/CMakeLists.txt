cmake_minimum_required(VERSION 3.12)

# Pull in SDK (must be before project)
include(pico_sdk_import.cmake)

project(blink C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

set(PICO_EXAMPLES_PATH ${PROJECT_SOURCE_DIR})

# Initialize the SDK
pico_sdk_init()

include(example_auto_set_url.cmake)
# Add blink example
add_executable(blink
        blink.c
        )

# Pull in our pico_stdlib which pulls in commonly used features
target_link_libraries(blink pico_stdlib)
pico_add_extra_outputs(blink)
example_auto_set_url(blink)
