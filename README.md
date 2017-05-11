# "WebVR: Getting started with Virtual Reality for the web" - Josephs Lab, Nuremberg Web Week, May 2017

My slides for [Josephs Lab, Nuremberg Web Week, May 2017](http://nueww.de/programm/2017/event/show/151/32441e3c4baeaf750e1fc9b9b89ec10b/). 

## To view the slides

Check them out at: [URL to come soon](#)

Use arrow keys or swipe to move left/right.


## To run locally

```
npm install
npm start
```


## To use the Bluetooth remote control

Load up the Remote page on a Web Bluetooth supporting browser, e.g. Chrome for Android, on the device you want to use 
as a presentation remote: http://localhost:9000/remote.html

Press Connect and (as long as you have the Node server running and Bluetooth enabled on both devices) you should see
a device option called 'Remote'. Select that, wait til it says Connected, then you can use the buttons to send 
commands!


## To deploy (for Peter's reference)

```
./deploy.sh
```
