# StreamSwitcher
Allows MediaStream to switch tracks without setting srcObject this allows MediaRecording to continue recording.

## [Demo](https://meething.github.io/StreamSwitcher/)

## Problem
The MediaRecorder is designed to stop recording when you switch streams during recording.

## Solution
Use RTCPSender to switch stream without MediaRecorder to stop recording. Another solution would be using MediaSourceBuffers but that is way more error sensitive in case of different codes etc.. 

## Result
A stream where you switch for instance camera with screenshare and back without need to stop and start the MediaRecorder

## How to use it
HTML file
```
<head>
<script src="https://cdn.jsdelivr.net/gh/meething/StreamSwitcher@latest/js/ReplaceableMediaStream.js"></script>
</head>
```
JS file
```
//Setup video with empty stream
var temporaryStream = new MediaStream();
video.srcObject = temporaryStream.remoteStream;

//Change the track from a stream
video.srcObject.replaceVideoTrack(stream.getVideoTracks()[0])//Video
video.srcObject.replaceAudioTrack(stream.getAudioTracks()[0])//Audio

//If not autoplay
video.play();
```

## Resource
- https://discourse.mozilla.org/t/switch-stream-in-media-recorder/27619/3
- https://stackoverflow.com/questions/59846230/mediarecorder-switch-video-tracks
- https://webrtc.github.io/samples/src/content/peerconnection/pc1/
