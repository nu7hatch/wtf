# WTF (Web Template Framework)

Web Template Framework was originally an integral part of [WebKit browser](http://www.webkit.org), and provides
huge bunch of useful classes, functions and templates used across all WebKit components. Now this code is
extracted and adjusted to use as a static library, so you can freely take advantage of it in your projects.

## Building

To build WTF use bundled `autogen.sh` script (after all it executes the `cmake` command and accepts all
its parameters).

    $ autogen.sh
    
Now you can compile and install it using `make`.

    $ make
    $ sudo make install

### Multi-threading

If you want WTF to support multi-threading, you need to have `pthreads` installed in your system. Installation
will detect it automatically. 

Using multi-threaded version you have to remember to initialize threading in your application:

    #include "wtf/Threading.h"
    
    int main()
    {
      WTF::initializeThreading();
      *snip*
    }

### Single-threaded build

If you want to build single-threaded version, use the following configuration: 

    $ autogen.sh -DSINGLE_THREADED=1

## Copyrights & License

Adapted by Chris Kowalik (aka. nu7hatch).

Copyright (C) 2005, 2006, 2007, 2008 Apple Inc. All rights reserved.

This library is free software; you can redistribute it and/or
modify it under the terms of the GNU Library General Public
License as published by the Free Software Foundation; either
version 2 of the License, or (at your option) any later version.

This library is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
Library General Public License for more details.

You should have received a copy of the GNU Library General Public License
along with this library; see the file COPYING.LIB.  If not, write to
the Free Software Foundation, Inc., 51 Franklin Street, Fifth Floor,
Boston, MA 02110-1301, USA.
