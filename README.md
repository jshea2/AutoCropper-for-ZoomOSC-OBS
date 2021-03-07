<img src="https://user-images.githubusercontent.com/70780576/110203165-5f21c000-7e21-11eb-942b-c72140d79f2f.png" width="400">

Standalone application that auto-crops a gallery view of ZoomOSC into individual OBS scenes.

*This application is an extension of "[OSC for OBS v.2.2](https://github.com/jshea2/OSC-for-OBS)". Same OSC Commands plus AutoCropping*

### [Download Now]()

<img width="299" alt="Screen Shot 2021-03-06 at 9 18 27 PM" src="https://user-images.githubusercontent.com/70780576/110230699-8f239e80-7ec7-11eb-8e8f-d152268d9306.png">


# Setup
- Download [*AutoCropper-for-ZoomOSC-OBS*]()
- Download [ZoomOSC 4.x](https://www.liminalet.com/zoomosc)
- Download [OBS Studio](https://obsproject.com/download)
- Download [obs-websocket plugin](https://github.com/Palakis/obs-websocket/releases/tag/4.9.0) (4.9 and up)
- In a **ZoomOSC** session...
  - "Update" and "Save" to "performance_config.txt" or manually enter in participants in order of OBS scenes
  - <img width="318" alt="Screen Shot 2021-03-06 at 9 22 32 PM" src="https://user-images.githubusercontent.com/70780576/110229994-5b924580-7ec2-11eb-9872-e3ac2a67f9bf.png">
  - In this example "Show Feed" is you, "Joe" would be Scene "1" in OBS, "Timmy" is Scene "2" in OBS, and etc...
- In **OBS** 
  - import and use the "AutoCropper Template.json" Scene Collection file or...
  -  To manually add more scenes you must name the scene the index of the participant from the "performance_config.txt" file (It starts at 0). 
      -  In the above example "Joe" is index 1, so the scene name should be "1" in OBS. 
  -  Next the source must be a "Display Capture" and the name must append a space with the same index number 
      - Scene: "1" Source: "Display Capture 1"
- In **AutoCropper for ZoomOSC/OBS** 
    - Input your 2nd monitor screen size in "Width" and "Height"
    - "Retina" should be enabled if you have a retina display
    - configure the OBS Websocket inputs to match the plugin
    - configure the ZoomOSC inputs to match the settings in ZoomOSC
      - "Port IN" is the "Transmission Port" from ZoomOSC
      - "Port OUT" is the "Receiving Port" from ZoomOSC
    - "Remove Names" should be enabled if you want the boxes to crop the names from Zoom.
      - *NOTE:* On "Connect" the app automatically sends a "Hide Usernames on Video", so this might not be needed.
    - Configure OSC IN inputs to what your OSC software is sending OSC commands to.
      - *NOTE:* This is only for sending OSC Commands to OBS from **[OSC for OBS](https://github.com/jshea2/OSC-for-OBS)**  
    - Configure OSC OUT to target Application you want the custom command sent to.
    - When Enabled his allows OBS to send the custom OSC message to other applications when a scene is activated.
      - To use/enable this function, change the toggle button to ON Configure the prefix and suffix for how you want your OSC application to receive an OSC string from OBS
      - Example: In OBS when a Scene named "Wide Shot" is activated, Qlab recieves an OSC message "/cue/Wide_Shot/start")
    - Lastly, click "Connect"! 
      - This should open the DevTools window.
      - Make sure you're on the "Console" tab NOT "Elements"
      - This will log all the info that it has sucessfully connected
    - On Connect it will automatically send the following commands to ZoomOSC:
      - Load the "performance_config.txt" file in ZoomOSC
      - Set Gallery View
      - Enable Original Sound
      - Hide Usernames on Video
      - Hide Non Video Participants
      - Set Subscribe in Settings to "All"
      - Get Gallery Order (To start AutoCropping)
- The AutoCropper will dynamically adjust scenes when the gallery view changes in ZoomOSC

# Utilizing *AutoCropper for ZoomOSC/OBS*

- If a participant Turns on or off their video, this will dynamically change their source visibility in OBS
- Feeding each participant into their own OBS scene allows you to nest scenes. This means you can make a new scene and add scene "1" "2" and "4" into a composited scene. 
- Another powerful tool to have for animating position for transitions between scenes is the "[move-transition](https://obsproject.com/forum/resources/move-transition.913/)" plugin.
- See the built-in **[OSC API](https://github.com/jshea2/OSC-for-OBS)** for all available commands to control OBS.
- You can combine this with show control software (like QLab) to control OBS parameters, overlay video with Syphon or NDI
- Check out the video below for what's possible with using QLab, ZoomOSC, OBS, and AutoCropper for ZoomOSC/OBS:
    - <a href="https://youtu.be/pR-0IUBodrc" target="_blank"><img src="http://img.youtube.com/vi/pR-0IUBodrc/0.jpg" 
alt="NodeOBS-ZoomOSC-Autocropper DEMO Video" width="200" border="10" /></a>



# Acknowledgements
- Powered by Bernie Bernstien's [AutoCropper code](https://github.com/bbernstein/izzy-crop-zoom-gallery)
- This was also inspired by [Other Lonestar](https://www.youtube.com/watch?v=WUJUGsxdMEQ)'s Node-Red version.

### Join The Discord Community for Support
<a href="https://discord.gg/FJ79AKPgSk">
        <img src="https://img.shields.io/discord/308323056592486420?logo=discord"
            alt="chat on Discord"></a>