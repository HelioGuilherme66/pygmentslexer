Pygments lexer for Robot Framework test data
============================================

This project implements a `Pygments <http://pygments.org>`_ lexer
for `Robot Framework <http://robotframework.org>`_ test data in plain
text format. It is available as a separate plugin and *included in
Pygments 1.6 and newer*.

This version will be available not before 

What is Pygments
----------------

Pygments_ is a generic library/tool for syntax highlighting. It is used by
many different applications and wikis.

What is Robot Framework
-----------------------

`Robot Framework`_ is a generic open source automation framework for
acceptance testing, acceptance test driven development (ATDD), and robotic
process automation (RPA). It has simple plain text syntax and this project
provides syntax highlighting for it.

Installation
------------

Installation packages are at `PyPI
<https://pypi.python.org/pypi/robotframeworklexer>`_. Installation itself
is easiest with ``pip``:

.. code:: bash

    pip install pygments
    pip install robotframeworklexer

The latter step is only needed if you want to use a newer lexer version than
the one included in Pygments.

Usage
-----

After installation Pygments will recognize ``robotframework``
lexer. It can be used, for example, with the ``pygmentize`` tool:

.. code:: bash

    # Lexer for ``*.robot`` files is found automatically.
    pygmentize tests.robot

    # Explicit lexer configuration needed with ``*.txt`` files.
    pygmentize -l robotframework tests.txt

    # Override built-in robotframework lexer with separately installed version.
    pygmentize -O robotframework=robotframework tests.robot

See `generate.py <https://github.com/robotframework/pygmentslexer/blob/master/generate.py>`_
script for an example of the programmatic usage. For general information about
using Pygments, consult `its documentation <http://pygments.org/docs/>`_ and/or
the documentation of the tool you are using it with.

Alternative Usage
-----------------

You can use ``robotframeworklexer.py`` as a custom lexer in ``pygments``. See the documentation
of ``pygments`` for more information. Below, are two examples applied to the test suite `example.robot <file:///./example.robot>`_.

.. code:: bash

   python -m pygments -l ./robotframeworklexer.py:RobotFrameworkLexer -x -o example.png -f png ./example.robot 
   # result: `<file:///./example.png>`_
   
   python -m pygments -l ./robotframeworklexer.py:RobotFrameworkLexer -x -o example.txt -f raw ./example.robot 
   # result: `<file:///./example.txt>`_

License
-------

`Apache License, Version 2.0 <http://www.apache.org/licenses/LICENSE-2.0.html>`_.
