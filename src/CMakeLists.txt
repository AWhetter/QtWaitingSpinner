set(QtWaitingSpinnerWidget_SRC
	waitingspinnerwidget.cpp
	)

set(QtWaitingSpinnerWidget_HEADERS
	waitingspinnerwidget.h
	)

find_package(Qt4 REQUIRED QtCore QtGui)
INCLUDE(${QT_USE_FILE})
qt4_wrap_cpp(QtWaitingSpinnerWidget_HEADERS_MOC ${QtWaitingSpinnerWidget_HEADERS})

include_directories(${CMAKE_CURRENT_BINARY_DIR})
add_definitions(-DQT_PLUGIN)
add_definitions(-DQT_SHARED)

add_library(${CMAKE_PROJECT_NAME} SHARED
	${QtWaitingSpinnerWidget_SRC}
	${QtWaitingSpinnerWidget_HEADERS_MOC}
	)
target_link_libraries(${CMAKE_PROJECT_NAME} ${QT_LIBRARIES})
