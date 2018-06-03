#
# project: fips-pcre
#
if (NOT FIPS_IMPORT)
    cmake_minimum_required(VERSION 2.8)
    get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
    include("${FIPS_ROOT_DIR}/cmake/fips.cmake")
    fips_setup(PROJECT fips-pcre)
endif()

fips_begin_lib(pcre)
    add_definitions(-DHAVE_CONFIG_H)
    include_directories(. pcre)
    fips_files(
        pcre.h
        pcre_chartables.c
    )
    fips_dir(pcre GROUP ".")
    fips_files(
        pcre_byte_order.c
        pcre_compile.c
        pcre_config.c
        pcre_dfa_exec.c
        pcre_exec.c
        pcre_fullinfo.c
        pcre_get.c
        pcre_globals.c
        pcre_jit_compile.c
        pcre_maketables.c
        pcre_newline.c
        pcre_ord2utf8.c
        pcre_refcount.c
        pcre_string_utils.c
        pcre_study.c
        pcre_tables.c
        pcre_ucd.c
        pcre_valid_utf8.c
        pcre_version.c
        pcre_xclass.c
    )
fips_end_lib()

if (NOT FIPS_IMPORT)
    fips_finish()
endif()
