# $Header: /home/cjm/cvs/libdprt-o/c/Makefile,v 1.2 2012-10-15 11:24:46 cjm Exp $

include	../../../Makefile.common
include	../../Makefile.common
include	../Makefile.common

LIBNAME		= $(LIBDPRT_HOME)_$(O_HOME)
INCDIR 		= $(LIBDPRT_O_SRC_HOME)/include
CCDIMAGERINCDIR	= $(LIBDPRT_SRC_HOME)/ccd_imager
OBJECTINCDIR	= $(LIBDPRT_SRC_HOME)/object/include
DOCSDIR 	= $(LIBDPRT_O_DOC_HOME)/cdocs
BINDIR		= $(LIBDPRT_O_BIN_HOME)/c/$(HOSTTYPE)
CFLAGS 		= -g $(CCHECKFLAG) -I$(INCDIR) -I$(CFITSIOINCDIR) -I$(JNIINCDIR) -I$(JNIMDINCDIR) \
		-I$(JNIGENERALINCDIR) -I$(CCDIMAGERINCDIR) -I$(OBJECTINCDIR) -L$(LT_LIB_HOME)
LINTFLAGS 	= -I$(INCDIR) -I$(JNIINCDIR) -I$(JNIMDINCDIR)
DOCFLAGS 	= -static
SRCS 		= dprt.c ngat_dprt_o_DpRtLibrary.c
HEADERS		= $(SRCS:%.c=%.h)
OBJS		= $(SRCS:%.c=$(BINDIR)/%.o)
DOCS 		= $(SRCS:%.c=$(DOCSDIR)/%.html)
LIBS		= -lcfitsio -lioo_ccd_dprt -ldprt_object -ldprt_libfits -llt_filenames -ldprt_jni_general

top: shared docs

shared: $(INCDIR)/ngat_dprt_o_DpRtLibrary.h $(LT_LIB_HOME)/$(LIBNAME).so

$(INCDIR)/ngat_dprt_o_DpRtLibrary.h: $(DPRT_BIN_HOME)/java/ngat/dprt/o/DpRtLibrary.class
	$(JAVAH) -jni -d $(INCDIR) -classpath $(DPRT_BIN_HOME)/java:$(CLASSPATH) ngat.dprt.o.DpRtLibrary
	$(TOUCH) $@

$(LT_LIB_HOME)/$(LIBNAME).so: $(OBJS)
	$(CC) $(CCSHAREDFLAG) $(CFLAGS) $(OBJS) -o $@ $(TIMELIB) $(LIBS) $(SOCKETLIB)

$(BINDIR)/%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

static: $(LT_LIB_HOME)/$(LIBNAME).a

$(LT_LIB_HOME)/$(LIBNAME).a: $(OBJS)
	ar rcv $@ $?

docs: $(DOCS)

$(DOCS) : $(SRCS)
	-$(CDOC) -d $(DOCSDIR) -h $(INCDIR) $(DOCFLAGS) $(SRCS)

# dont checkout ngat_dprt_o_DpRtLibrary.h - it is a machine built header
checkout:
	$(CO) $(CO_OPTIONS) $(SRCS)
	cd $(INCDIR); $(CO) $(CO_OPTIONS) dprt.h;

# dont checkin ngat_dprt_o_DpRtLibrary.h - it is a machine built header
checkin:
	-$(CI) $(CI_OPTIONS) $(SRCS)
	-(cd $(INCDIR); $(CI) $(CI_OPTIONS) dprt.h;)

staticdepend:
	makedepend $(MAKEDEPENDFLAGS) -p$(BINDIR)/ -- $(CFLAGS)  -- $(SRCS)

depend:
	makedepend $(MAKEDEPENDFLAGS) -p$(BINDIR)/ -- $(CFLAGS)  -- $(SRCS)

lint:
	$(LINT)	$(LINTFLAGS) $(SRCS)

clean:
	-$(RM) $(RM_OPTIONS) $(OBJS) $(LT_LIB_HOME)/$(LIBNAME).so $(LT_LIB_HOME)/$(LIBNAME).a 
	-$(RM) $(RM_OPTIONS) $(INCDIR)/ngat_dprt_o_DpRtLibrary.h $(TIDY_OPTIONS)

tidy:
	-$(RM)  $(RM_OPTIONS) $(TIDY_OPTIONS)
	-cd $(INCDIR); $(RM) $(RM_OPTIONS) $(TIDY_OPTIONS);

backup: tidy
	-$(RM) $(RM_OPTIONS) $(OBJS)

#
# $Log: not supported by cvs2svn $
# Revision 1.1  2011/10/31 13:51:48  cjm
# Initial revision
#
#
# DO NOT DELETE

/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/stdio.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/features.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/sys/cdefs.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/wordsize.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/gnu/stubs.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/gnu/stubs-32.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/types.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/typesizes.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/libio.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/_G_config.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/wchar.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/wchar.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/gconv.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/stdio_lim.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/sys_errlist.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/stdlib.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/sys/types.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/time.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/endian.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/endian.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/sys/select.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/select.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/sigset.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/time.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/sys/sysmacros.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/pthreadtypes.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/alloca.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/string.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/math.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/huge_val.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/mathdef.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/mathcalls.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /home/dev/src/cfitsio3310/include/fitsio.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/limits.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/posix1_lim.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/local_lim.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/linux/limits.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/posix2_lim.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /home/dev/src/cfitsio3310/include/longnam.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /home/dev/src/libdprt/jni_general/include/dprt_jni_general.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/java/jdk1.6.0_07/include/jni.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/java/jdk1.6.0_07/include/linux/jni_md.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /home/dev/src/libdprt/ccd_imager/ccd_dprt.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/sys/stat.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/stat.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/unistd.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/posix_opt.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/confname.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/getopt.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/errno.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/errno.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/linux/errno.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/asm/errno.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/asm-generic/errno.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/asm-generic/errno-base.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/pthread.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/sched.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/sched.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/signal.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/setjmp.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/dirent.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /usr/include/bits/dirent.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /home/dev/src/libdprt/ccd_imager/lt_filenames.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /home/dev/src/libdprt/ccd_imager/dprt_libfits.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /home/dev/src/libdprt/object/include/object.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /home/dev/src/libdprt/ccd_imager/generic_ccd_dprt.h
/home/dev/bin/libdprt/o/c/i386-linux/dprt.o: /home/dev/src/libdprt/o/include/dprt.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/stdio.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/features.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/sys/cdefs.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/bits/wordsize.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/gnu/stubs.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/gnu/stubs-32.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/bits/types.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/bits/typesizes.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/libio.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/_G_config.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/wchar.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/bits/wchar.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/gconv.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/bits/stdio_lim.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/bits/sys_errlist.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/stdlib.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/sys/types.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/time.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/endian.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/bits/endian.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/sys/select.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/bits/select.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/bits/sigset.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/bits/time.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/sys/sysmacros.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/bits/pthreadtypes.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/alloca.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/include/string.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/java/jdk1.6.0_07/include/jni.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /usr/java/jdk1.6.0_07/include/linux/jni_md.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /home/dev/src/libdprt/o/include/ngat_dprt_o_DpRtLibrary.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /home/dev/src/libdprt/object/include/object.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /home/dev/src/libdprt/o/include/dprt.h
/home/dev/bin/libdprt/o/c/i386-linux/ngat_dprt_o_DpRtLibrary.o: /home/dev/src/libdprt/jni_general/include/dprt_jni_general.h
