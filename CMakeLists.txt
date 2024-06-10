cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(pico_serialmic)

pico_sdk_init()

add_library(pico_serialmic INTERFACE)

target_sources(pico_serialmic INTERFACE
	${CMAKE_CURRENT_LIST_DIR}/machine_i2s.c)

target_link_libraries(pico_serialmic INTERFACE
	pico_stdlib
	hardware_pio
	hardware_irq
	hardware_dma
)
