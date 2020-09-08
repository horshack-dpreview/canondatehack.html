# datehack.html - Browser-based app for setting date/time on Canon R5/R6

This is small web-based app that allows you to quickly change the date of
your Canon R5/R6 over WiFi using Canon's Canon Control API (CCAPI). This can
be used as part of the Canon R5/R6 "hack" that allows for unlimited video
recording times from bypassing the camera's thermal management logic. You
can see the details of this workaround at the following link. Scroll down
to the "In short, here are my hack, step by step" section:

https://www.visionrouge.net/canon-r5-overheating-hack-solved/

**WARNING: Bypassing Canon's thermal management can cause your camera to
operate at temperatures much higher than it was designed to accommodate.
This workaround may cause permanent damage to your camera. Use this
workaround at your own risk**

## URL

http://www.testcams.com/ccapi/datehack.html

## Requirements

1. Canon R5/R6. Other Canon cameras with CCAPI-support will work but there's
   not much point in using this utility on those cameras except for testing
   the logic. Those cameras include: T8i, 1DX Mark III, M200, M6 Mark II,
   90D, SL3, RP, SX70 HS, G5 X Mark II, G5 X Mark III    
2. A browser that provides an option to disable CORS policy security.
   This app communicates with the camera over TCP/IP. Since the
   camera's IP address is different than the IP/domain you are running
   this page from, the browser's cross-domain CORS security will prevent
   the app from communicating with the camera as a security measure to
   prevent cross-domain data violations.
   
## Running Google Chrome with CORS security disabled

Run the following invocation from the command line/terminal to launch Chrome
with its web security disabled. Include the quotations. Do not use this browser
session for anything other than running this page - it disables the normal
cross-domain security measures and will put your data at risk if you use it
for general web browsing.

```
Windows: "C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" --disable-web-security --user-data-dir=%homepath%\chromenosecurity
Mac: "/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --disable-web-security --user-data-dir=~/.chromenosecurity 
Linux: chrome --disable-web-security --user-data-dir=~/.chromenosecurity   
```

## Camera Setup

Enabling the Control API requires a one-time activation using Canon's
CCAPI activation tool, which is distributed on Canon's developer
website at https://developercommunity.usa.canon.com/canon?id=sdk_download.

1. Connect the camera via USB to computer and run the CCAPI activation tool.
   Disconnect the camera from the computer when complete.
2. Go to "Wireless communication settings" in the camera, select "Wi-Fi
   settings", then "Camera Control API". You'll need to provide the info for
   your local wireless network if you haven't already done so - you can use
   WPS if your router supports it to get through the setup faster. You can
   optionally specify a static IP address, which may make it easier to use
   this utility since you'll always know the camera's IP address rather than
   having to check the camera (although most routers will reuse the same IP
   address for a given MAC address).. At the last step of the process the
   camera will display a URL you can access; enter that URL on your computer
   to finalize the setup and verify everything is working.
3. When done you'll also want to enable "Auto connect" in the same Camera
   Control API menu of the camera; that way the camera will automatically
   connect to your network and enable the CCAPI whenever you turn the camera
   on. You may need to temporarily disconnect from CCAPI in the camera in
   order to turn "Auto connect" on.
