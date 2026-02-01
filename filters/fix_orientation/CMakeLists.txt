PROJECT("Fix Orientation Filter")

INCLUDE_DIRECTORIES(BEFORE "${CMAKE_CURRENT_BINARY_DIR}")

FILE(GLOB ui_files "ui/*.ui")

SET(
	sources
	ImageView.cpp ImageView.h
	Filter.cpp Filter.h
	OptionsWidget.cpp OptionsWidget.h
	ApplyDialog.cpp ApplyDialog.h
	Settings.cpp Settings.h
	Task.cpp Task.h
	CacheDrivenTask.cpp CacheDrivenTask.h
)

SET(CMAKE_AUTOUIC_SEARCH_PATHS ${CMAKE_CURRENT_SOURCE_DIR}/ui)
ADD_LIBRARY(fix_orientation STATIC ${sources} ${ui_files})
TARGET_LINK_LIBRARIES(fix_orientation PUBLIC Qt6::Widgets Qt6::Xml)