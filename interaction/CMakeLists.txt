PROJECT(interaction)

INCLUDE_DIRECTORIES("${CMAKE_CURRENT_BINARY_DIR}")

SET(
	sources
	DraggableObject.h
	DraggablePoint.cpp DraggablePoint.h
	DraggableLineSegment.cpp DraggableLineSegment.h
	ObjectDragHandler.cpp ObjectDragHandler.h
	InteractionHandler.cpp InteractionHandler.h
	InteractionState.cpp InteractionState.h
	DragHandler.cpp DragHandler.h
	DragWatcher.cpp DragWatcher.h
	ZoomHandler.cpp ZoomHandler.h
	InteractiveXSpline.cpp InteractiveXSpline.h
)

ADD_LIBRARY(interaction STATIC ${sources})
TARGET_LINK_LIBRARIES(interaction PUBLIC Qt6::Widgets)