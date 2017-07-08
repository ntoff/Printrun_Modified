## RUNNING FROM SOURCE

Run Printrun for source if you want to test out the latest features.

### Dependencies

To use pronterface, you need:

  * python (ideally 2.6.x or 2.7.x),
  * pyserial (or python-serial on ubuntu/debian)
  * pyreadline (not needed on Linux) and
  * argparse (installed by default with python >= 2.7)
  * wxPython (some features such as Tabbed mode work better with wx 2.9)
  * pyglet
  * numpy (for 3D view)
  * pycairo (to use Projector feature)
  * cairosvg (to use Projector feature)
  * dbus (to inhibit sleep on some Linux systems)

Please see specific instructions for Windows and Mac OS X below. Under Linux, you should use your package manager directly (see the "GETTING PRINTRUN" section), or pip:

`pip install -r requirements.txt`

### Cython-based G-Code parser

Printrun default G-Code parser is quite memory hungry, but we also provide a much lighter one which just needs an extra build-time dependency (Cython), plus compiling the extension with:

    python setup.py build_ext --inplace

The warning message

    WARNING:root:Memory-efficient GCoder implementation unavailable: No module named gcoder_line

means that this optimized G-Code parser hasn't been compiled. To get rid of it and benefit from the better implementation, please install Cython and run the command above.

**My Note:** In order to compile this under windows, I also needed the "Microsoft Visual C++ Compiler for Python 2.7" and "Visual C++ 2008 Express Edition"

### Windows

Download the following, and install in this order:

  1. http://python.org/ftp/python/2.7.2/python-2.7.2.msi
  2. http://pypi.python.org/packages/any/p/pyserial/pyserial-2.5.win32.exe
  3. ~~http://downloads.sourceforge.net/wxpython/wxPython2.8-win32-unicode-2.8.12.0-py27.exe~~
  3. https://sourceforge.net/projects/wxpython/files/wxPython/3.0.2.0/ *(My own tests indicate wx3 works better)*
  4. https://pypi.python.org/packages/any/p/pyreadline/pyreadline-1.7.1.win32.exe
  5. https://pypi.python.org/pypi/pyglet/1.1.4

For the last one, you will need to unpack it, open a command terminal, 
go into the the directory you unpacked it in and run
`python setup.py install`

