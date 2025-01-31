title: Computing the convex hull area of a 2D binary particle
slug: computing-the-convex-hull-area-of-a-2d-binary-particle
timestamp: May 3 2011 4:07
categories: examples
author: "Jean-Patrick Pommier" <jeanpatrick.pommier@gmail.com>
---

Crossposted from `DIP4FISH
<http://dip4fish.blogspot.com/2011/05/computing-convex-hull-area-of-2d-binary.html>`__

A particle class is needed to handle the chromosomes extracted from a metaphase image.

.. image:: /media/files/images/blog/2011/convex_original.png
   :width: 66%
   :align: center

For this very beginning, the class only handles the counterstain image (DAPI),
it is possible to :

1. display a particle vertically,
2. compute the ratio between the particle area and the convex hull area, in
   order to distinguish between single chromosomes and overlapping chromosomes.
   The convex hull area is computed with a `funny formula
   <http://en.wikipedia.org/wiki/Polygon_area#Properties>`__.

.. figure:: /media/files/images/blog/2011/AnalyseParticule.png
   :width: 66%
   :align: center

    Blue curve:orientation curve for the original particle image (top left).
    Green curve: orientation curve after high pass filtering (top right).

With two features as the particle area and the ratio between the particle area
and the convex hull area, it should be possible to start to classify the
particles into four categories:

# non overlapping chromosomes,
# overlapping chromosomes,
# nuclei, 
# remaining small stuffs .

`scikit-learn <http://scikit-learn.sourceforge.net/>`__ may be considered.

`The script written to test the class
<https://docs.google.com/uc?id=0B4TdqXWu2MOWMGU0YzAxNTgtNDJmYi00YjQ2LWFjN2MtYjFjY2YzNmRjYzg1&export=download&hl=en>`__,
instanciates two particle objects, rotates  them and calculates the "convexity"
ratio. To use it with your images, modify the path to the image, numpy, scipy,
pylab, pymorph, mahotas must be installed.

