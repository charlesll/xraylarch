.. _install-chapter:

====================================
Downloading and Installation
====================================


.. _Larch Repository (github.com): http://github.com/xraypy/xraylarch
.. _Anaconda Python:               http://www.continuum.io/
.. _Anaconda Downloads:            http://www.continuum.io/downloads
.. _lmfit:                         https://lmfit.github.io/lmfit-py/
.. _Larch Releases (github.com):   https://github.com/xraypy/xraylarch/releases
.. _Larch Binary Installers:       https://millenia.cars.aps.anl.gov/xraylarch/downloads
.. _source code (tar.gz):          https://millenia.cars.aps.anl.gov/xraylarch/downloads/xraylarch-0.9.40.tar.gz
.. _Larch for 64bit Windows:       https://millenia.cars.aps.anl.gov/xraylarch/downloads/xraylarch-0.9.40-Windows-x86_64.exe
.. _Larch for 32bit Windows:       https://millenia.cars.aps.anl.gov/xraylarch/downloads/xraylarch-0.9.37-Windows-x86.exe
.. _Larch for MacOSX:              https://millenia.cars.aps.anl.gov/xraylarch/downloads/xraylarch-0.9.40-MacOSX-x86_64.sh
.. _Larch for Linux:               https://millenia.cars.aps.anl.gov/xraylarch/downloads/xraylarch-0.9.40-Linux-x86_64.sh
.. _Larch Docs and Examples:       https://millenia.cars.aps.anl.gov/xraylarch/downloads/xraylarch-0.9.40-docs-examples.zip

The latest release version of Larch is |release|.

Larch is in active and continuing development, and the intention is to tag
a new release version every three to six months.  Of course, there may be
bugs and unintended features, and some missing or incomplete desired
features as we add new functionality.  Still, most of what is in Larch for
XAFS data analysis and working with XRF maps from X-ray microprobes is
working and ready for use.

Single-File Installers
=========================

For Windows, MacOSX, and Linux, Larch now comes with simple installers,
available at `Larch Binary Installers`_.
These are self-contained files that will install a complete Python environment
from Anaconda Python and all of X-rayLarch onto your computer.  Installing
Larch this way will be create a folder in your home folder called `xraylarch`
by default (you can change it).  This does not require administrative
privilege and will not interfere with anything on your system -- you can
uninstall simply by removing this folder.  The installers are fairly large
(300 to 600 Mb), but includes an entire scientific python environment.
Installing by the other means described below will not actually take less disk
space, but will involve downloading many more smaller files, which may be an
advantage for some people with poor connectivity.

.. _installers_table:

**Table of Larch Installers**

  +-------------------------+-------------------------------------+
  | Operating System        |   installer                         |
  +=========================+=====================================+
  | Windows (64 bit)        | `Larch for 64bit Windows`_          |
  +-------------------------+-------------------------------------+
  | Mac OSX (64 bit)        | `Larch for MacOSX`_                 |
  +-------------------------+-------------------------------------+
  | Linux (64 bit)          | `Larch for Linux`_                  |
  +-------------------------+-------------------------------------+
  | Source Code             | `source code (tar.gz)`_             |
  +-------------------------+-------------------------------------+
  | Docs and Examples       | `Larch Docs and Examples`_          |
  | (all systems)           |                                     |
  +-------------------------+-------------------------------------+

A 32-bit installer for Windows may be created to support older systems, but
is not available at this writing.


For Mac OSX or Linux, download the appropriate file then open a Terminal
(Applications->Utilities->Terminal on Mac OSX), use `cd` to move to the
download folder (typically `cd Downloads`) and run::

    bash xraylarch-0.9.40-MacOSX-x86_64.sh

or::

    bash xraylarch-0.9.40-Linux-x86_64.sh

Once installed, you will be able to upgrade to future versions of Larch using::

    conda update xraylarch

and you will be able to completely uninstall simply by removing the
`xraylarch` folder in your home directory.

On Windows and Mac OSX, the installer will create a *Larch* folder on your
Desktop containing links to many of the Larch GUI applications listed above in
:ref:`Table of Larch Applications and Programs <larch_app_table>`.

A key advantage of using Anaconda is that once installed, updates can be
installed with::

    conda update -yc GSECARS xraylarch

As of this writing, some functionality -- notably X-ray diffraction -- may
need additional libraries installed, and some of these libraries may not be
available for Python3.6 or for all platforms.   We're working on this, but
if you need help, please contact us.


Installing with Anaconda Python
======================================

For those familiar with Python, Larch can be installed into an existing
Python environment.  We highly recommended using `Anaconda Python`_ for
Larch.  While Larch can be installed from source code with standard
versions of Python, Anaconda Python makes getting and installing the many
packages needed for Larch.

`Anaconda Python`_ provides a free and well-supported version of Python for
scientific work with many useful packages included.  By default, Anaconda
Python installs into your own home folder (on Windows, this will be the
`APPDATA` location, which is typically something like
`C:\\Users\\YourName\\AppData\\Local\\Continuum\\Anaconda3`).  As with the
single-file installers above, installing Anaconda Python does not require
extra permissions to install, upgrade, or remove components.  Anaconda
includes a robust package manager called *conda* that makes it easy to
update the packages it manages, including Larch.

Begin by installing the latest version of Anaconda Python from the
`Anaconda Downloads`_ site.  Python 3.6 is recommended, but Python 2.7
should work too.  Once that is installed, you can open a Terminal (on Linux
or Mac OSX) or the Anaconda prompt (on Windows) and type::

    conda install -yc GSECARS xraylarch

to install Larch.  On Windows or Mac OSX, then type::

    larch_makeicons

to make a `Larch` folder on your desktop with shortcuts (Windows) or
Applications (MacOS) for the main Larch applications.

One advantage of Anaconda Python is that it makes updates very easy.  As new
releases of Larch and the required packages are released, you can get the
latest versions with::

   conda update --all


Python Versions: 2.7 or 3.6?
================================

As of this writing (June, 2018) there are two main supported versions of
Python: Version 2.7 and Version 3.6.  We have moved to using Python 3.6 by
default and the installers above use Python 3.6, Larch still works with
Python 2.7, and we will maintain support for Python 2.7 through the end of
2018.  We intend to drop support for Python 2.7 in early 2019.


Source Installation
=========================

For Python-savvy users, Larch can be installed from source. You can use either
the `source code (tar.gz)`_ or from `Larch releases (github.com)`_.  In
addition, you can use `git` to grab the latest development version of the
source code::

   git clone http://github.com/xraypy/xraylarch.git


With the source kit unpacked using `tar` or `zip`, you should be able to
install Larch using `python setup.py install`.  This should automatically use
`pip` to install any required dependencies as well as Larch itself.  Depending
on your platform and version of Python, you may need elevated permissions as
from `sudo` to install Larch to a system folder.

There are several required packages and a few "highly recommended" packages
for Larch.  These are listed in the next section.



Prerequisites
~~~~~~~~~~~~~~~~~~~

Larch requires Python version 3.6 or 2.7. In addiion, many Python
packages are required for Larch to work.  These are listed in the table below.


.. _dependencies_table:

**Table of Larch Dependencies** This lists the packages that are either
required for Larch or required for some portion of Larch functionality to
work. The required packages and several of the recommended packages will
normally be installed by default or are easily available from with `conda` or
`pip`.

  +----------------+-------------+-----------------------------+
  | Package name   | min version | status, notes               |
  +================+=============+=============================+
  | numpy          | 1.10        | required                    |
  +----------------+-------------+-----------------------------+
  | scipy          | 0.17        | required                    |
  +----------------+-------------+-----------------------------+
  | six            | 1.10        | required                    |
  +----------------+-------------+-----------------------------+
  | matplotlib     | 2.0         | required                    |
  +----------------+-------------+-----------------------------+
  | sqlalchemy     | 0.9         | required                    |
  +----------------+-------------+-----------------------------+
  | h5py           | 2.4         | required                    |
  +----------------+-------------+-----------------------------+
  | scikit-learn   | 0.18        | required                    |
  +----------------+-------------+-----------------------------+
  | pillow         | 3.4         | required                    |
  +----------------+-------------+-----------------------------+
  | peakutils      | 1.0.0       | required                    |
  +----------------+-------------+-----------------------------+
  | requests       | 2.1         | required                    |
  +----------------+-------------+-----------------------------+
  | asteval        | 0.9.12      | required                    |
  +----------------+-------------+-----------------------------+
  | lmfit          | 0.9.11      | required                    |
  +----------------+-------------+-----------------------------+
  | uncertainties  | 3.0         | required                    |
  +----------------+-------------+-----------------------------+
  | pyyaml         |             | required                    |
  +----------------+-------------+-----------------------------+
  | psutil         |             | required                    |
  +----------------+-------------+-----------------------------+
  | termcolor      |             | required                    |
  +----------------+-------------+-----------------------------+
  | wxpython       | 4.0.0       | required for GUIs, plotting |
  +----------------+-------------+-----------------------------+
  | wxmplot        | 0.9.30      | required for plotting       |
  +----------------+-------------+-----------------------------+
  | wxutils        | 0.1.3       | required for GUIs           |
  +----------------+-------------+-----------------------------+
  | pyepics        | 3.3.0       | needed for using Epics      |
  +----------------+-------------+-----------------------------+
  |scikit-image    |             | needed for tomography maps  |
  +----------------+-------------+-----------------------------+
  |tomopy          |             | recommended for tomography  |
  +----------------+-------------+-----------------------------+
  |pyFAI           |             | needed for XRD              |
  +----------------+-------------+-----------------------------+
  |fabio           |             | needed for XRD              |
  +----------------+-------------+-----------------------------+
  |PyCifRW         |             | needed for XRD              |
  +----------------+-------------+-----------------------------+
  |epicsscan       |             | needed for epics scanning   |
  +----------------+-------------+-----------------------------+
  |psycopg2        |             | needed for epics scanning   |
  +----------------+-------------+-----------------------------+
  |silx            |             | needed to read Spec files   |
  +----------------+-------------+-----------------------------+


These are all available from PyPI (the Python Package Index), and for
Anaconda Python 2.7 and 3.6.  The packages not included with core Anaconda
packages are available on the GSECARS conda channel, and will be installed
with `conda install -c GSECARS xraylarch`.  If you're installing from
source or using a Python distribution other than Anaconda, all these
packages are also available from PyPI and can be installed with  `pip
install <packagename>` or `conda install -c GSECARS <packagename>`.

Optional Modules
~~~~~~~~~~~~~~~~~~~~~~~~~~

There are a few packages that are required only for some more specialized
uses of Larch that may not be important for everyone using Larch. For
example, the advanced and in-development X-ray diffraction analysis
capabilities require the following packages:

   fabio, pyFAI, PyCifRw

Some x-ray computed tomography capabilities are available, and require the
packages:

   tomopy, scikit-image

Some Epics-based data collection tools use Larch, and require:

   pyepics, psycopg2, epicsscan

As with the other packages listed above, these are either available from the
GSECARS anaconda channel or from PyPI.

To be clear, most of Larch will work fine without these modules installed,
but the corresponding functionality will not be available.

At this writing (March, 2018), we do not have supported packages for
Windows for fabio, pyFAI, or tomopy.  You may be able to install fabio and
pyFAI separately, and we are working on these packages.


Installation from Source
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If installing from source, first unpack the source distribution kit, move
into the created xraylarch-VERSION directory, and type::

    python setup.py install


Documentation and Examples
================================

The source kit includes sources for documentation in the `docs` folder
and several examples (including all those shown in this documentation)
in the `examples` folder.  These are also available separately at
`Larch Docs and Examples`_.


Citing Larch
========================

Currently, the best citation for Larch is M. Newville, *Larch: An Analysis
Package For XAFS And Related Spectroscopies*. Journal of Physics:
Conference Series, 430:012007 (2013).  :cite:`larch2013`


Funding and Support
=======================

Larch development at the GeoScoilEnviroCARS sector of Center for Advanced
Radiation Sources at the University of Chicago has been supported by the US
National Science Foundation - Earth Sciences (EAR-1128799), and Department
of Energy GeoSciences (DE-FG02-94ER14466).  In addition, funding
specifically for Larch was granted by the National Science Foundation -
Advanced CyberInfrastructure (ACI-1450468).


Acknowledgements
==================

Larch was mostly written by and is maintained by Matt Newville
<newville@cars.uchicago.edu>.  Bruce Ravel has an incalculable influence on
the design and implementation of this code and has provided countless fixes
for serious problems in design and execution in the early stages.  More
importantly, Larch would simply not exist without the long and fruitful
collaboration we've enjoyed.  Margaret Koker wrote most of the X-ray
diffraction analysis code, and much of the advanced functionality of the
GSECARS XRF Map Viewer.  Mauro Rovezzi has provided the spec-data reading
interface.  Tom Trainor had a very strong influence on the original design
of Larch, and helped with the initial version of the python implementation.
Yong Choi wrote the code for X-ray standing wave and reflectivity analysis
and graciously allowed it to be included and modified for Larch.  Tony
Lanzirotti and Steve Sutton have provided wonderful and patient feedback on
many parts of Larch, espcially for XANES processing and testing of the XAS
Viewer GUI.

Because Larch began as a rewrite of the Ifeffit XAFS Analysis Package, it
also references and builds on quite a bit of code developed for XAFS over
many years at the University of Chicago and the University of Washington.
The existence of the code and a great deal of its initial design therefore
owes a great thanks to Edward Stern, Yizhak Yacoby, Peter Livens, Steve
Zabinsky, and John Rehr.  More specifically, code written by Steve Zabinsky
and John Rehr for the manipulation of results from FEFF and for the
calculation of thermal disorder parameters for XAFS are included in Larch
with little modification.  Both Feff6l and Feff8l, the product of many man
years of effort by the Feff group led by John Rehr, are included in Larch.
A great many people have provided excellent bug reports, feedback, in depth
conversations, and suggestions for making Ifeffit better, including on the
ifeffit mailing list.  Many of these contributions have found their way
into Larch.

Larch includes calculations for anomalous cross-sections based on the work
of Cromer and Libermann, as implemented by Sean Brennan and Paul L. Cowen.
Their code is included in Larch with only minor changes.  Code to store and
read the X-ray Scattering data from the Elam Tables was modified from code
originally written by Darren S. Dale.  Refined values for anomalous
scattering factors have been provided directly by Christopher T. Chantler.
Further details of the origin of much of the tabularized X-ray data is
given in :ref:`xraydb-chapter`.

As Larch depends on the fantastic scientific librarie written and
maintained in python, especially the numpy, scipy, and matplotlib, the
entire scientific python community deserves a hearty thanks.  In
particular, Larch uses the `lmfit`_ library, which began as part of Larch
but was spun off into a standalone, general purpose fitting library that
became useful for application areas other than XAFS, and has benefited
greatly from numerous collaborators and added many features that Larch, in
turn, has been able to depend on.


License
============

Except where explicitly noted in the individual files, the code,
documentation, and all material associated with Larch are distributed under
the BSD License:


.. literalinclude:: ../LICENSE

.. rubric:: References

.. bibliography:: larch.bib
   :style: unsrt
   :labelprefix: Install_
   :filter: docname in docnames
