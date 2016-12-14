# Dark Adventure project
# Author : Aredhele, Exidhor
# Date   : 2016-12-14
CMAKE_MINIMUM_REQUIRED(VERSION 3.1)

# Add dll export
ADD_DEFINITIONS(-D ENGINE_IMPORTS)

# Creating the executable target
ADD_EXECUTABLE(BUILD_EXE TestEngine.cpp)

# Platform specific linkage
IF(PLATFORM_WINDOWS)
    # Linking all static libraries for windows
    TARGET_LINK_LIBRARIES(BUILD_EXE
            ${SFML_DEPENDENCIES}
            ${WINDOWS_DEPENDENCIES}
            ${CMAKE_SOURCE_DIR}/Bin/libDarkAdventure.dll.a)

ELSEIF(PLATFORM_UNIX)
    # Linking all static libraries for windows
    TARGET_LINK_LIBRARIES(BUILD_EXE
            ${SFML_DEPENDENCIES}
            ${UNIX_DEPENDENCIES})

ENDIF()
