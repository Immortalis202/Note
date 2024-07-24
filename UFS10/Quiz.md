## Intro
### Come si importa Component?

```Typescript
import { Component } from '@angular/core';
```

### A cosa serve il parametro "standalone"
Ad evitare di dover registrare il componente nel file AppModule

### Cosa determina il funzionamente del property binding

Le parentesi quadre

### Stato del bottone 

```html
<button disabled="false">Bottone </button>
```
disabilitato

### Qual è la riga esatta per l'event binding della funzione "incrementa"?

```typescript
(click)="incrementa"
```

### Come si passa l'oggetto evento indietro alla funzione chiamante?

```typescript
$event
```


### Segna la riga errata relativamente al casting in typescript
```typescript
const inputRef = (HTMLInputElement)e.target
```

### Seleziona la riga corretta

```typescript
(input)="onPremutoTasto($event)"
```


### Quale property permette il meccanismo di connessione bidirezionale con gli stati?

```typescript
[(ngModel)]
```


### Come si importa FormsModule?
```typescript
import { FormsModule } from '@angular/forms';
```


### Come si portano nella classe i moduli aggiuntivi?

Tramite l'array "imports"

### Come si esegue lo string interpolation in Angular
```typescript
{{variabile}}
```



### Mostra l'uso corretto dell'ngFor

```html
<li *ngFor="let parola of parole"> {{parola}} </li>
```

### Mostra l'uso corretto dell'ngIf

```HTML
<div *ngIf="!parole.length"> Non ci sono elementi nella lista </div>
```








## Intermedio


## Form

## Direttive

## Pipe

## Flusso Dati



## ROUTER

### Cosa si aspetta il tipo "Routes"
Un array

### Quali sono le due principali proprieta' esposte da Routes
path e component

### Quale stringa si usa per definire la home in Routes
stringa vuota

### Cosa si aspetta "component" in Routes

Una classe

### Cos'e' routerLink

Una direttiva

### Cosa fa routerLinkActive

Aggiunge la classe passata quando la rotta corrisponde alla pagina selezionata


### Che parametro si aspetta routerLink
Il percorso a partire da "/"

### seleziona la riga esatta
```typescript
[routerLinkActiveOptions]="{exact:true}"
```



### Come si crea una get tramite modulo HTTP
```typescript 
this.http.get("url")
```

### Cosa restituisce la get
Un observable

### Quale carattere permette la "pipe"
```typescript
|
```

### Come si passano i parametri nella URL

```typescript
prodotti/:id
```

### Come si accede ad un servizio

Tramite "inject"


### Quale servizio permetti  di accedere alla rotta dinamica

```typescript
ActivatedRoute
```



