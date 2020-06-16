# StreamSwitcher
Allows MediaStream to switch tracks without setting srcObject this allows MediaRecording to continue recording

## Problem
The MediaRecorder is designed to stop recording when you switch streams during recording.

## Solution
Use RTCPSender to switch stream without MediaRecorder to stop recording. Another solution would be using MediaSourceBuffers but that is way more error sensitive in case of different codes etc.. 

## Result
A stream where you switch for instance camera with screenshare and back without need to stop and start the MediaRecorder

## Resource
- https://discourse.mozilla.org/t/switch-stream-in-media-recorder/27619/3
- https://stackoverflow.com/questions/59846230/mediarecorder-switch-video-tracks
