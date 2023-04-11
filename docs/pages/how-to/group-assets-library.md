# Group assets in an asset library

Using assets libraries makes it possible to store the required asset for an environment on the client side. So, it does help a lot with speeding up the loading the same environment several times.

## Define the library

Create a new asset library as a ScriptableObject

![image.png](img/group-assets-library-so.png)

## Configure the library

![image.png](img/group-assets-library-conf.png)

1. Enter the library id. Usually "com.compagny.libraryname"
2. Click on "Now" to update the data value. It is important to click here when you update your library since browsers always look for new version of libraries based on their date.
3. Enter a number of variants. They are different sets of available ressources that could be ajusted to fit the device. For example, there is usually a default variant and an android variant.
4. Enter the name of your variant. Usually default.
5. Enter the path to your variant.
6. Enter the number of files in your library (Optionnal)
7. Enter the list of the format contained in the library

## Add the library to the environment

Then add the `AssetLibrary` to UMI3D Ressources objects that belongs to the library in the specified LibraryKey field that possess.
