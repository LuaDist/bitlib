# Copyright (C) 2007-2009 LuaDist.
# Created by Peter Drahoš
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

PROJECT(bitlib C)
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
INCLUDE(dist.cmake)

ADD_LUA_MODULE(bit lbitlib.c bit.def)
ADD_LUA_TEST(test.lua)

INSTALL(TARGETS bit DESTINATION ${INSTALL_CMOD})
INSTALL(FILES AUTHORS COPYING ChangeLog NEWS README DESTINATION ${INSTALL_DATA})
INSTALL(FILES find_limits.lua test.lua DESTINATION ${INSTALL_TEST})
