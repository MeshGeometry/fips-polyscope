if (NOT FIPS_IMPORT)
    cmake_minimum_required(VERSION 2.8)
    get_filename_component(FIPS_ROOT_DIR "../fips" ABSOLUTE)
    include("${FIPS_ROOT_DIR}/cmake/fips.cmake")
    
    set(FIPS_EXCEPTIONS ON CACHE BOOL "Enable C++ exceptions" FORCE)
    set(FIPS_RTTI  ON CACHE BOOL "Enable C++ RTTI" FORCE)

    fips_setup()
    fips_project(fips-polyscope)
endif()



fips_add_subdirectory(polyscope/)
fips_libs(polyscope)


if (NOT FIPS_IMPORT)
    fips_finish()
endif()