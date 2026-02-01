PROJECT("Page Layout Filter")

INCLUDE_DIRECTORIES(BEFORE "${CMAKE_CURRENT_BINARY_DIR}")

FILE(GLOB ui_files "ui/*.ui")

SET(
	sources
	Utils.cpp Utils.h
	ImageView.cpp ImageView.h
	Filter.cpp Filter.h
	OptionsWidget.cpp OptionsWidget.h
	Task.cpp Task.h
	CacheDrivenTask.cpp CacheDrivenTask.h
	Params.cpp Params.h
	Settings.cpp Settings.h
	Thumbnail.cpp Thumbnail.h
	ApplyDialog.cpp ApplyDialog.h
	Alignment.cpp Alignment.h
	OrderByWidthProvider.cpp OrderByWidthProvider.h
	OrderByHeightProvider.cpp OrderByHeightProvider.h
)

SET(CMAKE_AUTOUIC_SEARCH_PATHS ${CMAKE_CURRENT_SOURCE_DIR}/ui)
ADD_LIBRARY(page_layout STATIC ${sources} ${ui_files})
TARGET_LINK_LIBRARIES(page_layout PUBLIC Qt6::Widgets)