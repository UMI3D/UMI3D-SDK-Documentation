# Interaction design

The environment and its available interactions are designed on the server-side. Some of them are independant from available objects and are thus abstract Global Tools (such as answering to a short form), while the other are attached to objects through Interactables (such as pressing a button). Both are presented to clients through the UMI3D network protocol.

![image.png](./img)

## Global interactions

Global interactions are interactions that do not rely on an object. For example, answering to a form.

![image.png](./img)

## Object-focused interactions​ (Interactables)

Object-focused interactions are interactions that are related to an object, such as changing its colour. This interactions are grouped into a single specialized tool, called _Interactable_.

![image.png](./img)

## Interaction transfer

UMI3D Interactions are tools that are related to Events (e.g. trigger, hold) or parameters to set (e.g. a boolean, a float etc..). When a tool is associated to an UMI3D object, it is called an Ineractable. Tools are sent to browsers through the network protocol using UMI3D serialization conventions. When loaded on browsers, Interactable are wrapped up into an InteractableContainer on the scene graph (it has a transform).

![image.png](./img)
