macro(export)
endmacro()

if(SRB2_CONFIG_SHARED_INTERNAL_LIBRARIES)
	set(SRB2_INTERNAL_LIBRARY_TYPE SHARED)
	set(NOT_SRB2_CONFIG_SHARED_INTERNAL_LIBRARIES OFF)
else()
	set(SRB2_INTERNAL_LIBRARY_TYPE STATIC)
	set(NOT_SRB2_CONFIG_SHARED_INTERNAL_LIBRARIES ON)
endif()

if(NOT "${SRB2_CONFIG_SYSTEM_LIBRARIES}")
	include("cpm-sdl2.cmake")
	include("cpm-sdl2-mixer.cmake")
	include("cpm-zlib.cmake")
	include("cpm-png.cmake")
	include("cpm-curl.cmake")
	include("cpm-openmpt.cmake")
endif()

include("cpm-libgme.cmake")
