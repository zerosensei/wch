# Makefile - CH32SERIES SDK
#
# Copyright (c) 2021 Nanjing Qinheng Microelectronics Co., Ltd.
#
# SPDX-License-Identifier: Apache-2.0


zephyr_library()

zephyr_compile_definitions(
  -D${CONFIG_SOC}
  -DUSE_HAL_DRIVER
  )

if(CONFIG_CLOCK_CH32_HSE_CLOCK)
  zephyr_compile_definitions( -DHSE_VALUE=${CONFIG_CLOCK_CH32_HSE_CLOCK} )
endif()

zephyr_include_directories(ch32v30x/soc)  
zephyr_include_directories(ch32v30x/drivers/inc)

add_subdirectory(ch32v30x)