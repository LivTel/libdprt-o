# $Header: /home/cjm/cvs/libdprt-o/test/Makefile,v 1.1 2011-11-23 11:09:39 cjm Exp $

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
	$(CC) -o $@ $(BINDIR)/dprt_test.o -L$(LT_LIB_HOME) -ldprt_ccs -ldprt_object -ldprt_jni_general $(TIMELIB) -lm -lc

$(BINDIR)/%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

docs: $(DOCS)

$(DOCS) : $(SRCS)
	-$(CDOC) -d $(DOCSDIR) -h $(INCDIR) $(DOCFLAGS) $(SRCS)

depend:
	makedepend -p$(BINDIR)/ -- $(CFLAGS) -- $(SRCS)

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
#
