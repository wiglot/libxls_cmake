project (libxsl)

cmake_minimum_required(VERSION 2.6)
set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake/modules ${CMAKE_MODULE_PATH})

find_package(ICONV)

#need to create the config file.

enable_testing()

add_subdirectory(include)
add_subdirectory(src)
add_subdirectory(test)


########### install files ###############




#original Makefile.am contents follow:

### Process this file with automake to create Makefile.in.
#AUTOMAKE_OPTIONS = foreign dist-zip
#SUBDIRS = include src test
#
## Extra files to distribute
#EXTRA_DIST = doc
#
#dist-hook:
#	rm -rf `find $(distdir)/doc -name CVS`
#
