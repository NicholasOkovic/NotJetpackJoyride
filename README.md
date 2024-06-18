README file of the things I(Nick) have worked on for  Not Jetpack Joyride
(other small details such as value adjustment & iterations of bug fixes were not mentioned)


 - On this project I did the particles for the Coin collection, and the code and effects for both the zappers & lasers



*A Rundown of what I did*

Coin Collection particle effect:
 - Particle for when a coin is collected
 - Used Unity particle system 
 - Image was obtained online then had its background removed


Zappers & Rotating Zappers:

![image](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/74a7c02a-b0ae-474b-89ad-eb373bd4fed2)   ![image](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/6c7a4385-d597-418d-9e72-afffe794278e)






  -Code-
 
 - Take in the if rotating, min & max length, and min & max rotation
(a random number will be chosen inbetween these values)

 INSTANTIAZTEOBJECT
 - instantiate Zapper
 - Adjust end cap position to length given

 - determine if its a rotating zapper or not, if so adjust color and apply rotating component

 - Apply left moving component
 - Scale box collider to length
 - Apply rotate to zapper

 - Firing the renderer for effects used to be inside the zappers code, but was moved for
scalablity to be able to be used in other objects that shoot lines forward(ex: lasers)

  -Effects-
 - End caps of the zappers(both ends of zapper) obtained online, had their background removed, and rotated

![Zapper](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/b4de254e-644b-40a5-a319-fe2a98585df7) ![RotatingZapper](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/62696888-6940-486c-a058-ef7c378f54bf)


Lasers:
  -Code-

 - Recieves MovementVarience(how far the lasers move), Windup(time before laser fire), 
ActivationLength, Ease(how fast the lasers ease into frame), WindupWidth(the tiny laser width), Activation Width

 UPDATE
 - Timer
 - Lerp both ends of the laser

 AWAKE
 - get all relevant objects
 - save starting positions of leasers
 - Invoke LaserWindup

 LASERWINDUP
 - enble line renderer with windup width
 - Invoke LaserActivation

 LASERACTIVATION
 - line renderer width changes to active width
 - activate box collider
 - Invoke LaserDeactivation

 LASERDEACTIVATION
 - Disable line renderer and collider
 - lasers new position being set to its original
 - Destroy Objects

  -Effects-
 - End caps of the lasers(both ends of laser) obtained online, had their background removed


FireLineRenderer:

 - Recieves startpoint, endpoint, and the line renderer component
 - Draws the 2d ray from start to end

 -Effects-
 - Line renderer component added added to objects
 - Color set to either red(with falloff of white) for laser
or yellow (with falloff of white) for zappers(yellow changed to orange if its a rotating zapper)

 - Material added to line renderer(unique material per laser)
 - Materials made with texture from photoshop, then edited using the shader graph in unity packages
Texture is being multiplied by time and passes through "Tiling and Offset", applied to Sample Texture 2D 
and applied to fragments basecolors along with its alpha


Bug Fixes:
 - Bug fixes for the lasers & zappers

 - Rocket trail size reduced

 - Background UI no longer interactable when theres pop-ups(disable background UI Functionality, when pop-up active)

