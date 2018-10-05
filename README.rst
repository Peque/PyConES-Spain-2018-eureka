Eureka!
*******

|logo|

Through experimentation, math and, of course, Python, we will do science! We
will explore the symbolic calculus, the numeric and even the machine learning
field.

The goal is to measure the terrestrial gravity and validate the equations of
the uniformly accelerated motion.


Setup
=====

Use `Pipenv <https://pipenv.readthedocs.io/>`__ to setup your virtual
environment and install all the required dependencies::

   pipenv sync

Then run Jupyter notebook with::

   pipenv run jupyter notebook


Colab
=====

You can run the whole notebook online without the need to install any
dependencies in your local machine using `Google's Colaboratory
<https://colab.research.google.com>`__, but that will require some tweaks.

Use a code cell to install the required dependencies::

   !pip install bokeh numba

Upload all the ``.wav`` files to your environment and all the images under
``/images/`` too. Then, when running code cells, make sure to remove the image
or audio file paths if any.

If you cannot visualize your Bokeh figures, make sure to define this function
right after the first Bokeh imports in the notebook:

.. code:: python

   from bokeh.plotting import show as show_bokeh


   def show(figure):
       output_notebook()
       show_bokeh(figure)

If you cannot visualize your Plotly figures, make sure to call this function from the same cell where you are plotting the figure:

.. code:: python

   def configure_plotly_browser_state():
       import IPython
       display(IPython.core.display.HTML('''
           <script src="/static/components/requirejs/require.js"></script>
           <script>
             requirejs.config({
               paths: {
                 base: '/static/base',
                 plotly: 'https://cdn.plot.ly/plotly-latest.min.js?noext',
               },
             });
           </script>
       '''))


.. |logo| image:: ./images/pycones-logo.svg
   :width: 150
