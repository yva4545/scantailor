PROJECT("Select Content Filter")

INCLUDE_DIRECTORIES(BEFORE "${CMAKE_CURRENT_BINARY_DIR}")

FILE(GLOB ui_files "ui/*.ui")

SET(
	sources
	ImageView.cpp ImageView.h
	Filter.cpp Filter.h
	OptionsWidget.cpp OptionsWidget.h
	ApplyDialog.cpp ApplyDialog.h
	ContentBoxFinder.cpp ContentBoxFinder.h
	Task.cpp Task.h
	CacheDrivenTask.cpp CacheDrivenTask.h
	Dependencies.cpp Dependencies.h
	Params.cpp Params.h
	Settings.cpp Settings.h
	Thumbnail.cpp Thumbnail.h
	PhysSizeCalc.cpp PhysSizeCalc.h
	OrderByWidthProvider.cpp OrderByWidthProvider.h
	OrderByHeightProvider.cpp OrderByHeightProvider.h
)

SET(CMAKE_AUTOUIC_SEARCH_PATHS ${CMAKE_CURRENT_SOURCE_DIR}/ui)
ADD_LIBRARY(select_content STATIC ${sources} ${ui_files})
TARGET_LINK_LIBRARIES(select_content PUBLIC Qt6::Widgets)
