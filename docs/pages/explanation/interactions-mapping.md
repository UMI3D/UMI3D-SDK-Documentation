# Interaction mapping

On the client-side, browsers receive the available interactions and make them available for users.

![image.png](/.attachments/image-a100add9-9cc7-4f26-9289-25b3227d08e5.png =600x)

## Projection

When the user decides to access an interaction tool through selection (e.g. by pointing an object), the `InteractionMapper` looks for available input channels on the used controller and map the interaction to them, enabling the user to maniuplate through the controller's inputs. E.g. by looking at a door handle, the interaction "open the door" is projected on the user controller trigger button that when pressed will open the door.

The server can also request from a browser to force the projection of a tool.

![image.png](/.attachments/image-436d12c9-12ee-45c7-9c9e-3bfe3e530824.png)

## Displayers
Sometimes, an interaction requires specific inputs that cannot be offered physically by a device. (e.g. setting up a float) If such a specific user interface is required, a menu is created as a displayer to enable the user to interact with the parameter setting.

More details in [the specific section](/External/Reference/UMI3D-SDK/Interaction-System/Displayers-&-Menus).

![image.png](/.attachments/image-b93ff991-2c41-4963-aeb6-29b1a96598c0.png)
