========
bringbuf
========

*bringbuf* is very basic circular buffer implementation. Its purpose is to handle byte streams (for instance from a serial port). It is based on enque, which is a efficient way to handle queues in Python. First bytes written to the buffer, are first bytes read from the buffer. If the buffer is full it overflows and begins overwriting the oldest data.

The code is available at `github`_.

.. _github: https://github.com/ticktronaut/bringbuf

Install
-------

Requirements
````````````

There are no requirements. *bringbuf* has view dependencies (*collections*, *itertools* and *warnings*), which are core modules.

Setup
`````

Install *bringbuf* using the following command:

::

    $ [sudo] pip install bringbuf 

Usage
-----

.. code-block:: python

    from bringbuf import bRingBuf
    
    # define a ring buffer with the size of 5 bytes
    buf = bRingBuf(5)
    # check if buffer is empty (True)
    print(buf.is_empty())
    # enqueue 6 bytes to the buffer
    # (not that the buffer will overflow)
    buf.enqueue([0x01, 0x02, 0x03, 0x04, 0x05, 0x06])
    # check if buffer is empty (False) 
    print(buf.is_empty())
    # read content of the whole buffer without removing any bytes
    print(buf.read(buf.len))
    # read and remove three bytes from the buffer 
    print(buf.dequeue(3))
    # read content of the whole buffer without removing any bytes
    print(buf.read(buf.len))
  

License
-------

Copyright (c) 2016 Andreas Gschossmann

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.