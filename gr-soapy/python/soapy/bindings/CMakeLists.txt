# Copyright 2020-2021 Free Software Foundation, Inc.
#
# This file is part of GNU Radio
#
# SPDX-License-Identifier: GPL-3.0-or-later
#

include(GrPybind)

########################################################################
# Python Bindings
########################################################################

list(APPEND soapy_python_files
    block_python.cc
    soapy_types_python.cc
    source_python.cc
    sink_python.cc
    python_bindings.cc)

GR_PYBIND_MAKE_CHECK_HASH(soapy
   ../../..
   gr::soapy
   "${soapy_python_files}")

install(TARGETS soapy_python DESTINATION ${GR_PYTHON_DIR}/gnuradio/soapy COMPONENT pythonapi)
