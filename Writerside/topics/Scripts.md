# Scripts

Når vi gerne vil lave vores egne components, gør vi det ved at lave et nyt `script`. 
Scripts i Unity skrives i C#.
Man laver et nyt script ved at højreklikke i `Project` panelet og klikke `Create > MonoBehaviour Script`. I ældre versioner af Unity hed knappen bare `Script`.
Prøv nu selv at lave et script. Giv det navnet `Player` og dobbeltklik på filen for at åbne den i din IDE.

![EmptyMonoBehaviour.png](EmptyMonoBehaviour.png)

Scriptet indeholder allerede nogle elementer. Først deklarerer den en `Player` klasse.
`: MonoBehaviour` betyder at klassen _nedarver_ fra klassen `MonoBehaviour`. 
`MonoBehaviour` gør at vi kan bruge klassen som en component i Unity.

Prøv at tilføje `Player` scriptet som en component til karakterens GameObject.

Inde i klassen har Unity deklareret to metoder:
- `Start` Denne kode eksekveres, når spillet starter.
- `Update` Denne kode eksekveres hver frame.

Lad os prøve at få koden til at skrive en besked i vores Console.
Det kan gøres med `print()` funktionen.

Prøv at printe nogle beskeder!

```C#
using UnityEngine;

public class Player : MonoBehaviour
{
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        print("Start spillet!");
    }

    // Update is called once per frame
    void Update()
    {
        print("Ny frame!");        
    }
}
```

Hvis I går tilbage til Unity, sørger for at scriptet er tilføjet som en component, 
og starter spillet, burde I kunne se beskederne i Console panelet.

![Print.png](Print.png)

## Variabler

Det er ofte nødvendigt at gemme data i programmer. 
Det kan være et objekts position, spillerens liv, antal point, etc.
Vi kan derfor bruge variabler til at gemme værdier.
Vi deklarerer en variabel med den følgende struktur:

```C#
    type navn;
```

`type` skal være en _datatype_, og `navn` er navnet på variablen. Vi kan give variablen en start-værdi med den følgende struktur:

```C#
    type navn = værdi;
```

Der findes mange datatyper, men her er nogen af de mest grundlæggende:

<table style="header-column">
    <tr>
        <td>int</td>
        <td>heltal</td>
    </tr>
    <tr>
        <td>float</td>
        <td>decimaltal</td>
    </tr>
    <tr>
        <td>string</td>
        <td>tekst</td>
    </tr>
    <tr>
        <td>bool</td>
        <td>Sand/falsk</td>
    </tr>
</table>

Lad os give spilleren en `health` variabel. Lad os sige at spilleren har 3 liv. 
Prøv også at printe `health` variablen, så vi kan holde øje med spillerens liv.

Vi tilføjer deklarationen `int health;` til toppen af klassen.

```C#
    using UnityEngine;
    
    public class Player : MonoBehaviour
    {
    int health = 3;
    
        // Start is called once before the first execution of Update after the MonoBehaviour is created
        void Start()
        {
            print("Start spillet!");
        }
    
        // Update is called once per frame
        void Update()
        {
            print(health);        
        }
    }
```

### public variabler

Det kunne være rart, hvis vi kunne se og ændre spillerens liv fra Unity uden at skulle åbne koden.
Lige nu er `health` en _private_ variabel, hvilket betyder at det kun er `Player` klassen der kan se og ændre dens værdi. 

Vi kan give Unity mulighed for at se og ændre variablen ved at skrive `public int health = 3;`.

![PlayerHealth.png](PlayerHealth.png)

### Variable Scope

Bemærk at alle variabler har et bestemt _scope_. en variables scope bestemmer hvor den kan bruges. 
En variabel kan bruges i samme _block_ som den blev deklareret i eller dybere.

Fx kan vi bruge `health` variablen i både `Start()` og `Update`.

![GoodScope.png](GoodScope.png)

Hvis vi flyttede variablens deklaration til `Start()`, ville vi ikke kunne bruge den i `Update()`.

![BadScope.png](BadScope.png)
