This plugin allows for a simple way to turn any 3D game into a therapy game for amblyopia. It works by rendering some actors as red or blue, depending on which eye is sick, and rendering anything else using dark tones: this will allow the red (blue) actors to only be visible to the desired eye.

IMPLEMENTATION STEPS

0) Add the AmblyopiaTherapy folder into your project’s Plugins folder (create the Plugins folder yourself if one is not already present).
1) In project settings, set “Custom Depth-Stencil Path” to “Enabled with stencil”.
2) For each level in the game, create a new PostProcessVolume, set Unbound to true, add under Post Process Materials M_PP_Blacken and add a tag “DarkeningPP”.
3) For each mesh (skeletal or static) that should be rendered as obscured (generally all meshes that one does not wish to turn red/blue) change “Render CustomDepth Pass” to true, and     
   “CustomDepth Stencil Value” to 1.
4) For each actor that one wishes to make red/blue assign the component “AmblyopiaMatAssigner”.
5) Position the widget “WB_SelectAmblMode” inside your game’s starting menu.



ADDITIONAL INSTRUCTIONS

_ Make sure not to use any lights that are too bright: the main problem is that if the background around the red/blue object isn’t dark enough, both eyes will be able to see it; also, the 
   light might create a minor lighting glitch around the red/blue objects that are being illuminated.
_ The darkening amount can be modified inside of “M_PP_Blacken”.

