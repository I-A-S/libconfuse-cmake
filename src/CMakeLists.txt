add_library(libconfuse STATIC
  lexer.c
  confuse.c
  reallocarray.c
)

if(NOT HAVE_FMEMOPEN)
  target_sources(libconfuse PRIVATE fmemopen.c)
endif()

if(WIN32)
  target_compile_definitions(libconfuse PUBLIC
    _CRT_SECURE_NO_WARNINGS
    _CRT_NONSTDC_NO_WARNINGS
    _SCL_SECURE_NO_WARNINGS
  )
endif()

target_include_directories(libconfuse PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

target_compile_definitions(libconfuse PUBLIC 
  BUILDING_STATIC
  PACKAGE_VERSION="2.5"
  PACKAGE_STRING="libConfuse 2.5"
)
target_compile_definitions(libconfuse PRIVATE
  $<$<BOOL:${HAVE_FMEMOPEN}>:HAVE_FMEMOPEN>
  $<$<BOOL:${HAVE_REALLOCARRAY}>:HAVE_REALLOCARRAY>
  $<$<BOOL:${HAVE_STRDUP}>:HAVE_STRDUP>
  $<$<BOOL:${HAVE_STRNDUP}>:HAVE_STRNDUP>
  $<$<BOOL:${HAVE_STRCASECMP}>:HAVE_STRCASECMP>
)
