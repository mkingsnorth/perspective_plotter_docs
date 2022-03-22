#####################################
Tips and Troubleshooting
#####################################

.. note::
    If you're having any trouble and it is not answered here, don't hesitate to :ref:`contact us<Contact>`.

========================================================
Setting up perspective lines
========================================================

.. figure:: images/good_lines.jpg

    On the left, the perspective lines are too close together to provide enough information to the add-on for a good camera match.  On the right, the perspective lines are further apart and provide the best information when estimating camera orientation.

When setting up perspective lines try and choose lines in an image that are far apart.  This will give the add-on the best information to estimate camera position.  Lines that are close together can be too parallel and perspective errors can be introduced.

======================================================
Invalid Configuration
======================================================

.. image:: images/invalid_config.jpg
    :alt: Invalid Configuration

The add-on uses geometry calculations described |here| to estimate camera rotation, angle and focal length.  

This calculation cannot be done in certain scenarios. For instance, if the vanishing points are too parallel or fall outside the :ref:`Principal Point` of the camera lens.  

If this is the case, the add-on temporarily marks the configuration as invalid and stops moving the camera.  

To rectify this, keep adjusting the perspective axes until a valid configuration occurs.

.. |here| raw:: html

   <a href="https://www.coursera.org/lecture/robotics-perception/how-to-compute-intrinsics-from-vanishing-points-jnaLs" target="_blank">here</a>

======================================================
I cannot see the P.Plotter Panel after installation
======================================================

The Panel will only appear if you are |viewing though the Active Camera|.


.. |viewing though the Active Camera| raw:: html

   <a href="https://docs.blender.org/manual/en/2.79/editors/3dview/navigate/camera_view.html" target="_blank">viewing though the Active Camera</a>


=====================================================
How do I zoom in and move around the camera image?
=====================================================

.. image:: images/pan_zoom.gif
    :alt: Invalid Configuration

Use the mouse wheel to zoom in to the viewing border to see the image more clearly.  You can pan along the image by pressing *shift* and using the middle mouse button to click and drag along the image.

==========================================================================================================
How do I get the camera view back if I accidentally click and rotate outside?
==========================================================================================================

Press the '0' numpad key to get the Camera view back. *Perspective Plotter* will have temporarily stopped plotting: Press the **Plot Perspective** button again to resume editing.

======================================================
Resetting individual parameters
======================================================

You can reset any parameter to its default in Blender by hovering over the parameter with the mouse and pressing the **backspace** key.

======================================================
Does this add-on support lens distortion models?
======================================================

As Blender applies Lens distortion in post production, at the moment this is a future requirement and you would need to look at Blender's Movie Clip editor to resolve the distortion before doing a camera match.


============================================================================================================
My control points appear to wobble.  What could this be?
============================================================================================================

For very small or very large scale scenes, such as an aerial photo, Blender's Units settings may need to be adjusted so that the add-on can calculate the right level of accuracy.  

Go to the *Scene* -> *Units* section of Blender's properties tab, and look at the |Unit Scale| setting.  Change this to larger or smaller orders of magnitude (e.g. 10 or 0.1) will change the relative scale of units in Blender.  For instance, an aerial photo may benefit from having this setting changed to 10.  Note that when importing the objects into other scenes, they may need to be scaled up/down by the Unit Scale setting to match the other scene.

.. image:: images/unit_scale.jpg
    :alt: Unit Scale Setting

.. |unit scale| raw:: html

   <a href="https://docs.blender.org/manual/en/latest/scene_layout/scene/properties.html#units" target="_blank">Unit Scale</a>

============================================================================================================
I cannot make the vanishing Points match a 2D sketch or photo
============================================================================================================

If it is a sketch of a concept, or an image that may be distorted/cropped, it may be something to do with the image not being entirely perfect.  Double check that you are happy that the sketch's vanishing points are accurate.

Try different vanishing point modes: If in 2-point mode, try experimenting with the position of the :ref:`Principal Point` (which is used to estimate the 3rd vanishing point) or switching to another perspective mode.  

If in 1-point perspective mode, try experimenting with the :ref:`Focal Length` which has to be provided in this mode.

======================================================
No, I've checked, and they don't match!
======================================================

:ref:`Get in touch<Contact>` and we'll be very happy to check the add-on for any bugs.

