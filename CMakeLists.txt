cmake_minimum_required(VERSION 2.6)

PROJECT(PN2)


# Use the include path and library for Qt that is used by VTK.
INCLUDE_DIRECTORIES(
  ${CMAKE_CURRENT_BINARY_DIR}
  ${CMAKE_CURRENT_SOURCE_DIR}
)

# Set your files and resources here  
SET(PNSrcs nodeinfo.cxx objectinfo.cxx parser.cxx mainActivityDetection.cxx)
SET(PNHeaders cellinfo.h input.h nodeinfo.h objectinfo.h ObjectSegment.h objSegmentUtil.h parser.h stobject1.h stRGB.h util.h interfaceutil.h)


SOURCE_GROUP("Resources" FILES
  ${PNResources}
  ${EXE_ICON}
)

SOURCE_GROUP("Generated" FILES
  ${UISrcs}
  ${MOCSrcs}
  ${ResourceSrcs}
  ${RCS_SOURCES}
)

ADD_DEFINITIONS(-DQT_GUI_LIBS -DQT_CORE_LIB -DQT3_SUPPORT)
SET_SOURCE_FILES_PROPERTIES(${PNSrcs} PROPERTIES)


ADD_EXECUTABLE( PN2 MACOSX_BUNDLE ${PNSrcs} ${PNResources} ${MOCSrcs} ${ResourceSrcs} )