
Add a 'UI' 'Button - TextMeshPro'. It often makes sense to add the button as a child object of the GameObject with the method that will respond to the button click.
You can add a button to an existing Canvas otherwise Unity will create a Canvas.

**Tip:** Adding a Button also adds an EventSystem to your Scene if it didn't have one already. This will handle the button click events. 

The button will have a 'TextMeshPro' child. Set the text to be displayed in the Inspector. 

Create a **public** method on a script attached to the GameObject that will respond to the button click. This could be an NPC. You could add the method to an existing script or create a new script.

--- code ---
---
language: cs
---
public class ButtonHandler : MonoBehaviour
{
    public GameObject button; // if you want to be able to hide the button

    public void ButtonClicked()
    {
        Debug.Log("Button clicked");
        // Add code for other actions
        
        button.SetActive(false); // hide the button
    }
}
--- /code ---

Optionally add a button variable and drag the Button object to the 'Button' property of the script in the Inspector. This will allow you to use `SetActive` to make the button hide when it is clicked. 

Select the button and, in the Inspector, find 'OnClick()' - you may need to scroll down. Click on the '+' and then drag the GameObject with the method you want to call into the box below 'Runtime'. Click the 'No Function' drop-down and select your script and then the method you want to call when the button is clicked. 

**Test:** Play your scene and make sure that the `ButtonClicked()` method gets called. It's a good idea to use `Debug.Log()` to print to the console. 

**Debug:** 

+ Check that your method is on a script that is attached to a GameObject and that the OnClick() event for the button is connected to that method. 
+ Check that you have an EventSystem GameObject in your Scene. If not, right-click in the Hierachy and add one. 

