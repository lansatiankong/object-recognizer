PROJECT( surf )

set(CMAKE_CXX_FLAGS "-g -Wall")

FIND_PACKAGE( OpenCV REQUIRED )
FIND_PACKAGE(Boost COMPONENTS filesystem system REQUIRED)
IF (Boost_FOUND)
    INCLUDE_DIRECTORIES(${Boost_INCLUDE_DIR})
    ADD_DEFINITIONS( "-DHAS_BOOST" )
ENDIF()
INCLUDE_DIRECTORIES(includes)

SET(EXECUTABLE_OUTPUT_PATH ${CMAKE_SOURCE_DIR}/bin)

ADD_SUBDIRECTORY(src)