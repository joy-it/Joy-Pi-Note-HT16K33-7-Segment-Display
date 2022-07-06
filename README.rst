Introduction
=============

This is a library to access the 7-segment display of the Joy-Pi Note.
The library was originaly created by `library <https://github.com/adafruit/Adafruit_CircuitPython_HT16K33>`_.

Installing from PyPI
====================

To install, download the library and run the following command:

.. code-block:: shell

    sudo python3 setup.py install

Usage Example
=============

.. code-block :: python

    import board
    from adafruit_ht16k33.segments import Seg7x4

    i2c = board.I2C()
    segment = Seg7x4(i2c, address=0x70)

    segment.fill(0)
    segment[0] = str("1")
    segment[1] = str("2")
    segment[2] = str("3")
    segment[3] = str("4")



Documentation
=============

API documentation for this library can be found on `Read the Docs <https://docs.circuitpython.org/projects/ht16k33/en/latest/>`_.

For information on building library documentation, please check out `this guide <https://learn.adafruit.com/creating-and-sharing-a-circuitpython-library/sharing-our-docs-on-readthedocs#sphinx-5-1>`_.
