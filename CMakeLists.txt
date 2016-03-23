#
# BeagleBone Test
# 
#
# This is the master makefile for the entire project.
#
# Author:
#     Jeffrey Polochak
#

#
# Make sure there is a reasonable version of CMAKE installed.
#

cmake_minimum_required(VERSION 2.6)

#
# Define the base solution name.
#

project("BeagleBone_Test")

#
# Keep track of the base directory for the rest of the system.
#

set(BASE_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})

#
# This is where code is released to. This directory forms the
# final "installation", allowing you to copy one directory to
# a remote machine to avoid publishing source code.
#
if(${CMAKE_SYSTEM_NAME} MATCHES "Windows")
    set(RELEASE_DIRECTORY ${BASE_DIRECTORY}/release/build)
else()
    set(RELEASE_DIRECTORY ${BASE_DIRECTORY}/release)
endif()

#
# Install to the target directory.
#

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${RELEASE_DIRECTORY})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${RELEASE_DIRECTORY})
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${RELEASE_DIRECTORY})
