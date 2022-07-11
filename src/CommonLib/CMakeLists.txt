# Setup project.


if (PLATFORM_KIND STREQUAL "PLATFORM_WINDOWS")
  include(CMakeLists.win)
elseif (PLATFORM_KIND STREQUAL "PLATFORM_LINUX")
  include(CMakeLists.linux)
else()
  message (FATAL_ERROR "Unknown platform: ${PLATFORM_KIND}" )
endif()
