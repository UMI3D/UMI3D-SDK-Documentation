#Install the UMI3D SDK

##Get Unity

Go on the [Unity website](https://store.unity.com/) and select a plan, then download a version compatible with the UMI3D release you want to use.

##Import the SDK

###1 - Get a UMI3D SDK release
Go on the [GitHub releases](https://github.com/UMI3D/UMI3D-SDK/releases) and find the release you want to use. 

###2 - Download the packages
Under "Assets", download the packages files you want to use. 
Note that the source code zips are not required to use UMI3D as thay are already integrated in the packages.
![image.png](/img/get-release-sdk.png)

###3 - Import the packages
For each of the following package, drag and drop the file in the Unity project window.

- _core.unitypackage_
- _dependencies.unitypackage_ 
- If you want to create a UMI3D environment: _edk.unitypackage_; or if you want to create a UMI3D browser: _cdk.unitypackage_
-  The complementary modules you want: _interaction-system.unitypackage_, _user-capture.unitypackage_, _collaboration.unitypackage_ 

![image.png](/img/import-packages.png)

And import everything.

![image.png](/img/import-packages-2.png)

If you want basic scripts to launch a server, also import the _server-starter-kit.unitypackage_ file.