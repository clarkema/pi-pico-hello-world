# See https://github.com/raspberrypi/pico-sdk for a walkthrough
# of this setup

cmake_minimum_required(VERSION 3.12)

# initialize pico_sdk from submodule
# note: this must happen before project()
include(pico-sdk/pico_sdk_init.cmake)

project(hello_world)

# initialize the Pico SDK
pico_sdk_init()

add_executable(hello_world
    hello_world.c
)

# Add pico_stdlib library which aggregates commonly used features
target_link_libraries(hello_world pico_stdlib)

# create map/bin/hex/uf2 file in addition to ELF.
pico_add_extra_outputs(hello_world)
