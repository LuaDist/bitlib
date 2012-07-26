# Copyright (C) 2007-2012 LuaDist.
# Created by Peter Drahoš
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

project ( bitlib C )
cmake_minimum_required ( VERSION 2.8 )
include ( cmake/dist.cmake )
include ( lua )

install_lua_module ( bit lbitlib.c bit.def )
install_test ( find_limits.lua test.lua )
install_data ( AUTHORS COPYING ChangeLog NEWS README )

add_lua_test ( test.lua )
