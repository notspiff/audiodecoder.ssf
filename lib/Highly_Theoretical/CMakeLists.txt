project(Highly_Theoretical)

enable_language(C)

cmake_minimum_required(VERSION 2.6)

set(SOURCES Core/sega.c
            Core/m68k/m68kops.c
            Core/m68k/m68kcpu.c
            Core/arm.c
            Core/dcsound.c
            Core/yam.c
            Core/satsound.c)

add_definitions(-DEMU_COMPILE -DEMU_LITTLE_ENDIAN -DUSE_M68K -DLSB_FIRST -DHAVE_MPROTECT)

set(CMAKE_POSITION_INDEPENDENT_CODE 1)
add_library(highly_theoretical STATIC ${SOURCES})
