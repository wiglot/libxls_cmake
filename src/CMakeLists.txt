
include_directories(${CMAKE_CURRENT_BINARY_DIR} ../ ../include)


########### next target ###############

set(xls2csv_SRCS xls2csv.c getopt.c)

add_executable(xls2csv ${xls2csv_SRCS})

target_link_libraries(xls2csv  xlsreader ${ICONV_LIBRARIES})

#install(TARGETS xls2csv )


########### next target ###############

set(xlsreader_LIB_SRCS xlstool.c ole.c xls.c)

add_library(xlsreader SHARED ${xlsreader_LIB_SRCS})

target_link_libraries(xlsreader ${ICONV_LIBRARIES})

#set_target_properties(xlsreader PROPERTIES VERSION 1.0.0 SOVERSION 1)
#install(TARGETS xlsreader )
install (TARGETS xlsreader
         RUNTIME DESTINATION bin
         LIBRARY DESTINATION lib
         ARCHIVE DESTINATION lib
)


########### install files ###############




#original Makefile.am contents follow:

#AM_CPPFLAGS = -I$(top_srcdir)/include -I$(top_builddir)/include
#
#bin_PROGRAMS = xls2csv
#
#lib_LTLIBRARIES = libxlsreader.la
#
#xls2csv_SOURCES =       \
#	xls2csv.c	\
#	getopt.c
#
#xls2csv_LDADD = libxlsreader.la
#
#libxlsreader_la_SOURCES =	\
#	xlstool.c	\
#	ole.c		\
#	xls.c
#
#libxlsreader_la_LDFLAGS = -version-info $(VERSION_INFO) $(LIBXLS_LIBS)
