

ADD_LIBRARY (attentionbank
	AtomBins.cc
	AttentionBank.cc
	AVUtils.cc
	ImportanceIndex.cc
	StochasticImportanceDiffusion.cc
)

TARGET_LINK_LIBRARIES(attentionbank
	${NO_AS_NEEDED}
	atombase
	truthvalue
	${COGUTIL_LIBRARY}
)

IF(CMAKE_BUILD_TYPE MATCHES DEBUG)
    ADD_DEFINITIONS(-DECAN_EXPERIMENT)
ENDIF(CMAKE_BUILD_TYPE MATCHES DEBUG)

INSTALL (TARGETS attentionbank
	DESTINATION "lib${LIB_DIR_SUFFIX}/opencog"
)

INSTALL (FILES
	AtomBins.h
	AttentionBank.h
	AVUtils.h
	ImportanceIndex.h
	StochasticImportanceDiffusion.h
	DESTINATION "include/opencog/attentionbank"
)
