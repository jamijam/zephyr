zephyr_library()
zephyr_library_include_directories(. ../..)
zephyr_library_compile_definitions_ifdef(
  CONFIG_NEWLIB_LIBC __LINUX_ERRNO_EXTENSIONS__
  )

zephyr_library_sources_ifdef(CONFIG_NET_ARP              arp.c)
zephyr_library_sources_ifdef(CONFIG_NET_L2_ETHERNET      ethernet.c)
zephyr_library_sources_ifdef(CONFIG_NET_L2_ETHERNET_MGMT ethernet_mgmt.c)
zephyr_library_sources_ifdef(CONFIG_NET_STATISTICS_ETHERNET ethernet_stats.c)
