# **Overview**
“UIDialogBox” is an asset for creating dialog box based on your requirement. You can preset the attribute of the dialog box from the unity editor, or creating from unity “C#” script. Currently you can create it with “2 – Button” or “3 – Button” based on your requirement. So without further due, lets deep dive on the asset.
***
# **Types of Dialog Box:**
* **2 – Button:** The 2nd button of the dialog box is set to “Cancel” for closing the dialog box. You can preset anything on 1st button based on your requirement. Example could be for purchasing a following item or canceling it.
* **3 – Button:** The 3rd button of the dialog box is set to “Cancel” for closing the dialog box. You can preset anything on the 1st & 2nd button based on your requirement. Example could be “Apple Purchasing” mechanism for “Non – Consumable” product. You can either “Purchase”, “Restore” or “Cancel” your transaction based on the user choice.
***
# **How to use it?**
Just download the **UIDialogBox.unityPackage** from the following "Git", and import it to your "Unity Project".

***
# Configuring Dialog Box from Unity Editor
## 2 – Button
1.	Lets’ drag and drop our “**UIDialogBox**” prefab from our “**Project**” window to our “**Hierarchy -> Canvas**”. 

![](https://github.com/tashfiq103/UIDialogBox---UnityPackage/blob/master/Screenshot/Step%20-%201.png)
***

2.	Let’s create “DialogBoxTest” script for testing purpose. After creating and writing down the following script, let’s create “DialogBoxTestObject” in our “Hierarchy -> Canvas” and add our script to the following object.

```C#
using UnityEngine;

public class DialogBoxTest : MonoBehaviour {

    public void Purchase(){

        Debug.Log ("Purchase Succesful");
    }

    public void Restore(){

        Debug.Log ("Restore Purchase Succesful");
    }

    public void Cancel(){

        Debug.Log ("Purchase Cancel");
    }
}
```
![](https://github.com/tashfiq103/UIDialogBox---UnityPackage/blob/master/Screenshot/Step%20-%202.png)
***
	
3.	Now, let’s create our 1st dialog box by setting the “Size” to “1” of “Dialog Box” under the “UIDialogBox” script. Now let’s fill the attribute of the dialog box using the following picture.

![](https://github.com/tashfiq103/UIDialogBox---UnityPackage/blob/master/Screenshot/Step%20-%203.png)
***

4.	Now, let’s create a “Purchase Box” in our canvas and add our “OnClick” target to our “UIDialogBox.CreatePresetDialogBox” and set the parameter to the name of our dialog box we want to call. As our sated dialog box name is “PREMIUM_2B_USER”, we are passing it as our parameter. Now let’s tap on the “Purchase Box” to create our first preset dialog box.

![](https://github.com/tashfiq103/UIDialogBox---UnityPackage/blob/master/Screenshot/Step%20-%204.png)
***

5.	Now, if we click on the “Yes” button, you can see at the console that “Purchase Successful” has shown and the dialog box got closed automatically.
 
![](https://github.com/tashfiq103/UIDialogBox---UnityPackage/blob/master/Screenshot/Step%20-%205.png)
***

## 3 – Button 
There are only few difference between these 2 types, so I am going to show where the difference is going to be.
1.	Let’s create another preset dialog box with 3 – button.

![](https://github.com/tashfiq103/UIDialogBox---UnityPackage/blob/master/Screenshot/Step%20-%206.png)
***
2.	Now if you follow the previous step from “2-4” from creating “2 – Button Dialog Box”. You will find the output like this.

![](https://github.com/tashfiq103/UIDialogBox---UnityPackage/blob/master/Screenshot/Step%20-%207.png)

***

# Configuring Dialog Box from Unity C# Script:
•	Let’s modify our “DialogBoxTest” script to the following one that has given below.
•	That’s it, just hit on the play button on the unity editor and you will see a “2 – Button” Dialog box ha just created in the scene. Now try to create a “3 – Button” dialog box.

```C#
using UnityEngine;
using UnityEngine.Events;
using System.Collections;
using System.Collections.Generic;

public class DialogBoxTest : MonoBehaviour {

    void Start(){

        /*
            Keeping an initial delay so 
            the settings get time to finish 
            its configuration
        */
        StartCoroutine (CreateCustomDialogBox());
    }

    public IEnumerator CreateCustomDialogBox(){

        yield return new WaitForSeconds (1.0f);

        UIDialogBox.Instance.CreateCustomDialogBox2B (
            "Premium User",
            "Get your premium skin in 1$",
            "Purchase",
            new UnityAction (Purchase),
            "Cancel",
            null
        );
    }

    public void Purchase(){

        Debug.Log ("Purchase Succesful");
    }

    public void Restore(){

        Debug.Log ("Restore Purchase Succesful");
    }

    public void Cancel(){

        Debug.Log ("Purchase Cancel");
    }
}
```
***

If your following scene allow different screen orientation (Portrait/Landscape) for “Android/iOS” device. Then it is highly recommended to enable this setting. But if your screen has only one screen orientation, then just keep it disabled. Also the following setting only available when your building for “Android/iOS”, so don’t worry about any types of build.
***
![](https://github.com/tashfiq103/UIDialogBox---UnityPackage/blob/master/Screenshot/Step%20-%208.png)

***

You can also change the dialog box background, button background and the font using the following section.
***
![](https://github.com/tashfiq103/UIDialogBox---UnityPackage/blob/master/Screenshot/Step%20-%209.png)




