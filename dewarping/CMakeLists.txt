PROJECT("Dewarping library")

SET(
	sources
	Curve.cpp Curve.h
	DistortionModel.cpp DistortionModel.h
	DistortionModelBuilder.cpp DistortionModelBuilder.h
	DetectVertContentBounds.cpp DetectVertContentBounds.h
	TowardsLineTracer.cpp TowardsLineTracer.h
	TextLineTracer.cpp TextLineTracer.h
	TextLineRefiner.cpp TextLineRefiner.h
	TopBottomEdgeTracer.cpp TopBottomEdgeTracer.h
	CylindricalSurfaceDewarper.cpp CylindricalSurfaceDewarper.h
	DewarpingPointMapper.cpp DewarpingPointMapper.h
	RasterDewarper.cpp RasterDewarper.h
)
SOURCE_GROUP("Sources" FILES ${sources})

ADD_LIBRARY(dewarping STATIC ${sources})
TARGET_LINK_LIBRARIES(dewarping PUBLIC Qt6::Core Qt6::Xml Qt6::Gui)
TARGET_INCLUDE_DIRECTORIES(dewarping PUBLIC
    ${CMAKE_SOURCE_DIR}
    ${CMAKE_BINARY_DIR}
    ${Qt6_PRIVATE_INCLUDE_DIRS}
    ${Qt6Widgets_INCLUDE_DIRS}
    ${Qt6Core_INCLUDE_DIRS}
    ${Qt6Gui_INCLUDE_DIRS}
    ${Qt6Xml_INCLUDE_DIRS}
)
