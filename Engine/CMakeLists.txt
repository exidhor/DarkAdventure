# Dark Adventure project
# Author : Aredhele, Exidhor
# Date   : 2016-12-14
CMAKE_MINIMUM_REQUIRED(VERSION 3.1)

# Add dll export
ADD_DEFINITIONS(-D ENGINE_EXPORTS)

# Getting sources
FILE(GLOB_RECURSE HEADER_FILES include/*)

# Getting sources
FILE(GLOB_RECURSE SOURCE_FILES source/*)

# Creating the executable target
ADD_LIBRARY(${TARGET_COMPILE} SHARED ${SOURCE_FILES})

# Platform specific linkage
IF(PLATFORM_WINDOWS)
    # Linking all static libraries for windows
    TARGET_LINK_LIBRARIES(${TARGET_COMPILE}
            ${SFML_DEPENDENCIES}
            ${WINDOWS_DEPENDENCIES})

ELSEIF(PLATFORM_UNIX)
    # Linking all static libraries for windows
    TARGET_LINK_LIBRARIES(${TARGET_COMPILE}
            ${SFML_DEPENDENCIES}
            ${UNIX_DEPENDENCIES})

ENDIF()
