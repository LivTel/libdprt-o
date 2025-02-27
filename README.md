# libdprt-o

This is part of the libdprt package, which provides (real-time) data pipelines for Liverpool Telescope instruments.
This particular sub-module provides the JNI 'glue' (interface layer) between ngat.dprt.o.DpRtLibrary (in the dprt repository) and the particular build of libdprt/ccd_dprt (libo_ccd_dprt.so) (the source code for which is in the ccd_dprt repository) that is suitable for the IO:O instrument. 

# Installation

The repository should be installed inside the libdprt directory in an LT development environment. The directory name should be renamed to 'o' or soft-linked.

# Prerequisites

- LT Development environment
- lt_filenames (http://github.com/LivTel/lt_filenames) Filename support for the data pipeline.
- ccd_dprt (http://github.com/LivTel/ccd_dprt) The main data pipeline codebase.
- jni_general (http://github.com/LivTel/libdprt-jni_general) Generic JNI 'glue' routines.
