PROJECT("Deskew Filter")

INCLUDE_DIRECTORIES(BEFORE "${CMAKE_CURRENT_BINARY_DIR}")

FILE(GLOB ui_files "ui/*.ui")

SET(
	sources
	ImageView.cpp ImageView.h
	Thumbnail.cpp Thumbnail.h
	Filter.cpp Filter.h
	OptionsWidget.cpp OptionsWidget.h
	Settings.cpp Settings.h
	Task.cpp Task.h
	CacheDrivenTask.cpp CacheDrivenTask.h
	Dependencies.cpp Dependencies.h
	Params.cpp Params.h
	ApplyDialog.cpp ApplyDialog.h
)

SET(CMAKE_AUTOUIC_SEARCH_PATHS ${CMAKE_CURRENT_SOURCE_DIR}/ui)
ADD_LIBRARY(deskew STATIC ${sources} ${ui_files})
TARGET_LINK_LIBRARIES(deskew PUBLIC Qt6::Widgets Qt6::Xml)
