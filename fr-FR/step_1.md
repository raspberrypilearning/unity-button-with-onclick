
Ajouter un « UI » « Button - TextMeshPro ». Il est souvent judicieux d'ajouter le bouton en tant qu'objet enfant du GameObject avec la méthode qui répondra au clic sur le bouton. Tu peux ajouter un bouton à un Canvas existant, sinon Unity créera un Canvas.

**Astuce :** l'ajout d'un bouton permet également d'ajouter un EventSystem à ta scène si elle n'en avait pas déjà un. Il gère les événements liés au clic sur le bouton.

Le bouton aura un enfant « TextMeshPro ». Définis le texte à afficher dans l'Inspector.

Crée une méthode **publique** sur un script attaché au GameObject qui répondra au clic sur le bouton. Il peut s'agir d'un PNJ. Tu peux ajouter la méthode à un script existant ou créer un nouveau script.

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

Si nécessaire, ajoute une variable bouton et faites glisser l'objet Button vers la propriété Button du script dans l'Inspector. Cela te permettra d'utiliser `SetActive` pour cacher le bouton lorsqu'il est cliqué.

Sélectionne le bouton et, dans l'Inspector, trouve « OnClick() », il se peut que tu aies besoin de faire défiler la page vers le bas. Clique sur le **+** puis fais glisser le GameObject avec la méthode que tu veux appeler dans la case située sous « Runtime ». Clique sur le menu déroulant **No Function** et sélectionne ton script puis la méthode que tu veux appeler lorsque le bouton est cliqué.

**Test :** joue ta scène et assure-toi que la méthode `BoutonClique()` est appelée. Il est conseillé d'utiliser `Debug.Log()` pour imprimer dans la console.

**Déboguer :**

+ Vérifie que ta méthode se trouve sur un script attaché à un GameObject et que l'événement OnClick() du bouton est connecté à cette méthode.
+ Vérifie que tu as un GameObject EventSystem dans ta scène. Si ce n'est pas le cas, fais un clic droit dans la fenêtre Hierarchy et ajoutes-en une. 

