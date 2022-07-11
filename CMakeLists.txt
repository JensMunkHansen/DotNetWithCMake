cmake_minimum_required( VERSION 3.0.8)

if (WIN32)
  set(
    PLATFORM_KIND PLATFORM_WINDOWS CACHE STRING
    "Select platform: PLATFORM_WINDOWS or PLATFORM_LINUX")
else()
  set(
    PLATFORM_KIND PLATFORM_LINUX CACHE STRING
    "Select platform: PLATFORM_WINDOWS or PLATFORM_LINUX")
endif()
if (PLATFORM_KIND STREQUAL "PLATFORM_WINDOWS")
  include(CMakeLists.win)
elseif (PLATFORM_KIND STREQUAL "PLATFORM_LINUX")
  include(CMakeLists.linux)
else()
  message (FATAL_ERROR "Unknown platform: ${PLATFORM_KIND}" )
endif()

