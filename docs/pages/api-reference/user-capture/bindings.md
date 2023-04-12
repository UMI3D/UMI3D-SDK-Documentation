# Bindings

Bindings are part of the system set up in order to efficiently link objects to users. This system is based on the skeleton present in the browser used. It is possible to declare links between the objects and the parts of the skeleton, in order to let the browser manage the movement of the linked objects, and therefore to save on server update. The bindings of other users known by the browser are also animated locally, thanks to the tracking information transmitted between the browsers.

```cs
UMI3DBinding binding = new UMI3DBinding()
{
    boneType = bone.boneType,
    node = obj.GetComponent<UMI3DAbstractNode>(),
    rigName = rig.rigname,
    isBinded = true,
    offsetPosition = new Vector3(1, 1, 0),
    offsetRotation = Quaternion.FromEulers(90, 0, 0)
}
```

The offsets are both set in the local frame of the bone.
The boolean `isBinded` sets the binding activation. Several bindings with the same object can cohabit if only one of them is active.
In case of binding an object's rig, specifying the rigName property field is needed. In case of this field remaining empty, the Binding will be created for the entire object.

## Adding a binding

The method `AddBinding` of the `UMI3DEmbodimentManager` class returns a new `SetEntityProperty` with the operation of adding a binding to a `UMI3DAvatarNode` object.

## Updating a binding

Each binding can be partially or totally updated. It is possible to create of copy of the existing bindings and to modify the concerns fields. Then, the method "UpdateBinding" of the `UMI3DEmbodimentManager` class will return a new `SetEntityProperty`. It contains the operation of updating a binding at a certain index of the list of bindings of a `UMI3DAvatarNode` object.

For example, in order to make a binding inactive, it only requires to copy the binding to update and to change the boolean field `isBinded` to False.

## Removing a binding

Deleting a binding removes the link between the object concerned and the user's skeleton. The method `RemoveBinding` requires the binding to delete or its index in the list of bindings of the concerned UMI3DAvatarNode object. In addition, it is possible to fix the position of the object in space at the time of deletion.
For that, the method `RemoveBinding` accepts two optionnal parameters : a boolean, to specify the fixing in space, and an `UMI3DAbstractNode` object, which is the relative node to which the debinded object will be placed. The method returns a list of `SetEntityProperty` with the dedicated operations.

## Disable all bindings

It is possible to disable the bindings of a UMI3DAvatarNode object by using the method `UpdateBindingActivation` and specifying the activation boolean. After having disabled the activation by this means, it will be necessary to reuse this method to reactivate them.

## Updating the list of bindings

The method `UpdateBindingList` is used to replace all the existing bindings by a new set.

Each described feature could be use for synchrone and asynchrone users. It is advised to synchronize on the server the movement of binded objects according to the position of the users.
