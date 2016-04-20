cmake_minimum_required(VERSION 2.9)

project(hu_vision)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

find_package(PkgConfig)
pkg_check_modules(OPENCV opencv)
link_directories(${OPENCV_LIBRARY_DIRS})
include_directories(${OPENCV_INCLUDE_DIRS})

set(SOURCES
		"DefaultExtraction.cpp"
		"DefaultLocalization.cpp"
		"DefaultPreProcessing.cpp"
		"DLLExecution.cpp"
		"Feature.cpp"
		"FeatureMap.cpp"
		"GrayscaleAlgorithm.cpp"
		"HereBeDragons.cpp"
		"Image.cpp"
		"ImageFactory.cpp"
		"ImageIO.cpp"
		"IntensityImage.cpp"
		"IntensityImagePrivate.cpp"
		"IntensityImageStudent.cpp"
		"Main.cpp"
		"PostProcessing.cpp"
		"Representation.cpp"
		"RGBImage.cpp"
		"RGBImagePrivate.cpp"
		"RGBImageStudent.cpp"
		"SonnetXVIII.cpp"
		"StudentExtraction.cpp"
		"StudentLocalization.cpp"
		"StudentPreProcessing.cpp")
list(REMOVE_ITEM SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/export.cpp")
add_executable(hu_vision ${SOURCES})
target_link_libraries(hu_vision ${OPENCV_LIBRARIES})