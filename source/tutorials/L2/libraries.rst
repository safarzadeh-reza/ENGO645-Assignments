Install Required Python libraries
=================================


In the previous tutorial, we have installed Anaconda Python distribution. 
Anaconda comes with a lot of useful libraries for scientific computing. 
However, we need to install a few more libraries for this tutorial.

.. admonition:: Is it necessary to install Anaconda and JupyterLab?

    No! You can also complete the course without installing Anaconda and JupyterLab.
    As far as you can edit python **Notebooks** and do the **version controling** with GitHub, you are good to go.
    You can use any IDE you like such as PyCharm, Spyder, VSCode, Google Colab, etc.

General guide for installing packages with Conda
------------------------------------------------

Conda has an excellent `online user guide <https://docs.conda.io/projects/conda/en/latest/index.html>`__ which covers most of the basic things,
such as installing new packages.


Conda install
~~~~~~~~~~~~~

You can install new packages using the `conda install <https://docs.conda.io/projects/conda/en/latest/commands/install.html>`__
command. The basic syntax for installing packages is ``conda install package-name``.
In addition, we also want to specify the **conda channel** from where the package is downloaded using the parameter `-c`.

**Installing Pandas package from the conda-forge channel:**

.. code-block::

    conda install -c conda-forge pandas

Once you run this command, you will see also other packages getting installed and/or updated as conda checks for dependencies of the installed package.
Read more about package installations in the `conda documentation <https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-pkgs.html#installing-packages>`__
It's a good idea to search for installation instructions for each package online.

You can **install other useful packages in a similar way:**

.. code-block::

    conda install -c conda-forge matplotlib
    conda install -c conda-forge bokeh
    conda install -c conda-forge geopandas

.. admonition:: Conda channels

    `Conda channels <https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/channels.html>`__ are remote locations where packages are stored.
    During this course (and in general when installing packages for scientific computing and GIS analysis) we download most packages from the `conda-forge <https://conda-forge.org/#about>`__ channel.


.. admonition:: Conflicting packages

    A good rule of thumb is to **always install packages from the same channel** (for this course, we prefer the `conda-forge` channel).
    In case you encounter an error message when installing new packages, you might want to first check the versions and channels of existing
    packages using the `conda list` command before trying again.


Some of the useful packages for this course
-------------------------------------------

In the following, we list some of the useful packages for this course. 
You can install them using the `conda install` command as shown above.
Some of these packages are already installed with Anaconda.
You can check the installed packages using the `conda list` command.


-  `Pandas <https://pandas.pydata.org/>`__ is a Python library for data analysis.
-  `Matplotlib <https://matplotlib.org/>`__ is a Python library for plotting.
-  `Bokeh <https://bokeh.org/>`__ is a Python library for interactive plotting.
-  `Seaborn <https://seaborn.pydata.org/>`__ is a Python library for statistical data visualization.
-  `Folium <https://python-visualization.github.io/folium/>`__ is a Python library for creating interactive maps.
-  `Geopandas <https://geopandas.org/>`__ is a Python library for working with geospatial data.
-  `Shapely <https://shapely.readthedocs.io/en/latest/>`__ is a Python library for working with geometric objects.
-  `Pyproj <https://pyproj4.github.io/pyproj/stable/>`__ is a Python library for working with projections.
-  `Cartopy <https://scitools.org.uk/cartopy/docs/latest/>`__ is a Python library for working with maps and projections.
-  `Scikit-learn <https://scikit-learn.org/stable/>`__ is a Python library for machine learning.
-  `Scipy <https://www.scipy.org/>`__ is a Python library for scientific computing.
-  `Statsmodels <https://www.statsmodels.org/stable/index.html>`__ is a Python library for statistical modeling.
-  `tabulate <https://pypi.org/project/tabulate/>`__ is a Python library for printing tables.
-  `branca <https://pypi.org/project/branca/>`__ is a Python library for creating HTML maps.

