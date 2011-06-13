
include_directories(${KDE4_INCLUDES} ${KDE4_INCLUDE_DIR} ${QT_INCLUDES} )


########### next target ###############

set(test_SRCS test.c)

kde4_add_executable(test ${test_SRCS})

target_link_libraries(test ${KDE4_KDECORE_LIBS} xlsreader)


########### next target ###############

set(test2_SRCS test2.c)

kde4_add_executable(test2 ${test2_SRCS})

target_link_libraries(test2 ${KDE4_KDECORE_LIBS} xlsreader)


########### install files ###############




#original Makefile.am contents follow:

#AM_CPPFLAGS = -I$(top_srcdir)/include -I$(top_srcdir) -I../include
#
#noinst_PROGRAMS = test test2
#
#test_SOURCES = test.c
#test_LDADD = $(top_builddir)/src/libxlsreader.la
#
#test2_SOURCES = test2.c
#test2_LDADD = $(top_builddir)/src/libxlsreader.la
#
## Extra files to distribute
#EXTRA_DIST = files/test2.xls
