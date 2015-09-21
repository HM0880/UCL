*******************************************************************************
Technical details
*******************************************************************************

Required programs
===============================================================================

 .. note:: These instructions are for Windows.

Download and install the following programs in the given order:

#. Anaconda (download the Windows executable Graphical Installer
   `here <http://continuum.io/downloads>`__)

   * This will install Python and most of the `packages
     <http://docs.continuum.io/anaconda/pkg-docs>`__ needed.

   * Spyder (**Start Menu -> Anaconda -> Spyder**) is the recommended
     IDE (Integrated Development Enviroment) for Python.

      - The two required panes in Spyder (**View -> Panes**) are the Editor
        and the IPython console.

   * If a non-included package is needed, open
     **Start Menu -> Anaconda -> Anaconda Command Prompt** and type
     ``pip install package_name`` to easily install ``package_name``.


#. wxPython, which is the Python port of wxWidgets can be downloaded
   `here <http://www.wxpython.org/download.php>`__.  Choose the appropriate
   ``.exe`` file and simply run the executable to install.

  * wxWidgets needs to run in separate console each time, or else the GUI
    will crash after the first run.

    * In the wxWidgets Python file, open **Run -> Configure** and click
      **Execute in new dedicated Python Console**.

    * When the "already running in separate process" error appears on a second
      run, just click "yes" to kill the current process.


#. PyInstaller is installed via ``pip install pyinstaller``.

   * For compiling and releasing Python GUIs as a Windows executable.

   * From the directory where the Python file is, run
     ``pyinstaller.exe --onefile --windowed FILENAME.py``.


    .. todo:: work on pyinstaller instructions for multiple files


#. pep8 is installed via ``pip install pep8``.

   * Python style checker.  From the directory where ``FILENAME`` is stored,
     run ``pep8 FILENAME`` to check that the code conforms to the standard
     Python style.

   * More documentation `here <https://pypi.python.org/pypi/pep8>`__.


#. YAML ("YAML Ain't Markup Language") is installed via ``pip install pyyaml``.

   * Used for human-readable config files.  For an incredibly detailed
     description, go to the latest spec sheet `here <http://yaml.org/>`__.


#. Sphinx (installation and quick-start instructions
   `here <http://sphinx-doc.org/tutorial.html>`__)

   * This documentation is written in reStructured Text (``.rst``) format and
     built with Sphinx, which runs on Python.

   * Syntax examples

     - Cheatsheet by Thomas Cokelaer `here
       <http://thomas-cokelaer.info/tutorials/sphinx/rest_syntax.html>`__.

     - More useful codes `here
       <http://udig.refractions.net/files/docs/latest/user/docguide/sphinxSyntax.html>`__.

     - And even more useful conventions/syntax `here
       <http://rest-sphinx-memo.readthedocs.org/en/latest/ReST.html>`__.

   * Sphinx is *insanely* particular technical_details whitespace, so that should be the
     first thing to check if something doesn't display properly.


#. MikTeX (download the Windows executable Basic MikTex Installer
   `here <http://miktex.org/download>`__)

   * You need ``dvipng`` (installed for Windows via MikTeX) for the
     ``sphinx.ext.pngmath``, which is a Sphinx extension typesets the math,
     to work.




.. todo:: install instructions for any of the database functionality





Highly recommended programs (but not required)
===============================================================================

#. Mercurial (download `here <https://mercurial.selenic.com/>`__)

   * *Highly* recommended for version control.  The ``.hg`` folders contain
     all the Mercurial information from past work by HM.

   * Excellent tutorial by Joel Spolsky `here <http://hginit.com/01.html>`__.

#. Notepad++ (download fresh copy
   `here <https://notepad-plus-plus.org/download/v6.8.1.html>`__) or
   Sublime Text (download `here <http://www.sublimetext.com/>`__).

   * Both of these programs can be installed as "portable programs, which"
     means you can open them from anywhere on a given network and your 
     changes will stay synced across computers.

   * Very useful with syntax highlighting, zoom, and tons of customization.

   * Sublime Text's syntax highlighting is great for these ``.rst`` documents.


Valuable command-line inputs
===============================================================================

- Anaconda

   .. note:: ``pip`` can be run from any directory in the command line.

   * Get a list of all the installed Python packages and their versions.

      - From any directory in the command line, type ``pip list >OUTPUT_PATH``.

          * ``OUTPUT_PATH`` is where you want the file to be saved.  For
            example, ``c:\ds\packages.txt``.

          * This will save a text file to the ``OUTPUT_PATH`` location.

      - To display the output in the command line, simply type ``pip list``.

- Mercurial

   .. note:: Mercurial must be run from a directory in which there is a
      Mercurial repository.

   * To get a log of all the Mercurial changes with the last change at the
     bottom, run ``hg log -r :``.

   * To get a log of the changes between two revision numbers, run
     ``hg log -r START:STOP``, where ``START`` and ``STOP`` are the revision
     numbers of interest.  The range is inclusive.

   * To view the change log on a specific file, run ``hg log -f FILENAME``.



.. todo:: code testing setup, running, design, etc.



Commands to build this documentation
===============================================================================

- Open the command line and navigate to the current directory.
   #. Open **Start Menu -> All Programs -> Accessories -> Command Prompt**.
   #. Type ``cd path_to_rst_directory`` where ``path_to_rst_directory``
      is where these ``.rst`` documents are saved.

- Generate the HTML code:
   #. Use the command line to go to the directory where these ``.rst``
      documents are saved (see above).

   #. Type ``make.bat html`` into the command line and hit enter.

   #. Wait for the process to complete.

   #. Then open ``\_build\html\index.html`` to view the results.

      .. note:: The HTML files can be kept open in a web browser, and the page
         simply refreshed (by pressing ``F5``) when a new build is created.

- Generate API documentation from inside source code
   * First-time setup (only needs to be done once per project!)
      #. Add ``'numpydoc',`` to the Sphinx extensions in the ``conf.py`` file.
         This will parse the RST documentation inside the source code files.

         .. figure:: _static\technical_details_numpydoc.PNG
            :align: center

            Where to put ``'numpydoc',`` in the ``conf.py`` file.

      #. Add ``.. automodule:: OUTPUT_FOLDER\modules.rst`` to ``index.rst``.
         This tells Sphinx where to look for the module documentation ``.rst``
         files.

         .. figure:: _static\technical_details_index_example.PNG
            :align: center

            Where to put the ``automodule`` command in ``index.rst``.


         .. note:: All of the module documentation will appear under the
            module index on the home page (as shown by the second red box).

            .. figure:: _static\technical_details_module_index.PNG
               :align: center

               Where the module documentation can be found.


  * Build the documentation

      .. note:: These two steps have to be redone every time the
         documentation is updated.

     #. Type ``sphinx-apidoc -o OUTPUT_FOLDER CODE_SOURCE_PATH`` to generate
        the ``.rst`` files from the source code.

        In the example below, the source code files are in
        ``C:\+HM\plot_MTF``, and the auto-generated ``.rst`` files will be in
        ``C:\+HM\plot_MTF\+autodoc``.  If you want the autodocs to end up in
        the same source folder, put the full source code path in place of
        ``OUTPUT_FOLDER``.

        .. figure:: _static\technical_details_apidoc.PNG
           :align: center

           Example of ``sphinx-apidoc`` input and output.


     #. Then run ``make.bat html``, and now the API documentation will come too!


- Generate a LaTeX PDF
    #. Type ``make.bat latex`` into the command line and hit enter.
    #. Wait for the process to complete.
    #. Open ``\_build\latex\MetrologyDocumentation.tex`` in TeXworks.
    #. Press ``Ctrl + t`` to typeset the document.
    #. The output will be at ``\_build\latex\MetrologyDocumentation.pdf``.
