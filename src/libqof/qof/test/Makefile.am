# A template Makefile.am for GLib g_test-based test directories.
# Copyright 2011 John Ralls <jralls@ceridwen.us>

include $(top_srcdir)/test-templates/Makefile.decl


#You will only need one of these: It points to the module directory
#after $(top_srcdir) or $(top_builddir):
MODULEPATH = src/libqof/qof

test_qof_SOURCES = \
        test-gnc-date.c \
        test-qof.c \
        test-qofbook.c \
        test-qofinstance.cpp \
        test-qofobject.c \
        test-qof-string-cache.c \
        ${top_srcdir}/src/test-core/unittest-support.c

test_qof_HEADERS = \
        $(top_srcdir)/${MODULEPATH}/qofbook.h \
        $(top_srcdir)/${MODULEPATH}/qofinstance.h \
        $(top_srcdir)/${MODULEPATH}/kvp_frame.hpp \
        $(top_srcdir)/${MODULEPATH}/qofobject.h \
        $(top_srcdir)/${MODULEPATH}/qofsession.h \
        $(top_srcdir)/src/test-core/unittest-support.h

test_numeric_SOURCES = \
        ${top_srcdir}/src/engine/cashobjects.c \
        ${top_srcdir}/src/test-core/test-stuff.c \
        ${top_srcdir}/src/engine/test-core/test-engine-stuff.cpp \
        ${top_srcdir}/${MODULEPATH}/gnc-numeric.cpp \
        ${top_srcdir}/${MODULEPATH}/gnc-rational.cpp \
        ${top_srcdir}/${MODULEPATH}/gnc-int128.cpp \
        ${top_srcdir}/${MODULEPATH}/test/test-numeric.cpp

test_numeric_CPPFLAGS = \
       -I${top_srcdir}/src/engine \
       -I${top_srcdir}/src/test-core \
       -I${top_srcdir}/src/engine/test-core \
       -I${top_srcdir}/src \
       -I${top_srcdir}/${MODULEPATH} \
       ${BOOST_CPPFLAGS} \
       ${GLIB_CFLAGS}

test_numeric_LDADD = \
      ${top_builddir}/src/engine/libgncmod-engine.la \
      ${top_builddir}/${MODULEPATH}/libgnc-qof.la \
      ${BOOST_LDFLAGS} -lboost_regex \
      ${GLIB_LIBS}

check_PROGRAMS = \
  test-numeric \
  test-qof

TESTS = ${check_PROGRAMS}

test_gnc_guid_SOURCES = \
        $(top_srcdir)/$(MODULEPATH)/guid.cpp \
        test-gnc-guid.cpp
test_gnc_guid_LDADD = \
        $(top_builddir)/$(MODULEPATH)/libgnc-qof.la \
        $(GLIB_LIBS) \
        $(GTEST_LIBS) \
        $(BOOST_LDFLAGS)
if !GOOGLE_TEST_LIBS
nodist_test_gnc_guid_SOURCES = \
        ${GTEST_SRC}/src/gtest_main.cc
endif

test_gnc_guid_CPPFLAGS = \
    -I$(GTEST_HEADERS) \
    -I$(top_srcdir)/$(MODULEPATH) \
    $(GLIB_CFLAGS) \
    $(BOOST_CPPFLAGS)

check_PROGRAMS += test-gnc-guid

test_kvp_value_SOURCES = \
    $(top_srcdir)/$(MODULEPATH)/kvp-value.cpp \
    test-kvp-value.cpp \
    test-kvp-frame.cpp
test_kvp_value_LDADD = \
        $(top_builddir)/$(MODULEPATH)/libgnc-qof.la \
        $(GLIB_LIBS) \
        $(GTEST_LIBS) \
        $(BOOST_LDFLAGS)

if !GOOGLE_TEST_LIBS
nodist_test_kvp_value_SOURCES = \
        ${GTEST_SRC}/src/gtest_main.cc
endif

test_kvp_value_CPPFLAGS = \
    -I$(GTEST_HEADERS) \
    -I$(top_srcdir)/$(MODULEPATH) \
    $(GLIB_CFLAGS) \
    $(BOOST_CPPFLAGS)

check_PROGRAMS += test-kvp-value

test_qofsession_SOURCES = \
        $(top_srcdir)/$(MODULEPATH)/qofsession.cpp \
        test-qofsession.cpp
test_qofsession_LDADD = \
        $(top_builddir)/$(MODULEPATH)/libgnc-qof.la \
        $(GLIB_LIBS) \
        $(GTEST_LIBS) \
        $(BOOST_LDFLAGS) -lboost_regex

if !GOOGLE_TEST_LIBS
nodist_test_qofsession_SOURCES = \
        ${GTEST_SRC}/src/gtest_main.cc
endif

test_qofsession_CPPFLAGS = \
        -I$(GTEST_HEADERS) \
        -I$(top_srcdir)/$(MODULEPATH) \
        $(GLIB_CFLAGS) \
        $(BOOST_CPPFLAGS)

check_PROGRAMS += test-qofsession

test_gnc_int128_SOURCES = \
        $(top_srcdir)/${MODULEPATH}/gnc-int128.cpp \
        gtest-gnc-int128.cpp
test_gnc_int128_CPPFLAGS = -I${GTEST_HEADERS}

test_gnc_int128_LDADD = ${GTEST_LIBS}
if !GOOGLE_TEST_LIBS
nodist_test_gnc_int128_SOURCES = \
        ${GTEST_SRC}/src/gtest_main.cc
endif
check_PROGRAMS += test-gnc-int128

test_gnc_rational_SOURCES = \
        $(top_srcdir)/${MODULEPATH}/gnc-rational.cpp \
        $(top_srcdir)/${MODULEPATH}/gnc-numeric.cpp \
        $(top_srcdir)/${MODULEPATH}/gnc-int128.cpp \
        $(top_srcdir)/$(MODULEPATH)/gnc-datetime.cpp \
        $(top_srcdir)/$(MODULEPATH)/gnc-timezone.cpp \
        $(top_srcdir)/$(MODULEPATH)/gnc-date.cpp \
        $(top_srcdir)/${MODULEPATH}/qoflog.cpp \
        gtest-gnc-rational.cpp

test_gnc_rational_CPPFLAGS = \
        -I${top_srcdir}/src \
        -I${top_srcdir}/src/libqof/qof \
        -I${GTEST_HEADERS} \
        ${BOOST_CPPFLAGS} \
        ${GLIB_CFLAGS}

test_gnc_rational_LDADD = \
        ${GTEST_LIBS} \
        ${BOOST_LDFLAGS} -lboost_regex \
        ${GLIB_LIBS}

if !GOOGLE_TEST_LIBS
nodist_test_gnc_rational_SOURCES = \
        ${GTEST_SRC}/src/gtest_main.cc
endif
check_PROGRAMS += test-gnc-rational
check_PROGRAMS += test-gnc-int128

test_gnc_numeric_SOURCES = \
        $(top_srcdir)/${MODULEPATH}/gnc-rational.cpp \
        $(top_srcdir)/${MODULEPATH}/gnc-int128.cpp \
        $(top_srcdir)/${MODULEPATH}/gnc-numeric.cpp \
        $(top_srcdir)/$(MODULEPATH)/gnc-datetime.cpp \
        $(top_srcdir)/$(MODULEPATH)/gnc-timezone.cpp \
        $(top_srcdir)/$(MODULEPATH)/gnc-date.cpp \
        $(top_srcdir)/${MODULEPATH}/qoflog.cpp \
        gtest-gnc-numeric.cpp
test_gnc_numeric_CPPFLAGS = \
        -I${top_srcdir}/src \
        -I${top_srcdir}/src/libqof/qof \
        -I${GTEST_HEADERS} \
        ${BOOST_CPPFLAGS} \
        ${GLIB_CFLAGS}

test_gnc_numeric_LDADD = \
        ${GTEST_LIBS} \
        ${BOOST_LDFLAGS} -lboost_regex \
        ${GLIB_LIBS}
if !GOOGLE_TEST_LIBS
nodist_test_gnc_numeric_SOURCES = \
        ${GTEST_SRC}/src/gtest_main.cc
endif
check_PROGRAMS += test-gnc-numeric

test_gnc_timezone_SOURCES = \
        $(top_srcdir)/${MODULEPATH}/gnc-timezone.cpp \
        gtest-gnc-timezone.cpp

test_gnc_timezone_CPPFLAGS = \
        -I${GTEST_HEADERS} \
        -I$(top_srcdir)/$(MODULEPATH) \
        -I${top_srcdir}/src \
        $(GLIB_CFLAGS) \
        $(BOOST_CPPFLAGS)

test_gnc_timezone_LDADD = \
        ${top_builddir}/${MODULEPATH}/libgnc-qof.la \
        $(GLIB_LIBS) \
        $(GTEST_LIBS)
if !GOOGLE_TEST_LIBS
nodist_test_gnc_timezone_SOURCES = \
        ${GTEST_SRC}/src/gtest_main.cc
endif
check_PROGRAMS += test-gnc-timezone

test_gnc_datetime_SOURCES = \
        $(top_srcdir)/$(MODULEPATH)/gnc-datetime.cpp \
        $(top_srcdir)/$(MODULEPATH)/gnc-timezone.cpp \
        gtest-gnc-datetime.cpp
test_gnc_datetime_CPPFLAGS =\
        -I$(GTEST_HEADERS) \
        -I$(top_srcdir)/$(MODULEPATH) \
        -I$(top_srcdir)/src \
        $(GLIB_CFLAGS) \
        $(BOOST_CPPFLAGS)

test_gnc_datetime_LDADD = \
        -lboost_date_time \
        ${top_builddir}/${MODULEPATH}/libgnc-qof.la \
        $(GLIB_LIBS) \
        $(GTEST_LIBS)
if !GOOGLE_TEST_LIBS
nodist_test_gnc_datetime_SOURCES = \
        $(GTEST_SRC)/src/gtest_main.cc
endif
check_PROGRAMS += test-gnc-datetime


test_qofdir = ${GNC_LIBEXECDIR}/${MODULEPATH}/test

#The tests might require more libraries, but try to keep them
#as independent as possible.
test_qof_LDADD = \
        ${top_builddir}/${MODULEPATH}/libgnc-qof.la \
        $(GLIB_LIBS)

test_qof_CPPFLAGS = \
        ${DEFAULT_INCLUDES} \
        -I$(top_srcdir)/${MODULEPATH} \
        -I$(top_srcdir)/src/test-core \
        -DTESTPROG=test_qof \
        -I$(top_srcdir)/lib/libc \
        ${GLIB_CFLAGS}
