README file of the things I(Nick) have worked on for the Not Jetpack Joyride game

---

**Other contributors:** 

![image](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/c822852d-919a-49d6-b377-ee0781258936) https://github.com/SleepingDragon0


![image](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/742280df-39a0-47c9-8665-f5733e589e7f) https://github.com/LeahTaurisano 

![image](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/0ac794c1-d76e-4cc7-be9f-8a6e3dc693dc) https://github.com/twdaviss 

![image](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/7c19a2af-05cf-49fa-9c1e-d1d088b4a17c) https://github.com/CultyMarble

![image](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/859b874c-3a0c-44f5-9062-506bad1ea22e) https://github.com/PhiBeo

![image](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/3ddd6336-0f50-485b-8698-ac1541474f4a) https://github.com/MiguelAyala25

---

![Jetpacklaser zapper](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/d71f1adb-e7cb-493d-8afb-487892f6623f)


# How to Play

```
https://github.com/NicholasOkovic/NotJetpackJoyride.git
```

https://unity.com/releases/editor/whats-new/2022.3.23#installs

Launch the scene in Assets > Scenes > MainScenes > 00_Menu


![image](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/ac5d52d2-eb6d-479a-a2b1-85175fcd8326)




# A Rundown of what I did

**Coin Collection particle effect:**

![CoinParticle](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/7298ea32-f5c2-426a-9c34-97934c0993da)

 - Particle for when a coin is collected
 - Used Unity particle system 
 - Image was obtained online then had its background removed


## Zappers & Rotating Zappers:

![Zapper](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/b4de254e-644b-40a5-a319-fe2a98585df7) ![RotatingZapper](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/62696888-6940-486c-a058-ef7c378f54bf)


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



## Lasers:
![Lasers](https://github.com/NicholasOkovic/NotJetpackJoyride/assets/139954443/dc392a59-7693-43b6-a4f7-94d98b2579ff)


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



## FireLineRenderer:

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



## Bug Fixes:
 - Bug fixes for the lasers & zappers

 - Rocket trail size reduced

 - Background UI no longer interactable when theres pop-ups(disable background UI Functionality, when pop-up active)






