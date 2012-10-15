# $Header: /home/cjm/cvs/libdprt-o/test/Makefile,v 1.2 2012-10-15 11:23:16 cjm Exp $

include	../../../Makefile.common
include ../../Makefile.common
include ../Makefile.common

LIBNAME		= $(LIBDPRT_HOME)_$(O_HOME)
INCDIR 		= $(LIBDPRT_O_SRC_HOME)/include
DOCSDIR 	= $(LIBDPRT_O_DOC_HOME)/test
DOCFLAGS 	= -static
BINDIR		= $(LIBDPRT_O_BIN_HOME)/test/${HOSTTYPE}
OBJECT_CFLAGS	= $(LIBDPRT_SRC_HOME)/object/include
# log_udp library (log_udp.h is included for verbosity settings)
LOG_UDP_HOME	= log_udp
LOG_UDP_SRC_HOME= $(LT_SRC_HOME)/$(LOG_UDP_HOME)
LOG_UDP_CFLAGS	= -I$(LOG_UDP_SRC_HOME)/include
CFLAGS 		= -g -I$(INCDIR) -I$(JNIINCDIR) -I$(JNIMDINCDIR) -I$(JNIGENERALINCDIR) -I$(OBJECT_CFLAGS) \
		$(LOG_UDP_CFLAGS)

SRCS 		= dprt_test.c
OBJS 		= $(SRCS:%.c=$(BINDIR)/%.o)
DOCS 		= $(SRCS:%.c=$(DOCSDIR)/%.html)

top: ${BINDIR}/dprt_test docs

${BINDIR}/dprt_test: $(BINDIR)/dprt_test.o $(LT_LIB_HOME)/$(LIBNAME).so
	$(CC) -o $@ $(BINDIR)/dprt_test.o -L$(LT_LIB_HOME) -ldprt_o -ldprt_object -ldprt_jni_general $(TIMELIB) -lm -lc

$(BINDIR)/%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

docs: $(DOCS)

$(DOCS) : $(SRCS)
	-$(CDOC) -d $(DOCSDIR) -h $(INCDIR) $(DOCFLAGS) $(SRCS)

depend:
	makedepend $(MAKEDEPENDFLAGS) -p$(BINDIR)/ -- $(CFLAGS) -- $(SRCS)

clean:
	-$(RM) $(RM_OPTIONS) ${BINDIR}/dprt_test $(OBJS) $(TIDY_OPTIONS)

tidy:
	-$(RM) $(RM_OPTIONS) $(TIDY_OPTIONS)

backup: tidy
	-$(RM) $(RM_OPTIONS) $(LIBDPRT_BIN_HOME)/test/dprt_test

checkin:
	-$(CI) $(CI_OPTIONS) $(SRCS)

checkout:
	$(CO) $(CO_OPTIONS) $(SRCS)

#
# $Log: not supported by cvs2svn $
# Revision 1.1  2011/11/23 11:09:39  cjm
# Initial revision
#
#
# DO NOT DELETE

/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/stdio.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/features.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/sys/cdefs.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/bits/wordsize.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/gnu/stubs.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/gnu/stubs-32.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/bits/types.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/bits/typesizes.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/libio.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/_G_config.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/wchar.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/bits/wchar.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/gconv.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/bits/stdio_lim.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/bits/sys_errlist.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/stdlib.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/sys/types.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/time.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/endian.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/bits/endian.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/sys/select.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/bits/select.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/bits/sigset.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/bits/time.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/sys/sysmacros.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/bits/pthreadtypes.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/alloca.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/include/strings.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /home/dev/src/libdprt/o/include/dprt.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /home/dev/src/libdprt/jni_general/include/dprt_jni_general.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/java/jdk1.6.0_07/include/jni.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /usr/java/jdk1.6.0_07/include/linux/jni_md.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /home/dev/src/libdprt/object/include/object.h
/home/dev/bin/libdprt/o/test/i386-linux/dprt_test.o: /home/dev/src/log_udp/include/log_udp.h
