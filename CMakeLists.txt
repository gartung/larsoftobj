# ======================================================================
#  larsoftobj main build file
#
#  cd .../path/to/build/directory
#  source .../path/to/larsoftobj/ups/setup_for_development <-d|-p>
#  cmake [-DCMAKE_INSTALL_PREFIX=/install/path]
#        -DCMAKE_BUILD_TYPE=$CETPKG_TYPE
#        $CETPKG_SOURCE
#  make
#  make test
#  make install
#  make package (builds distribution tarfile)
# ======================================================================
# LArSoftObj is an empty product
# It sets up the larsoftobj ups products (lardataobj, larcoreobj)
# ======================================================================


# use cmake 3.12 or later
cmake_minimum_required (VERSION 3.12)

project(larsoftobj VERSION 08.26.02 LANGUAGES CXX)

find_package(cetmodules)
include(CetCMakeEnv)
cet_cmake_env()

find_package(nusimdata REQUIRED)
find_package(lardataalg REQUIRED)
find_package(lardataobj REQUIRED)
find_package(larcorealg REQUIRED)
find_package(larcoreobj REQUIRED)

# larsoftobj bundle scripts
add_subdirectory(bundle)
# ups - table and config files
#add_subdirectory(ups)
add_subdirectory(cmakeConfig)
# packaging utility
#include(UseCPack)
