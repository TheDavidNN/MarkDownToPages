# If-else

En af de simpleste ting et program skal gøre er at tjekke om noget er sandt. 
Fx skal spilleren kun dø, hvis de har 0 liv tilbage.

Vi kan derfor lave if-statements:

```C#
if (condition) {
    ...
}
```

Hvis `condition` evalueres til `true`, bliver koden i blokken kørt. 
Vi kan tilføje en `else` til at gøre noget, hvis `condition` ikke er `true`.

```C#
if (condition) {
    ...
} else {
    ...
}
```

Vi kan også tilføje `else if` blokke:

```C#
if (condition1) {
    ...
} else if (condition2) {
    ...
} else if (condition3) {
    ...
} else {
    ...
}
```

Hvis `condition1` er `true`, vil koden ikke eksekvere nogle af de andre grenne.

## Udfordring: Print en besked når spilleren skal hoppe

Lav et if-statement i `Update()` der tjekker om spilleren skal hoppe.
Hvis de skal, print en besked.