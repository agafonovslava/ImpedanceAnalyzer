Contribute to Impedance Analyzer
================================

Local Setup
------------------

Recommended minimum environment:

* `Python <https://www.python.org/>`_
* `git <https://git-scm.com/>`_
* `virtualenv <https://python-guide.readthedocs.io/en/latest/dev/virtualenvs/#virtualenv>`_

The following assumes you have all of the above tools installed already.

Windows
^^^^^^^^

1. Clone the project:
::

    > git clone https://github.com/mdmurbach/ImpedanceAnalyzer.git
    > cd ImpedanceAnalyzer

2. Create and initialize the virtual environment for the project:
::

    > virtualenv flask
    > cd flask/Scripts
    > activate
    > cd ../..
    > pip install -r requirements.txt

3. Run the python flask server
::

    > python application.py

4. Open http://localhost:5000

Flask Application Structure
---------------------------

ImpedanceAnalyzer's structure is a Flask application with the structure shown below.

.. code-block:: python

    \ImpedanceAnalyzer
        \.ebextensions      <-- setup files for executing code on EC2 instances
        \.elasticbeanstalk  <-- config files for setting up Elastic Beanstalk environment
        \application        <-- main module
            \static         <-- folder for static (data, images, js, css, etc.) files
            \templates      <-- contains html templates for pages
            __init.py__     <-- makes this folder a module
            fitModels.py    <-- python functions for fitting equivalent circuit and physics-based models
            views.py        <-- responsible for routing requests to different pages
        \docs               <-- contains files associated with this documentation
        application.py      <-- .py file for starting Flask app
        config.py           <-- config file for Flask app
        requirements.txt    <-- list of python packages used to setup environment

Flask API
^^^^^^^^^

The views module contains the routing structure for the flask application

.. automodule:: application.views
    :members:

Functions for Model Fitting
---------------------------
At the heart of ImpedanceAnalyzer is the ability to fit models to data:

Physics-based Models
^^^^^^^^^^^^^^^^^^^^

.. automodule:: application.fitPhysics
    :members:

Equivalent Circuit Models
^^^^^^^^^^^^^^^^^^^^^^^^^

.. automodule:: application.ECfit.fitEC
    :members:

.. automodule:: application.ECfit.utilities
    :members:

Circuit elements can be added to the circuit_elements.py

.. automodule:: application.ECfit.circuit_elements
    :members:
