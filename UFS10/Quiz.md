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

### Come funziona lo string interpolation in Angular
{{variabile}}


### Cosa permette di evitare l'uso di AppModule
standalone:true

### Quale direttiva permette il 2 way binding

```typescript
[(ngModel)]
```

### Da dove si importa FormsModule

@angular/forms

### Ho importato FormsModule ma non funziona

Bisogna aggiungere FormsModule in "imports"

### Segna la riga corretta
```typescript
(click)="aggiungiNota()"
[disabled]="!testo"
```


### Segna la riga per il for
```html
<li *ngFor="let nota of note">{{nota}}</li>
```

### Errore?
```typescript
aggiungiNota(){
	note = [...note, testo],
	testo = "";
}
```
manca il this

### ngFor modifica il DOM

Si sempre

### Cosa si aspetta come parametro filter di array?

Una callback

### Seleziona la riga corretta
```html
<li *ngFor="let nota of note">
	<span (click)="togliNota(nota)">
		{{nota}}
	</span>
</li>
```

### Seleziona tra questi quello che non e' un selettore Angular
```typescript
{app-accordion}
```

### A quale selettore appartiene `[app-nota]`
```html
<div app-nota></div>
```


### A quale selettore `"app-nota"`
```hmtl
<app-nota></app-nota>
```

### Cosa permette il passaggio di parametri da un componente all'altro
```typescript
@Input()
```

### Cos'e' il parametro passato al decoratore che permette il passaggio di parametri

string alias

### Come passo i parametri ad un componente?
```html
<componente parametro="valore"/>
```


### Quale parametro porta l'evento al metodo chiamante
```typescript
$event
```

### Cosa fa preventDefault

Evita l'invio della form


### Cosa fa il decoratore Output

Permette di associare un evento custom al componente

### Quale comando permette di lanciare un evento da event emitter 

`emit`


### Come si passa il "generic" di tipo "stringa"
```typescript
new EventEmitter<string>()
```


### Come si crea una local reference 

`#mioRef`

### Come si usa una local reference 

`prendiRef(mioRef)`


### A cosa serve il ViewChild

Ad evitare l'uso della local reference

### Cos'e' il ViewChild

Un decoratore

### A cosa serve ViewChild

A collegare un elemento del DOM ad una proprieta'


###  Riga esatta

```typescript
@ViewChild('mioInput') mioInput?: ElementRef;
```


### Come si chiama il tag che permette di mostrare il contenuto di un componente

`ng-content`


### Riga esatta

```html
<ng-content>
contenuto di default
</ng-content>
```

### Come si accede ad un elemento del DOM tramite local reference

`#miaRef`

### Cosa permette di mostrare o non mostrare un tag

`*ngIf`




## Form

### Cosa vuole come parametro "ViewChild"

Il nome della referenza puntata

### Come si chiama l'evento dell'event binding da associare alla onSubmit

ngSubmit


### Che stringa si associa alla referenza della form

ngForm


### Come si chiama il tipo associato alla property della form

NgForm

### Quale metodo sovrascritto permette di leggere la form

NgDoCheck


### Quale property rende l'input obbligatorio?

require


### Come si chiama la property di form che restituisce lo stato della form stessa

status


### Come si chiama quando la form e' "ok"

VALID


### Quale modulo e' il principale gestore della reactive form

ReactiveFormsModule

### In caso di ReactiveForm, come si chiama il tipo della form

FormGroup

### Nella reactive form come si chiama la proprieta' che collega la form "loginForm"

formGroup 



## Direttive

### Quale di questa e' una direttiva strutturale

NgIf

### Cosa permette di generare una direttiva

Decorando la classe con @Directive

### HostBinding

Un decoratore

### OnInit

Interfaccia 

### A cosa serve HostBinding

A creare un collegamento tra una proprieta' del DOM ed una di classe 


### Cos'e' HostListener

Un decoratore

### Che scopo ha HostListener

Creare un collegamento tra un metodo di classe ed un evento del DOM

###  Normalmente il selettore di una direttiva e' tra parentesi

Quadre

### A cosa serve il decoratore @Input

A passare parametri ad una classe

### Che parametro e' possibile passare al decoratore @Input

Una stringa


### Cosa succede se si passa lo stesso nome della direttiva al decoratore @Input di uno dei parametri della direttiva stessa 

Si applica automaticamente il metodo associato

### Cosa succede se si lascia "applicaColore" e sis lascia "coloreBase"

Niente, ma la direttiva non funziona piu'


## Pipe

### Quale carattere permette la pipe

`|`

### Come si passano parametri alla pipe "date"

`date:'parametro'`

### Quante pipe di possono concatenare

Infinite

### Come si usa substring

testo.substring(0,10)

### Come si implementa un'interfaccia di classe 

implements 


### Come si passa un valore di default al parametro di una funzione

```typescript
funzione(par1:number = 3)
```

### Quati parametri possono essere passati ad una pipe

Infiniti

### Quale carattere separa i parametri passati alla pipe

`:`

### Dove si passano i generic delle classi

`classe<T>`

### Quando si itera su un *ngFor si usa

of

### E' possibile aggiungere una pipe nel parametro di un ngFor

Si 






## Flusso Dati

### Come si decora un servizio

`@Injectable`

### Come si inserisce un servizio in una pagina 

```typescript
constructor(private service:Service) //vecchio metodo
inject(Service)
```

### Come si crea un selettore per questo componente `<app-component/>`\

`app-component`

### Cosa ritorna Interval

Un Observable

### Quale metodo di Observable permette di accedere al callback

`subscribe`

### Quale metodo permette di interrompere l'accesso alla callback

`unsubscribe`

### Quale metodo va implementato per la OnDestroy

`ngOnDestroy`

### Cosa fa la pipe async

Sottoscrive e chiama la next

### Quale simbolo e forma vengono usati per identificare un observable 

`mioObservable$`

### Nullish Coaleshing

`??`

### Come si crea un nuovo Observable

```typescript
obs$ = new Observable
```

### Cosa si passa durante la costruzione di un Observable

Una callback

### Quali sono i metodi che possono essere invocati in una sottoscrizione

next, error, complete

### Cosa si aspetta una subscription

Un oggetto oppure una callback

### Cosa ritorna il metodo subscribe

Una Subscription 

### I Subject sono 

Multicast

### I Subject sono detti imperativi

Possono produrre un valore anche se non vengono sottoscritti

### Da che versione sono disponibili i Signal

16

### In uno stato signal di nome conta come si legge il valore\

`conta()`

### Come si modificano i signal

`conta.set(3)`

### Da dove si importano i signal

```typescript
"@angular/core"
```

### Cosa si aspetta il metodo update di signal

Una callback

### Quando si usa update al posto di set

Quando si vuole accedere al valore precedente senza usare lo stato()

### Con quale funzione di React si puo' equiparare "computed"

`useMemo`

### Cosa si aspetta computed

Una callback

### I computed sono modificabili tramite set o update?

No

### A cosa corrisponde "effect" di signal

`useEffect con limitazioni`

### E' possibile modificare uno stato dentro effect

Si, ma e' fortemente sconsigliato


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



