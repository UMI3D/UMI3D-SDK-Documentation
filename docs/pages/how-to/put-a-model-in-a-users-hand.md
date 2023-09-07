# Put a model in a user's hand

Enrich user interactions by letting them pick up object in the environment and carry them.

## Set up the pickable object

The object should have an UMI3DModel component on it.

## Define a binding between the user's hand and the object

You need to create a binding and to dispatch it. You can use the BindingManager to that end.

```cs
using umi3d.common.userCapture;
using umi3d.edk;
using umi3d.edk.binding;
using umi3d.edk.userCapture.binding;

using UnityEngine;

public class BindModel : MonoBehaviour
{
    private UMI3DModel modelToPick;

    private void Start()
    {
        modelToPick = GetComponent<UMI3DModel>();

        UMI3DServer.Instance.OnUserJoin.AddListener((user) => Bind(user.Id()));
    }

    public void Bind(ulong userId)
    {
        BoneBinding binding = new BoneBinding(modelToPick.Id(), userId, BoneType.RightHand) // create between model and the user's hand
        {
            syncPosition = true,
            syncRotation = true,
        };

        var operations = BindingManager.Instance.AddBinding(binding); // add the binding through the manager 

        Transaction t = new Transaction(reliable: true);
        t.AddIfNotNull(operations);
        t.Dispatch();
    }
}
```

This script will put the model at the user's hand and will synchronise the model position and rotation with those of the user's hand.

!!! warning Local computations
    Binding are computed locally on the browsers, so the object is still at its previous position from the environment point of view.
