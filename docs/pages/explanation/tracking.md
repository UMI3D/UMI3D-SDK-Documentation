# Body tracking

_Partly imported from the powerpoint "Umi3d_2.0". Last updated on 07/12/21._

## User Tracking Frames

![image.png](./img/)

Each browser send tracking data as User Tracking Frames. Each frames contains the position and rotation of the anchor of the skeleton and the relative position, rotation and scale of each bone.

## Tracking Extrapolation

Based on the received tracking frames, movement is reconstructed using extrapolators. The use of extrapolator is caused by the heavyness of user Tracking Frames that cannot be sent at every frames. This reconstrcution ensures a smooth movement as well as a relatively manageable amount of data to send to browsers.

![image.png](/img/)

This reconstruction is done using simple linear extrapolators, but plans are on the way to make better extrapolations.
