ADD_LIBRARY(dummyLSTM SHARED dummy_LSTM.c)

TARGET_LINK_LIBRARIES(dummyLSTM ${CUSTOMFILTERDEP})

INSTALL(TARGETS dummyLSTM
	RUNTIME DESTINATION ${EXEC_PREFIX}
	LIBRARY DESTINATION ${LIB_INSTALL_DIR}
	ARCHIVE DESTINATION ${LIB_INSTALL_DIR}
	)
