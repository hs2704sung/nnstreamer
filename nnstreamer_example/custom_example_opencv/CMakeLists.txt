pkg_check_modules(opencv_pkg REQUIRED opencv)

ADD_LIBRARY(nnstreamer_customfilter_opencv_scaler SHARED nnstreamer_customfilter_opencv_scaler.cc)
TARGET_LINK_LIBRARIES(nnstreamer_customfilter_opencv_scaler ${opencv_pkg_LIBRARIES} ${CUSTOMFILTERDEP})
TARGET_INCLUDE_DIRECTORIES(nnstreamer_customfilter_opencv_scaler PUBLIC ${opencv_pkg_INCLUDE_DIRS})

ADD_LIBRARY(nnstreamer_customfilter_opencv_average SHARED nnstreamer_customfilter_opencv_average.cc)
TARGET_LINK_LIBRARIES(nnstreamer_customfilter_opencv_average ${opencv_pkg_LIBRARIES} ${CUSTOMFILTERDEP})
TARGET_INCLUDE_DIRECTORIES(nnstreamer_customfilter_opencv_average PUBLIC ${opencv_pkg_INCLUDE_DIRS})

INSTALL(TARGETS nnstreamer_customfilter_opencv_scaler
	RUNTIME DESTINATION ${EXEC_PREFIX}
	LIBRARY DESTINATION ${LIB_INSTALL_DIR}
	ARCHIVE DESTINATION ${LIB_INSTALL_DIR}
)

INSTALL(TARGETS nnstreamer_customfilter_opencv_average
	RUNTIME DESTINATION ${EXEC_PREFIX}
	LIBRARY DESTINATION ${LIB_INSTALL_DIR}
	ARCHIVE DESTINATION ${LIB_INSTALL_DIR}
)
