cmake_minimum_required(VERSION 2.8)

project(spcconv C CXX)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

if(MSVC)
    add_definitions(-D_CRT_SECURE_NO_WARNINGS)

    option(STATIC_CRT "Use static CRT libraries" OFF)

    # Rewrite command line flags to use /MT if necessary
    if(STATIC_CRT)
        foreach(flag_var
                CMAKE_CXX_FLAGS CMAKE_CXX_FLAGS_DEBUG CMAKE_CXX_FLAGS_RELEASE
                CMAKE_CXX_FLAGS_MINSIZEREL CMAKE_CXX_FLAGS_RELWITHDEBINFO)
            if(${flag_var} MATCHES "/MD")
                string(REGEX REPLACE "/MD" "/MT" ${flag_var} "${${flag_var}}")
            endif(${flag_var} MATCHES "/MD")
        endforeach(flag_var)
    endif()

    # Allow for wildcards in command-line path arguments
    # http://msdn.microsoft.com/en-us/library/8bch7bkk.aspx
    set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} setargv.obj")
endif()


#============================================================================
# akaospc
#============================================================================

set(AKAOSPC_SRCS
    akaospc/src/akaospc.c
    akaospc/src/cioutil.c
    akaospc/src/libsmfc.c
    akaospc/src/libsmfcx.c
    akaospc/src/spcseq.c
)

set(AKAOSPC_HDRS
    akaospc/src/akaospc.h
    akaospc/src/cioutil.h
    akaospc/src/libsmfc.h
    akaospc/src/libsmfcx.h
    akaospc/src/spcseq.h
)

add_executable(akaospc ${AKAOSPC_SRCS} ${AKAOSPC_HDRS})

#============================================================================
# capspc
#============================================================================

set(CAPSPC_SRCS
    capspc/src/capspc.c
    capspc/src/cioutil.c
    capspc/src/libsmfc.c
    capspc/src/libsmfcx.c
    capspc/src/spcseq.c
)

set(CAPSPC_HDRS
    capspc/src/capspc.h
    capspc/src/cioutil.h
    capspc/src/libsmfc.h
    capspc/src/libsmfcx.h
    capspc/src/spcseq.h
)

add_executable(capspc ${CAPSPC_SRCS} ${CAPSPC_HDRS})

#============================================================================
# chunspc
#============================================================================

set(CHUNSPC_SRCS
    chunspc/src/chunspc.c
    chunspc/src/cioutil.c
    chunspc/src/libsmfc.c
    chunspc/src/libsmfcx.c
    chunspc/src/spcseq.c
)

set(CHUNSPC_HDRS
    chunspc/src/chunspc.h
    chunspc/src/cioutil.h
    chunspc/src/libsmfc.h
    chunspc/src/libsmfcx.h
    chunspc/src/spcseq.h
)

add_executable(chunspc ${CHUNSPC_SRCS} ${CHUNSPC_HDRS})

#============================================================================
# compspc
#============================================================================

set(COMPSPC_SRCS
    compspc/src/compspc.c
    compspc/src/cioutil.c
    compspc/src/libsmfc.c
    compspc/src/libsmfcx.c
    compspc/src/spcseq.c
)

set(COMPSPC_HDRS
    compspc/src/compspc.h
    compspc/src/cioutil.h
    compspc/src/libsmfc.h
    compspc/src/libsmfcx.h
    compspc/src/spcseq.h
)

add_executable(compspc ${COMPSPC_SRCS} ${COMPSPC_HDRS})

#============================================================================
# hbdqspc
#============================================================================

set(HBDQSPC_SRCS
    hbdqspc/src/hbdqspc.c
    hbdqspc/src/cioutil.c
    hbdqspc/src/libsmfc.c
    hbdqspc/src/libsmfcx.c
    hbdqspc/src/spcseq.c
)

set(HBDQSPC_HDRS
    hbdqspc/src/hbdqspc.h
    hbdqspc/src/cioutil.h
    hbdqspc/src/libsmfc.h
    hbdqspc/src/libsmfcx.h
    hbdqspc/src/spcseq.h
)

add_executable(hbdqspc ${HBDQSPC_SRCS} ${HBDQSPC_HDRS})

#============================================================================
# hudspc
#============================================================================

set(HUDSPC_SRCS
    hudspc/src/hudspc.c
    hudspc/src/cioutil.c
    hudspc/src/libsmfc.c
    hudspc/src/libsmfcx.c
    hudspc/src/spcseq.c
)

set(HUDSPC_HDRS
    hudspc/src/hudspc.h
    hudspc/src/cioutil.h
    hudspc/src/libsmfc.h
    hudspc/src/libsmfcx.h
    hudspc/src/spcseq.h
)

add_executable(hudspc ${HUDSPC_SRCS} ${HUDSPC_HDRS})

#============================================================================
# konspc
#============================================================================

set(KONSPC_SRCS
    konspc/src/konspc.c
    konspc/src/cioutil.c
    konspc/src/libsmfc.c
    konspc/src/libsmfcx.c
    konspc/src/spcseq.c
)

set(KONSPC_HDRS
    konspc/src/konspc.h
    konspc/src/cioutil.h
    konspc/src/libsmfc.h
    konspc/src/libsmfcx.h
    konspc/src/spcseq.h
)

add_executable(konspc ${KONSPC_SRCS} ${KONSPC_HDRS})

#============================================================================
# mintspc
#============================================================================

set(MINTSPC_SRCS
    mintspc/src/mintspc.c
    mintspc/src/cioutil.c
    mintspc/src/libsmfc.c
    mintspc/src/libsmfcx.c
    mintspc/src/spcseq.c
)

set(MINTSPC_HDRS
    mintspc/src/mintspc.h
    mintspc/src/cioutil.h
    mintspc/src/libsmfc.h
    mintspc/src/libsmfcx.h
    mintspc/src/spcseq.h
)

add_executable(mintspc ${MINTSPC_SRCS} ${MINTSPC_HDRS})

#============================================================================
# nintspc
#============================================================================

set(NINTSPC_SRCS
    nintspc/src/nintspc.c
    nintspc/src/cioutil.c
    nintspc/src/libsmfc.c
    nintspc/src/libsmfcx.c
    nintspc/src/spcseq.c
)

set(NINTSPC_HDRS
    nintspc/src/nintspc.h
    nintspc/src/cioutil.h
    nintspc/src/libsmfc.h
    nintspc/src/libsmfcx.h
    nintspc/src/spcseq.h
)

add_executable(nintspc ${NINTSPC_SRCS} ${NINTSPC_HDRS})

#============================================================================
# pboxspc
#============================================================================

set(PBOXSPC_SRCS
    pboxspc/src/pboxspc.c
    pboxspc/src/cioutil.c
    pboxspc/src/libsmfc.c
    pboxspc/src/libsmfcx.c
    pboxspc/src/spcseq.c
)

set(PBOXSPC_HDRS
    pboxspc/src/pboxspc.h
    pboxspc/src/cioutil.h
    pboxspc/src/libsmfc.h
    pboxspc/src/libsmfcx.h
    pboxspc/src/spcseq.h
)

add_executable(pboxspc ${PBOXSPC_SRCS} ${PBOXSPC_HDRS})

#============================================================================
# rarespc
#============================================================================

set(RARESPC_SRCS
    rarespc/src/rarespc.c
    rarespc/src/cioutil.c
    rarespc/src/libsmfc.c
    rarespc/src/libsmfcx.c
    rarespc/src/spcseq.c
)

set(RARESPC_HDRS
    rarespc/src/rarespc.h
    rarespc/src/cioutil.h
    rarespc/src/libsmfc.h
    rarespc/src/libsmfcx.h
    rarespc/src/spcseq.h
)

add_executable(rarespc ${RARESPC_SRCS} ${RARESPC_HDRS})

#============================================================================
# softcspc
#============================================================================

set(SOFTCSPC_SRCS
    softcspc/src/softcspc.c
    softcspc/src/cioutil.c
    softcspc/src/libsmfc.c
    softcspc/src/libsmfcx.c
    softcspc/src/spcseq.c
)

set(SOFTCSPC_HDRS
    softcspc/src/softcspc.h
    softcspc/src/cioutil.h
    softcspc/src/libsmfc.h
    softcspc/src/libsmfcx.h
    softcspc/src/spcseq.h
)

add_executable(softcspc ${SOFTCSPC_SRCS} ${SOFTCSPC_HDRS})

#============================================================================
# suzuhspc
#============================================================================

set(SUZUHSPC_SRCS
    suzuhspc/src/suzuhspc.c
    suzuhspc/src/cioutil.c
    suzuhspc/src/libsmfc.c
    suzuhspc/src/libsmfcx.c
    suzuhspc/src/spcseq.c
)

set(SUZUHSPC_HDRS
    suzuhspc/src/suzuhspc.h
    suzuhspc/src/cioutil.h
    suzuhspc/src/libsmfc.h
    suzuhspc/src/libsmfcx.h
    suzuhspc/src/spcseq.h
)

add_executable(suzuhspc ${SUZUHSPC_SRCS} ${SUZUHSPC_HDRS})

#============================================================================
# wgpspc
#============================================================================

set(WGPSPC_SRCS
    wgpspc/src/wgpspc.c
    wgpspc/src/cioutil.c
    wgpspc/src/libsmfc.c
    wgpspc/src/libsmfcx.c
    wgpspc/src/spcseq.c
)

set(WGPSPC_HDRS
    wgpspc/src/wgpspc.h
    wgpspc/src/cioutil.h
    wgpspc/src/libsmfc.h
    wgpspc/src/libsmfcx.h
    wgpspc/src/spcseq.h
)

add_executable(wgpspc ${WGPSPC_SRCS} ${WGPSPC_HDRS})
