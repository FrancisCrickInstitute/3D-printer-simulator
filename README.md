Printator is a simple 3D printer simulator based on a subpart of Printrun.

At the time of writing this, the simulator in itself fits in 232 lines of
Python code (as reported by sloccount). Most of the non-trivial things come
from Printrun's gcoder and gcview modules, which respectively provide gcode
parsing and the 3D viewer.

# Dependencies

To use Printator, you will need:

  * Linux or MacOS (to use socat command)
  * python (tested on 3.12.4),
  * pyserial (or python-serial on ubuntu/debian)
  * pyglet (<2.0)
  * wxPython
  * socat (external binary dependency, used to create virtual serial ports)
  * Printrun (installed directly from the GitHub repo)

# Initial setup

Install most of the dependencies from the requirements.txt file

    pip install -r requirements.txt

Once this is done, you will just need to install socat. Install instructions for Mac can be found at https://ports.macports.org/port/socat/.

# Running

Running Printator is as easy as

    python printator.py

It will create a serial port with a random file name and start the simulator.

You can specify the serial port path with the `-s` option:

    python printator.py -s `pwd`/sim

You can also disable delays (i.e. process gcode as fast as possible, without
realistically waiting) using the `-f` option.

# Known issues

- Custom baudrates are not supported for serial-based communications. TCP
  support shouldn't have any speed limit, though.

# Planned features

- Checksum/line number verification
- Computing an STL file from the print results
- Temperature support
