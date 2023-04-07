## 1	Prerequisite: Creating Unity AssetBundles

### 1.1	Creating an AssetBundle from a FBX file

1.  Create an "AssetBundle" folder, an "Editor" folder and a "FBX” folder
![image.png](/.attachments/image-fefbfa30-d2ae-4617-b05d-b6962266acb4.png)
2. Create a BuildAssetBundle script in the Editor folder and paste the code below inside
```cs
using System.Collections;
using System.Collections.Generic;
using UnityEditor;
using UnityEngine;

public class BuildAssetBundle : Editor
{
    [MenuItem("Assets/ Build AssetBundles")]

    static void BuildAllAsseetBundles()
    {
        BuildPipeline.BuildAssetBundles(@"D:\Dev\UMI3DTutorial\UMI3DTutorial\Assets\Project\Models\AssetBundles", BuildAssetBundleOptions.ChunkBasedCompression, BuildTarget.StandaloneWindows64);
    }
}
```
3. Replace the path in the code so that it references the path of your “AssetBundle” folder
4. Copy your FBX file in the “FBX” folder
![image.png](/.attachments/image-a825e4bb-06cb-458b-af27-5674cec9c846.png)
5. Select your FBX file and at the bottom of the Inspector view, select “New” in the AssetBundle drop down menu, and give the bundle a name (“avatar” here)
![image.png](/.attachments/image-3b17759a-b5df-41c0-b6aa-ccbbb9a29cd3.png)
6. With the FBX file selected, open the “Assets” menu and click on “Build AssetBundles”
![image.png](/.attachments/image-3c00b83d-1066-4037-b8ea-8612979ca110.png)
7. When the build is over, the file will be available in your “AssetBundle” folder
![image.png](/.attachments/image-81290464-a53e-445f-a53d-c913e1394c15.png)
8. In order to load the AssetBundles, create a `LoadBundle` script and paste the code below inside
```cs
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class LoadBundle : MonoBehaviour
{
    AssetBundle myLoadAssetBundle;
    public string path;
    public string objName;
    void Start()
    {
        LoadAssetBundle(path);
        InstantiatedObjectFromBundle(objName);
    }
    void LoadAssetBundle(string bundleUrl)
    {
        myLoadAssetBundle = AssetBundle.LoadFromFile(bundleUrl);

        if (myLoadAssetBundle != null)
        {
            foreach (string n in myLoadAssetBundle.GetAllAssetNames())
            {
                Debug.Log("nom=" + n);
            }
        }
        Debug.Log(myLoadAssetBundle == null ? "Failed to load AssetBundle " : "Load AssetBundle OK");
    }

    void InstantiatedObjectFromBundle(string assetName)
    {
        var prefab = myLoadAssetBundle.LoadAsset(assetName);
        Instantiate(prefab);
    }
}
```
This script loads the file form the path of the folder and the asset’s name. To know the name of the bundle, a debug is visible on the console window, with all the available names
![image.png](/.attachments/image-41cbf074-940a-4afe-8522-49d5ff960a04.png)