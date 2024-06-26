cmake_minimum_required(VERSION 3.16.3...3.19.7 FATAL_ERROR)

#-----------------------------------------------------------------------------
project(Scoliosis)

#-----------------------------------------------------------------------------
set(EXTENSION_HOMEPAGE "https://www.assembla.com/spaces/Scoliosis/wiki")
set(EXTENSION_CATEGORY "Quantification")
set(EXTENSION_CONTRIBUTORS "Franklin King (PerkLab, Queen's University), Tamas Ungi (PerkLab, Queen's University)")
set(EXTENSION_DESCRIPTION "Extensions pertaining to scoliosis analysis")
set(EXTENSION_ICONURL "https://www.slicer.org/slicerWiki/images/2/2b/ScoliosisLogo.png")
set(EXTENSION_SCREENSHOTURLS "https://www.slicer.org/slicerWiki/images/d/d1/ScoliosisScreenshot.png")
set(EXTENSION_STATUS "Experimental")
set(EXTENSION_DEPENDS "NA") # Specified as a space separated list or 'NA' if any

#-----------------------------------------------------------------------------
find_package(Slicer REQUIRED)
include(${Slicer_USE_FILE})

#-----------------------------------------------------------------------------
add_subdirectory(SpinalCurvatureMeasurement)
add_subdirectory(ScoliosisMonitoring)

#-----------------------------------------------------------------------------
INCLUDE(${Slicer_EXTENSION_CPACK})
