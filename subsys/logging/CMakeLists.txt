# SPDX-License-Identifier: Apache-2.0

if(NOT CONFIG_LOG_MINIMAL)
  zephyr_sources_ifdef(
    CONFIG_LOG
    log_list.c
    log_core.c
    log_msg.c
    log_output.c
  )

  zephyr_sources_ifdef(
    CONFIG_LOG_BACKEND_UART
    log_backend_uart.c
  )

  zephyr_sources_ifdef(
    CONFIG_LOG_CMDS
    log_cmds.c
  )

  zephyr_sources_ifdef(
    CONFIG_LOG_BACKEND_NATIVE_POSIX
    log_backend_native_posix.c
  )

  zephyr_sources_ifdef(
    CONFIG_LOG_BACKEND_XTENSA_SIM
    log_backend_xtensa_sim.c
  )

  zephyr_sources_ifdef(
    CONFIG_LOG_BACKEND_NET
    log_backend_net.c
  )

  zephyr_sources_ifdef(
    CONFIG_LOG_BACKEND_RTT
    log_backend_rtt.c
  )

  zephyr_sources_ifdef(
    CONFIG_LOG_BACKEND_SWO
    log_backend_swo.c
  )

  zephyr_sources_ifdef(
    CONFIG_LOG_BACKEND_QEMU_X86_64
    log_backend_qemu_x86_64.c
  )
else()
  zephyr_sources(log_minimal.c)
endif()
