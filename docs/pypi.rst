scikit-neuralnetwork
====================

Deep neural network implementation without the learning cliff!  This library implements multi-layer perceptrons as a wrapper for the powerful ``pylearn2`` library that's compatible with ``scikit-learn`` for a more user-friendly and Pythonic interface.

**NOTE**: This project is possible thanks to the `nucl.ai Conference <http://nucl.ai/>`_ on **July 20-22**. Join us in **Vienna**!

|Documentation Status| |Code Coverage| |License Type| |Project Stars|

----

Features
--------

Thanks to the underlying ``pylearn2`` implementation, this library supports the following neural network features, which are exposed in an intuitive and `well documented <http://scikit-neuralnetwork.readthedocs.org/>`_ API:

* **Activation Types —**
    * Nonlinear: ``Sigmoid``, ``Tanh``, ``Rectifier``, ``Maxout``.
    * Linear: ``Linear``, ``Gaussian``, ``Softmax``.
* **Layer Types —** ``Convolution`` (greyscale and color, 2D), ``Dense`` (standard, 1D).
* **Learning Rules —** ``sgd``, ``momentum``, ``nesterov``, ``adadelta``, ``rmsprop``.
* **Dataset Types —** ``numpy.ndarray``, ``scipy.sparse``, coming soon: iterators.

If a feature you need is missing, consider opening a `GitHub Issue <https://github.com/aigamedev/scikit-neuralnetwork/issues>`_ with a detailed explanation about the use case and we'll see what we can do.


Installation & Testing
----------------------

If you want to use the latest official release, you can get it from PYPI directly::

    > pip install scikit-neuralnetwork

This contains its own packaged version of ``pylearn2`` from the date of the release (and tag) but will use any globally installed version if available.

Then, you can run the samples and benchmarks available in the ``examples/`` folder.


Getting Started
---------------

The library supports both regressors (to estimate continuous outputs from inputs) and classifiers (to predict labels from features).  This is the ``sklearn``-compatible API:

.. code:: python

    from sknn.mlp import Classifier, Layer

    nn = Classifier(
        layers=[
            Layer("Rectifier", units=100),
            Layer("Linear")],
        learning_rate=0.02,
        n_iter=10)
    nn.fit(X_train, y_train)

    y_valid = nn.predict(X_valid)

    score = nn.score(X_test, y_test)

The `generated documentation <http://scikit-neuralnetwork.readthedocs.org/>`_ as a standalone page where you can find more information about parameters, as well as examples in the `User Guide <http://scikit-neuralnetwork.readthedocs.org/en/latest/guide.html>`_.

----

|Documentation Status| |Code Coverage| |License Type| |Project Stars|

.. |Documentation Status| image:: https://readthedocs.org/projects/scikit-neuralnetwork/badge/?version=latest
    :target: http://scikit-neuralnetwork.readthedocs.org/

.. |Code Coverage| image:: https://coveralls.io/repos/aigamedev/scikit-neuralnetwork/badge.svg?branch=master
    :target: https://coveralls.io/r/aigamedev/scikit-neuralnetwork?branch=master

.. |License Type| image:: https://img.shields.io/badge/license-New%20BSD-blue.svg
    :target: https://github.com/aigamedev/scikit-neuralnetwork/blob/master/LICENSE

.. |Project Stars| image:: https://img.shields.io/github/stars/aigamedev/scikit-neuralnetwork.svg
    :target: https://github.com/aigamedev/scikit-neuralnetwork/stargazers    
