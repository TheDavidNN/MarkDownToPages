# Input

For at spilleren skal kunne spille spillet, programmet kunne genkende og reagere, når spilleren trykker på knapperne, bruger joysticket, etc.

Unity har to systemer til at læse input: den gamle `Input Manager` og det nye `Input System`.
Unity har desuden givet os flere forskellige måder at bruge det nye system. Vi kommer til at bruge en af de nyere versioner. 
De fleste online tutorials bruger enten den gamle `Input Manager` eller andre metoder for det nye system. 

Det første vi gør er at skabe en variabel, der skal indeholde alle vores key-mappings (hvilke knapper systemet skal holde styr på).
I `Player` klassen, lav en `public` variabel af typen `InputAction`:

```C#
    ...
    public class Player : MonoBehaviour 
    {
        public int health = 3;
        public InputAction moveAction;
    ...
```

I Unity, giv konfigurer variablerne så man bevæger sig med WASD-knapperne.

![InputAction.png](InputAction.png)

Tilbage i koden, før vi kan bruge input systemet skal vi først kalde `Enable()` metoden på variablen.

Vi kan nu læse input med `.ReadValue()` metoden. Vi kan gemme resultatet i en variabel:

```C#
    void Update()
    {
        Vector2 moveInput = moveAction.ReadValue<Vector2>();
    }
```

Fordi brugeren giver input på to akser (op/ned og venstre/højre), skal vi bruge en Vector2 som kan indeholde begge værdierne.
`ReadValue<Vector2>()` fortæller Unity at vi forventer at inputtet er af typen `Vector2`.

Vi kan læse de individuelle værdier ved at bruge `moveInput.x` og `moveInput.y`. 
Prøv at printe dem, og tjek at det virker ved at starte spillet og trykke på knapperne!



## Udfordring: Hoppe-input

Prøv at lave endnu en variabel, der skal holde styr på, hvornår spilleren skal hoppe.