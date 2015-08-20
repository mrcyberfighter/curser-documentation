======
Curser
======

	curser is a python module based and complementary to pygame,                           
	who will give you analog functions as the turtle module implement                      
	in a pygame display to make easier the generation and the animation of                 
	forms like polygons, spirals, fractals and so soon.                                    
	With abstraction of the coordinates computing throught an curser object analog         
	to the turtle whose orientation is setable throught rotation functions                 
	to the left or to the right from the number of wanted degrees with progressiv          
	animated stroke drawing or not animated functions whose color and width is             
	configurable.   
	
	.. note:: usage of curser.
    
	  curser does not work in interactive mode like the turtle module.
	  So you must define the code to execute on the curser in a file and run it.
	  

:mod:`curser` -- curser is a module based and complementary to pygame: an turtle implementation for the pygame module.
======================================================================================================================
.. module:: curser

:platform: Linux, Windows
:synopsis: curser is a module based and complementary to pygame: an turtle implementation for the pygame module.
	  

.. moduleauthor:: Eddie Bruggemann <mrcyberfighter@gmail.com>

	
	  
-----------------------------
Instantiate the Curser object
-----------------------------

.. class:: Curser(start_x,start_y,start_angle=0,color=(0,0,0),bg_color=(255,255,255),stroke_width=1,curser_down=True)
    
    Create a curser at position (start_x,start_y) pointed in direction start_angle with which you can drive forms as an turtle in an pygame display.
    
    :argument start_x: Start x coordinate from the curser position in the display.
    
    :argument start_y: Start y coordinate from the curser position in the display.
    
    :argument start_angle: Start orientation from the curser, 0 per default. Which orient the curser to 3 o'clock.
    
    :argument color: Color from the stroke which the curser will drive and from the curser itself.
    
    :argument bg_color: Display background color.
    
    :argument stroke_width: Width of the stroke the curser will drive.
    
    :argument curser_down: Boolean value to set if the curser is down: ready to drive.
    
    .. note:: Settings.
    
      All this settings are changeable with the appropriate methods from the Curser object.
      
----------------------------
Curser object moving methods
----------------------------
      
.. method:: Curser.mv_right(angle)
  
  turn the curser right from argument angle degrees and update the current direction.
  
  :argument angle: Angle in degrees to turn the curser to the right. 
  
  
.. method:: Curser.mv_left(angle)
  
  turn the curser left from argument angle degrees and update the current direction.
  
  :argument angle: Angle in degrees to turn the curser to the left. 
  
.. method:: Curser.mv_forward(px)

  Move the curser forward in the current direction from px pixels.
  
  :argument px: Pixels to move the curser forward.
  
.. method:: Curser.anim_forward(px,speed=0.0001) 

  move the curser forward in current direction from one pixel every speed seconds (or fraction) from px pixels far what create an stroke drawning animation effect.
  
  :argument px: the number of pixels to move the curser forward.
  
  :argument speed: the time for moving forward from one pixel.
  
.. method:: Curser.mv_backward(px)

  Move the curser backward in the current opposite direction from px pixels.
  
  :argument px: Pixels to move the curser backward.  
  
.. method:: Curser.anim_backward(px,speed=0.0001) 

  move the curser backward in the opposite current direction from one pixel every speed seconds (or fraction) from px pixels far what create an stroke drawning animation effect.
  
  :argument px: the number of pixels to move the curser backward.
  
  :argument speed: the time for moving backward from one pixel.  
  
.. method:: Curser.get_coords_forward(px)

  return the coordinates for a forward moving from px pixels without drawing a stroke or move the curser.
  
  ! Use this method with your own coordinates container.
  
  :argument px: The number of pixels to get the coordinates in the forward direction.
  
.. method:: Curser.get_coords_backward(px)

  return the coordinates for a backward moving from px pixels without drawing a stroke or move the curser.
  
  ! Use this method with your own coordinates container.
  
  :argument px: The number of pixels to get the coordinates in the backward direction.  
  

-----------------------
Curser managing methods
-----------------------

.. method:: Curser.return_curser()

  Switch the curser in inverse direction.
  
.. method:: Curser.curser_up()

  Raise the curser up and any curser moving method will not draw but the direction changings are effectiv.
  
  ! This method does not hide the curser.

.. method:: Curser.curser_down()

  Put the curser down any moving method will draw on the display. 
  
  ! This method do not show the curser if he is hidden.

.. method:: Curser.set_curser_pos(x,y)

  set the curser position to the coordinates x,y.
  
  :argument x: The x coordinate component of the position to set the curser.
  
  :argument y: The y coordinate component of the position to set the curser.
  
.. method:: Curser.get_curser_pos()

  return the current curser position as an tuple (x,y).
  
.. method:: Curser.show_curser()

  Show the curser but does not put him down.
  
  ! The curser is visible per default.
  
.. method:: Curser.hide_curser()

  Hide the curser but does not raise him up, it is simply to hide the curser for driving.
  
  
------------------------------
Curser object settings methods
------------------------------

.. method:: Curser.set_stroke_color(color)

  set stroke and curser color to the argument color which must be an 3-elements tuple (red,green,blue).
  
  With values between 0 and 255 representing the intensity from the color.
  
  :argument color: An 3-elements tuples (red, green, blue) representing the color to set. 

.. method:: Curser.get_stroke_color()

  return the current stroke and curser color as (red,green,blue) tuple.
  
.. method:: Curser.set_stroke_width(stroke_width=1)

  set the stroke width to the stroke_width argument in pixels.
  
  ! The curser size will increase or decrease if you change the stroke width.
  
  :argument stroke_width: width of the stroke.
  
.. method:: Curser.get_stroke_width() 

  return the current stroke width.
  
.. method:: Curser.set_bg_color(bg_color)

  Change the display background.
  
  ! You have to set the show_hook() method in the mainloop to make it effectiv if you work with it.
  
.. method:: Curser.get_bg_color()

  return the current display background color as (red,green,blue) tuple.
  
--------------------
Miscellaneous method
--------------------

.. method:: Curser.show_hook()

  Hook method to set in the pygame mainloop if you use it, this is the core for displaying the curser and the driven strokes.
  
  