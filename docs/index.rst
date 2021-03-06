PyKaldi
=======

.. warning:: PyKaldi is still at alpha stage. Some features might not work yet.

`PyKaldi <https://github.com/pykaldi/pykaldi>`_ is a Python wrapper for `Kaldi
<http://kaldi-asr.org>`_ exposing nearly all of Kaldi's C++ API to Python code.
It aims to bridge the gap between Kaldi and all the nice things Python has to
offer including its mature ecosystem of high quality software for scientific
computing, machine learning, interactive data exploration and visualization.

PyKaldi is more than a collection of bindings into Kaldi libraries. It is a
scripting layer providing first class support for essential Kaldi and
`OpenFst <http://www.openfst.org>`_ types in Python. PyKaldi vector and matrix
types are tightly integrated with `NumPy <http://www.numpy.org>`_. They can be
seamlessly converted to NumPy arrays and vice versa without copying the
underlying memory buffers. PyKaldi FST types, including Kaldi style lattices,
are first class citizens in Python. The API for the user facing FST types and
operations is almost entirely defined in Python mimicking the API exposed by
`pywrapfst <http://www.openfst.org/twiki/bin/view/FST/PythonExtension>`_, the
official Python wrapper for OpenFst.


Features
--------

* Near-complete coverage of Kaldi C++ API

* First class support for Kaldi and OpenFst types in Python

* Extensible design

* Open license

* Extensive documentation

* Thorough testing

* Example scripts

* Support for both Python 2.7 and 3.5+


About PyKaldi
-------------

PyKaldi harnesses the power of `CLIF <https://github.com/google/clif>`_ to wrap
Kaldi C++ libraries using simple API descriptions. The CPython extension modules
generated by CLIF can be imported in Python to interact with Kaldi. While CLIF
is great for exposing the existing C++ API in Python, the wrappers do not always
expose a "Pythonic" API that is easy to use from Python. To address this
concern, PyKaldi extends the raw CLIF wrappers in Python (and sometimes in C++)
to provide a more "Pythonic" API. Below figure illustrates where PyKaldi fits in
the Kaldi software architecture.

.. image:: pykaldi.png
   :alt: Kaldi Software Architecture
   :align: center
   :scale: 60 %

PyKaldi has a modular design which makes it easy to maintain and extend. Source
files are organized in a directory tree that is a replica of the Kaldi source
tree. Each directory defines a subpackage and contains only the wrapper code
written for the associated Kaldi library. The wrapper code consists of:

* CLIF C++ API descriptions defining the types and functions to be wrapped and
  their Python API,

* C++ headers defining the shims for Kaldi code that is not compliant with the
  Google C++ style expected by CLIF,

* Python modules grouping together related extension modules generated with CLIF
  and extending the raw CLIF wrappers to provide a more "Pythonic" API.


Getting Started
---------------

Some places to help you get started:

* `Walkthrough Example <https://github.com/pykaldi/pykaldi/tree/master/examples/walkthrough.md>`_
* `Some Kaldi binaries re-implemented using PyKaldi <https://github.com/pykaldi/pykaldi/tree/master/examples>`_


.. toctree::
   :hidden:

   self

.. toctree::
   :caption: User Guide
   :glob:
   :maxdepth: 2

   user/*

.. toctree::
   :caption: Developer Guide
   :glob:
   :maxdepth: 2

   dev/*

.. include:: api.rst
