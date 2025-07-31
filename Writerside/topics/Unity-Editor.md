# Unity Editor
Før vi dykker ned i noget kode, bør man gøre sig bekendt med Unity editoren.


## Paneler
Unity Editoren er opdelt i forskellige paneler.

![UnityPanels](UnityPanels.png)

1. **Hierarchy**: Her kan I se alle `GameObjects` i jeres scene.
2. **Scene view**: Her kan I se jeres spil og redigere det.
3. **Game view**: Her kan I se jeres spil som det vil se ud for spilleren.
4. **Inspector**: Her kan I se og redigere egenskaberne for det valgte objekt.
5. **Project**: Her kan I se alle filer i jeres projekt.
6. **Console**: Her kan I se fejl og beskeder fra Unity.

Man kan drag-and-drop panelerne rundt. Det giver nogle gange mening at vise og skjule bestemte paneler.

![DragPanel.gif](DragPanel.gif)

Man kan dobbelt-klikke på toppen af et panel for at vise den med hele skærmen.

![FullscreenPanel.gif](FullscreenPanel.gif)

Hvis I laver en fejl med jeres layout, kan man nemt gå tilbage til standarden ved at klikke på `Window > Layouts > Default`.



## GameObjects

I Unity er ethvert objekt et `GameObject`. Det inkluderer:

- karakterer,
- miljø,
- spillerens kamera,
- usynlige objekter, der holder styr på data,
- etc.

Hierakiet viser en liste af alle GameObjects i den nuværende scene. En `scene` kan ses som en samling af GameObjects.

Når I skaber en ny scene, burde den automatisk indeholde et GameObject, `Main Camera`.

![Hierachy.png](Hierachy.png)

Hvis I klikker på kameraet i hierakiet, kan i se alle dets egenskaber i inspektoren.

![Inspector.png](Inspector.png)

### Components

GameObjects består af `Components`. Components er hvad der bestemmer, hvad et GameObject gør. Fx har `Main Camera` en `Transform` og en `Camera` component.


Alle GameObjects har en `Transform` component, der bestemmer dens position, rotation og skalering. 
Når vi gerne vil bevæge et GameObject (fx vores spiller), så ændrer vi dens Transform component.

Prøv at skabe en cirkel ved at højreklikke i hierakiet og klikke `2D Object > Sprites > Circle`. 
GameObjectet har en Transform, så den har en position, og det har en `Sprite Renderer`, der tegner billedet af en cirkel.

Hvis I nu starter spillet, burde der ikke ske så meget - der er bare en cirkel. Prøv at tilføje en `Rigidbody 2D` component til cirklen!

Unity giver os utrolig mange components, og mange flere kan findes på internettet.
Hvis vi skal bruge noget komplekst eller unikt til vores spil, skal vi lave vores egne components. Dette gøres gennem kode.

### Parent-child forhold

Nogle GameObjects kan være "parents" af andre GameObjects (deres "children"). 
Children vil altid eksisterer relativt til deres parent. Fx, hvis en parent bevæger sig, vil dets child følge med.
Hvis du drag-and-dropper et GameObject over på et andet i hierakiet, burde de blive til parent-child.

![ParentChild.gif](ParentChild.gif)

## Skab en spiller karakter

Prøv at skabe en spiller karakter og en platform, de kan stå på:

1. Skab en cirkel.
2. Skab en firkant under cirklen og skaler den, så der er plads til spilleren.
3. Giv spilleren en `Rigidbody 2D`, så den falder ned på platformen.
4. Giv både karakteren og platformen en `Collider`, så de ikke kan bevæge sig igennem hinanden.

![BallDrop.gif](BallDrop.gif)

