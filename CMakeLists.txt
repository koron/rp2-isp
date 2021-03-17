cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

include(pico_sdk_import.cmake)

project(isp C CXX ASM)

pico_sdk_init()

add_executable(isp
	isp.c
	)

pico_set_program_name(isp "isp")
pico_set_program_version(isp "0.1")

pico_enable_stdio_uart(isp 1)
pico_enable_stdio_usb(isp 0)

target_link_libraries(isp
	pico_stdlib
	)

target_link_libraries(isp
        hardware_spi
        )

pico_add_extra_outputs(isp)

