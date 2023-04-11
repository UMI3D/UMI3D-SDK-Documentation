# API Reference

## Generated documentation

Automatically generated documentation from code is available [here](https://umi3d.github.io/UMI3D-SDK/index.html).

## Modules

UMI3D is composed of four modules:

1. [Core](./Core)
2. [InteractionSystem](./Interaction-System)
3. [UserCapture](./UserCapture)
4. [Collaboration](./Collaboration)

More API descriptions to come soon.

![image.png](./img/architecture.png)

## Packages

The SDK is exported in three packages:

- Common: Contains all the UMI3D network standardization
- EDK: Contains all classes for UMI3D environment design and hosting on a server
- CDK: Contains all classes for UMI3D environments access through a browser

To develop an environment you'll need Common+EDK, to develop a browser you need Common+CDK.