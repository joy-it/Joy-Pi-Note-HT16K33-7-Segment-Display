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

    # Import all board pins and bus interface.
    import board
    import busio

    # Import the HT16K33 LED matrix module.
    from adafruit_ht16k33 import matrix

    # Create the I2C interface.
    i2c = busio.I2C(board.SCL, board.SDA)

    # Create the matrix class.
    # This creates a 16x8 matrix:
    matrix = matrix.Matrix16x8(i2c)
    # Or this creates a 8x8 matrix:
    #matrix = matrix.Matrix8x8(i2c)
    # Or this creates a 8x8 bicolor matrix:
    #matrix = matrix.Matrix8x8x2
    # Finally you can optionally specify a custom I2C address of the HT16k33 like:
    #matrix = matrix.Matrix16x8(i2c, address=0x70)

    # Clear the matrix.
    matrix.fill(0)

    # Set a pixel in the origin 0,0 position.
    matrix[0, 0] = 1
    # Set a pixel in the middle 8, 4 position.
    matrix[8, 4] = 1
    # Set a pixel in the opposite 15, 7 position.
    matrix[15, 7] = 1
    matrix.show()

    # Change the brightness
    matrix.brightness = 8

    # Set the blink rate
    matrix.blink_rate = 2


Documentation
=============

API documentation for this library can be found on `Read the Docs <https://docs.circuitpython.org/projects/ht16k33/en/latest/>`_.

For information on building library documentation, please check out `this guide <https://learn.adafruit.com/creating-and-sharing-a-circuitpython-library/sharing-our-docs-on-readthedocs#sphinx-5-1>`_.
