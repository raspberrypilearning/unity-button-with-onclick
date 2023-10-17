
Voeg een 'UI' 'Knop - TextMeshPro' toe. Het is vaak zinvol om de knop als onderliggend object van het GameObject toe te voegen met de methode die zal reageren als er op de knop wordt geklikt. Je kunt een knop toevoegen aan een bestaand Canvas, anders maakt Unity een canvas.

**Tip:** Door een knop toe te voegen, wordt ook een EventSystem aan je Scène toegevoegd als deze er nog niet was. Hiermee worden gebeurtenissen afgehandeld wanneer er op de knop wordt geklikt.

De knop heeft een 'TextMeshPro'-onderliggend object. Stel de tekst in die in de Inspector moet worden weergegeven.

Maak een **public** method op een script dat is gekoppeld aan het GameObject en dat reageert op de klik op de knop. Dit zou een NPC kunnen zijn. Je kunt de methode toevoegen aan een bestaand script of een nieuw script maken.

--- code ---
---
language: cs
---
public class ButtonHandler : MonoBehaviour
{ public GameObject button; // If you want to be able to hide the button

    public void ButtonClicked()
    {
        Debug.Log("Button clicked");
        // Add code for other actions
    
        button.SetActive(false); // Hide the button
    }
} --- /code ---

Voeg optioneel een knopvariabele toe en sleep het Button-object naar de Button-eigenschap van het script in de Inspector. Dit maakt het mogelijk om `SetActive` te gebruiken om de knop te verbergen wanneer er op geklikt wordt.

Selecteer de knop en zoek in de Inspector 'OnClick()' - misschien moet je naar beneden scrollen. Klik op de **+** en sleep vervolgens het GameObject met de methode die je wilt aanroepen naar het vak onder 'Runtime'. Klik op het vervolgkeuzemenu **No Function** en selecteer je script en vervolgens de methode die je wil aanroepen wanneer op de knop wordt geklikt.

**Test:** Speel je scène en zorg ervoor dat de `ButtonClicked()` methode wordt aangeroepen. Het is een goed idee om `Debug.Log()` te gebruiken om de Console af te drukken.

**Fouten oplossen:**

+ Controleer of je methode op een script zit dat is gekoppeld aan een GameObject en dat de OnClick() gebeurtenis voor de knop is verbonden met die methode.
+ Controleer of je een EventSystem GameObject in je Scène hebt. Zo niet, klik met de rechtermuisknop in het Hierarchy venster en voeg er een toe. 

