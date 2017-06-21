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

cmake_minimum_required(VERSION 3.0)  

project(larsoftobj VERSION 1.21.00 )

# cetmodules contains our cmake modules
find_package(cetmodules REQUIRED)

include(CetCMakeEnv)
cet_cmake_env()

# larsoftobj bundle scripts
add_subdirectory(bundle)
# ups - table and config files
add_subdirectory(ups)

# packaging utility
include(UseCPack)
