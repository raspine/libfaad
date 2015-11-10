cmake_minimum_required(VERSION 2.8)
project (libfaad2)
 
ADD_DEFINITIONS(-D_SCL_SECURE_NO_WARNINGS)

set(CMAKE_BUILD_TYPE Release)

set(PROJECT_MAIN_SRCS 
	${CMAKE_CURRENT_SOURCE_DIR}/bits.c
	${CMAKE_CURRENT_SOURCE_DIR}/cfft.c
	${CMAKE_CURRENT_SOURCE_DIR}/common.c
	${CMAKE_CURRENT_SOURCE_DIR}/decoder.c
	${CMAKE_CURRENT_SOURCE_DIR}/drc.c
	${CMAKE_CURRENT_SOURCE_DIR}/drm_dec.c
	${CMAKE_CURRENT_SOURCE_DIR}/error.c
	${CMAKE_CURRENT_SOURCE_DIR}/filtbank.c
	${CMAKE_CURRENT_SOURCE_DIR}/hcr.c
	${CMAKE_CURRENT_SOURCE_DIR}/huffman.c
	${CMAKE_CURRENT_SOURCE_DIR}/ic_predict.c
	${CMAKE_CURRENT_SOURCE_DIR}/lt_predict.c
	${CMAKE_CURRENT_SOURCE_DIR}/mdct.c
	${CMAKE_CURRENT_SOURCE_DIR}/mp4.c
	${CMAKE_CURRENT_SOURCE_DIR}/ms.c
	${CMAKE_CURRENT_SOURCE_DIR}/output.c
	${CMAKE_CURRENT_SOURCE_DIR}/pns.c
	${CMAKE_CURRENT_SOURCE_DIR}/ps_dec.c
	${CMAKE_CURRENT_SOURCE_DIR}/ps_syntax.c
	${CMAKE_CURRENT_SOURCE_DIR}/pulse.c
	${CMAKE_CURRENT_SOURCE_DIR}/rvlc.c
	${CMAKE_CURRENT_SOURCE_DIR}/sbr_dct.c
	${CMAKE_CURRENT_SOURCE_DIR}/sbr_dec.c
	${CMAKE_CURRENT_SOURCE_DIR}/sbr_hfadj.c
	${CMAKE_CURRENT_SOURCE_DIR}/sbr_hfgen.c
	${CMAKE_CURRENT_SOURCE_DIR}/sbr_huff.c
	${CMAKE_CURRENT_SOURCE_DIR}/sbr_qmf.c
	${CMAKE_CURRENT_SOURCE_DIR}/sbr_syntax.c
	${CMAKE_CURRENT_SOURCE_DIR}/sbr_tf_grid.c
	${CMAKE_CURRENT_SOURCE_DIR}/specrec.c
	${CMAKE_CURRENT_SOURCE_DIR}/ssr.c
	${CMAKE_CURRENT_SOURCE_DIR}/ssr_fb.c
	${CMAKE_CURRENT_SOURCE_DIR}/ssr_ipqf.c
	${CMAKE_CURRENT_SOURCE_DIR}/syntax.c
	${CMAKE_CURRENT_SOURCE_DIR}/tns.c
)

 
add_library(${PROJECT_NAME} STATIC ${PROJECT_MAIN_SRCS})

### OS specific stuff ###
#if(NOT WIN32)
	#install(TARGETS ${PROJECT_NAME} LIBRARY DESTINATION lib)
	#install(DIRECTORY ../include/ DESTINATION include/${PROJECT_NAME})
#endif()
#########################

# Post-build copy of lib binary to lib folder
#add_custom_command(TARGET logga POST_BUILD 
					#COMMAND "${CMAKE_COMMAND}" -E copy 
					#"$<TARGET_FILE:logga>"
					#"../../lib/$<TARGET_FILE_NAME:logga>" 
					#COMMENT "Copying to lib directory")
