Issue: Hardware Accelerated Decode: Seeking near the end of a some variable framerate videos never completes
Versions: Chrome 33 and later
OS: Windows 7

We are seeing seeking issues with variable framerate H.264 media when Hardware Accelerated Video Decide is enabled. Issue appears when using both nVidia and AMD GPUs. Seeking in other applications using DXVA2 does not exhibit this behavior, and the issue goes away when hardware accelerated decode is disabled.

Certain variable framerate videos are not able to seek to the last GOP of the video, and attempting to seek there puts the player into a bad state after which any seeking or playback is no longer possible. Other variable framerate videos don't fail completely but exhibit other poor behavior such as seeking to the wrong frames in the last GOP.

Example media that triggers this behavior:

IMG_0155.mp4
original file; recorded with iPhone. 30 frame GOPs. Last IFrame at pts 9610 (16.016s)

driving.mp4 
transcode of IMG_0155.mp4; 60 frame GOPs. Last IFrame also at pts 9610 (16.016s)

driving-iframes.mp4
transcode of IMG_0155.mp4; IFrame only media.

We can provide other media privately if needed.
