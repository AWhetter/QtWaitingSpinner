cmake_minimum_required(VERSION 2.6)

project(QTSpinnerWidget)

set(SOURCES
	src/waitingspinnerwidget.cpp
	)

set(HEADERS
	src/waitingspinnerwidget.h
	)

find_package(Qt4 REQUIRED QtCore QtGui)
INCLUDE(${QT_USE_FILE})
qt4_wrap_cpp(HEADERS_MOC ${HEADERS})

include_directories(${CMAKE_CURRENT_BINARY_DIR})
add_definitions(-DQT_PLUGIN)
add_definitions(-DQT_SHARED)

add_library(${CMAKE_PROJECT_NAME} SHARED
	${SOURCES}
	${HEADERS_MOC}
	)
target_link_libraries(${CMAKE_PROJECT_NAME} ${QT_LIBRARIES})
