# Les 2: CSS & Selectors

## 2.1 Tooling

Er zijn verschillende applicaties & websites die ons goed kunnen helpen bij het leren ontwikkelen van websites. Voor deze les gaan we een account maken bij GitHub. Vervolgens gebruiken we dezelfde account voor CodePen. Er volgt een video die uitlegt hoe je dit doet.

### GitHub

#### Intro

We gaan later zelf ook GitHub leren gebruiken, maar de hoofdreden dat ik jullie nu vraag een account te maken is zodat je met je GitHub account op een heel groot aantal verschillende web technology gerelateerde websites kan inloggen en dan moet je niet telkens een nieuwe account maken.

Deze cursus is overigens ook een repository / online folder die op GitHub staat.

#### Wikipedia uitleg

**GitHub** is een online platform waar [software](https://nl.wikipedia.org/wiki/Software "Software") op kan worden geplaatst. GitHub is gebouwd rond het [Git](https://nl.wikipedia.org/wiki/Git_(software) "Git (software)")-[versiebeheersysteem](https://nl.wikipedia.org/wiki/Versiebeheersysteem "Versiebeheersysteem"), waardoor GitHub alle mogelijkheden van [Git](https://nl.wikipedia.org/wiki/Git_(software) "Git (software)") en eigen toevoegingen aanbiedt.

Het beschikt onder ander over [toegangscontrole](https://nl.wikipedia.org/wiki/Toegangscontrole "Toegangscontrole") en verschillende samenwerkingsfuncties, zoals een [issue tracker](https://nl.wikipedia.org/wiki/Issue_tracker "Issue tracker"), een forum voor het aanvragen van functies, takenlijsten en [wiki](https://nl.wikipedia.org/wiki/Wiki "Wiki")'s voor ieder project.<sup id="cite_ref-2" class="reference">[[2]](https://nl.wikipedia.org/wiki/GitHub#cite_note-2)</sup>

Op GitHub staat veel [opensourcesoftware](https://nl.wikipedia.org/wiki/Opensourcesoftware "Opensourcesoftware") omdat bij openbare repositories de [broncode](https://nl.wikipedia.org/wiki/Broncode "Broncode") kan worden ingekeken door derden.

GitHub biedt zowel gratis als betaalde abonnementen. Om privé-projecten te kunnen hosten op GitHub is sinds 8 januari 2019 geen betaald abonnement meer nodig.<sup id="cite_ref-3" class="reference">[[3]](https://nl.wikipedia.org/wiki/GitHub#cite_note-3)</sup>

De mascotte van GitHub is _Octocat_, een [geantropomorfiseerde](https://nl.wikipedia.org/wiki/Antropomorfisme "Antropomorfisme") kat met octopusachtige-ledematen.<sup id="cite_ref-4" class="reference">[[4]](https://nl.wikipedia.org/wiki/GitHub#cite_note-4)</sup>

GitHub is geschreven in _[Ruby on Rails](https://nl.wikipedia.org/wiki/Ruby_on_Rails "Ruby on Rails")_ en [Erlang](https://nl.wikipedia.org/wiki/Erlang_(programmeertaal) "Erlang (programmeertaal)") door Chris Wanstrath, P. J. Hyett en Tom Preston-Werner.

### OPDRACHT: Maak een account op GitHub

[https://github.com/](https://github.com/)

Vervolgens mag je je GitHub account delen in #general channel in Discord.

### CodePen

We gaan in onze lessen ook gebruik maken van CodePen.

Dit is een site met een community die HTML, CSS & JavaScripts "snippets" deelt.

Een "snippet" is gewoon een klein stukje code of HTML.

Je kan hier ook makkelijk veel uitproberen en dan delen. Je kan ook veel inspirerende code / html snippets vinden van andere mensen.

[https://codepen.io/](https://codepen.io/)

#### Inloggen op CodePen met GitHub Account

We gaan onze GitHub account inloggen op CodePen.

[Zie deze video hieronder hoe dit te doen](codepenlogin.mkv)

### Gebruik maken van CodePen

[Zie deze video hoe codepen te gebruiken](codepengebruiken.mkv)

## 2.2 CSS Basis

### CSS toevoegen aan ons document

Het allereerste dat we moeten doen, is het HTML-document vertellen dat we enkele CSS-regels hebben die we willen gebruiken. Er zijn drie verschillende manieren om CSS toe te passen op een HTML-document dat u vaak tegenkomt, maar voorlopig zullen we kijken naar de meest gebruikelijke en nuttige manier om dit te doen: CSS koppelen vanuit de kop van uw document.

Maak een bestand in dezelfde map als uw HTML-document en sla het op als `styles.css`. De extensie `.css` geeft aan dat dit een CSS-bestand is.

Om `styles.css` aan `index.html` te koppelen, voegt u de volgende regel ergens in de [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head "The HTML <head> element contains machine-readable information (metadata) about the document, like its title, scripts, and style sheets.") van het HTML-document:

```HTML
<link rel="stylesheet" href="styles.css">
```

Deze [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link "The HTML External Resource Link element (<link>) specifies relationships between the current document and an external resource. This element is most commonly used to link to stylesheets, but is also used to establish site icons (both "favicon" style icons and icons for the home screen and apps on mobile devices) among other things.") element vertelt de browser dat we een stylesheet hebben, met behulp van het `rel` attribuut, en de locatie van dat stylesheet als de waarde van het `href` attribuut. U kunt testen of de CSS werkt door een regel toe te voegen aan `styles.css`. Gebruik uw code-editor om het volgende toe te voegen aan uw CSS-bestand:

```CSS
h1 {
  color: red;
}
```

Sla uw HTML- en CSS-bestanden op en laad de pagina opnieuw in een webbrowser. De kop van niveau één bovenaan het document moet nu rood zijn. Als dat gebeurt, gefeliciteerd - u hebt met succes wat CSS op een HTML-document toegepast. Als dat niet gebeurt, controleer dan zorgvuldig of je alles correct hebt getypt.

Je kunt lokaal in `styles.css` blijven werken, of je kunt oefeningen maken in CodePen. De interactieve editor werkt alsof de CSS in het eerste paneel is gekoppeld aan het HTML-document, net zoals we hebben gedaan met ons document hierboven.

## HTML-elementen opmaken

Door onze kop rood te maken, hebben we al aangetoond dat we een HTML-element kunnen targeten en stylen. We doen dit door een _element selector_ te targeten - dit is een selector die direct overeenkomt met de naam van een HTML-element. Om alle alinea's in het document te targeten, gebruikt u de selector `p`. Om alle alinea's groen te maken, gebruikt u:

```CSS
p {
  color: green;
}
```

U kunt meerdere selectors tegelijk targeten door de selectors te scheiden met een komma. Als ik wil dat alle alinea's en alle lijstitems groen zijn, ziet mijn regel er als volgt uit:

```CSS
p, li {
    color: green;
}
```

[Probeer in deze oefening meerdere selectors tegelijk te selecteren](https://codepen.io/GoldFlow/pen/mdrdexJ?editors=1100)

---

### Het standaardgedrag van elementen wijzigen

Als we naar een goed gemarkeerd HTML-document kijken, zelfs zoiets eenvoudigs als ons voorbeeld, kunnen we zien hoe de browser de HTML leesbaar maakt door een standaardstijl toe te voegen. Koppen zijn groot en vetgedrukt en onze lijst bevat opsommingstekens. Dit gebeurt omdat browsers interne stylesheets hebben met standaardstijlen, die ze standaard op alle pagina's toepassen; zonder hen zou alle tekst in een hoop samenkomen en zouden we alles vanaf nul moeten opmaken. Alle moderne browsers geven standaard HTML-inhoud op vrijwel dezelfde manier weer.

Vaak wilt u echter iets anders dan de keuze die de browser heeft gemaakt. Dit kan gedaan worden door simpelweg het HTML-element te kiezen dat u wilt wijzigen, en een CSS-regel te gebruiken om het uiterlijk te veranderen. Een goed voorbeeld is onze `<ul>`, een ongeordende lijst. Het heeft lijstkogels, en als ik besluit dat ik die kogels niet wil, kan ik ze als volgt verwijderen:

```CSS
li {
  list-style-type: none;
}
```

Probeer dit nu aan uw CSS toe te voegen.

De eigenschap `list-style-type` is een goede eigenschap om op MDN naar te kijken om te zien welke waarden worden ondersteund. Kijk eens op de pagina voor [`[list-style-type]`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type) en je zult een interactief voorbeeld vinden bovenaan de pagina om enkele verschillende waarden te proberen, daarna worden alle toegestane waarden verderop op de pagina gedetailleerd.

Als je naar die pagina kijkt, zul je ontdekken dat je, naast het verwijderen van de lijst met opsommingstekens, deze ook kunt wijzigen - probeer ze te veranderen in vierkante opsommingstekens door de waarde `vierkant` te gebruiken.

### Een klas toevoegen

Tot nu toe hebben we elementen opgemaakt op basis van hun HTML-elementnamen. Dit werkt zolang u wilt dat alle elementen van dat type in uw document er hetzelfde uitzien. Meestal is dat niet het geval en moet u een manier vinden om een ​​subset van de elementen te selecteren zonder de andere te wijzigen. De meest gebruikelijke manier om dit te doen, is door een klasse aan uw HTML-element toe te voegen en die klasse te targeten.

Voeg in je HTML-document een [class attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/class) toe aan het tweede lijstitem. Je lijst ziet er nu als volgt uit:

```HTML
<ul>
  <li> Eerste punt </li>
  <li class="special"> Punt twee </li>
  <li> Item <em>drie</em> </li>
</ul>
```

In uw CSS kunt u zich richten op de klasse "special" door een selector te maken die begint met een punt. Voeg het volgende toe aan uw CSS-bestand:

```CSS
.special {
  color: orange;
  font-weight: bold;
}
```

### Oefening Klas Toevoegen:

[Open deze link om bovenstaande uit te proberen](https://codepen.io/GoldFlow/pen/MWjWaBG)

Video hieronder die de oefening en het principe van klasses uitlegt.

<video width="600" controls>
<source src="klassetoevoegen.mkv">
</video>

U kunt de klasse 'speciaal' toepassen op elk element op uw pagina dat u hetzelfde uiterlijk wilt geven als dit lijstitem. Als je bijvoorbeeld wilt dat het `<span>` element in de alinea ook oranje en vetgedrukt is, dan kan je dat ook doen: probeer er een `class` van `special` aan toe te voegen, herlaad dan je pagina en kijk wat er gebeurt.

Soms zie je regels met een selector die de HTML-elementselector samen met de klasse vermeldt:

```CSS
li.special {
  color: orange;
  font-weight: bold;
}
```

Deze syntaxis betekent "target elk `li` element dat een speciale klasse heeft ". Als je dit zou doen, zou je de klasse niet langer kunnen toepassen op een `<span>` of een ander element door de klasse er gewoon aan toe te voegen; je zou dat element aan de lijst met selectors moeten toevoegen:

```CSS
li.special,
span.special {
  color: orange;
  font-weight: bold;
}
```

Zoals u zich kunt voorstellen, kunnen sommige klassen op veel elementen worden toegepast en wilt u niet steeds uw CSS moeten blijven bewerken als er iets nieuws nodig is om die stijl aan te nemen. Daarom is het soms het beste om het element te omzeilen en simpelweg naar de klasse te verwijzen, tenzij je weet dat je een aantal speciale regels wilt maken voor één element alleen, en misschien zeker wilt weten dat ze niet op andere dingen worden toegepast.

Ik leg het hieronder nog eens uit in video:

<video width="600" controls>
<source src="elementspecificclass.mkv">
</video>

## Dingen stylen op basis van hun locatie in een document

Er zijn momenten waarop u wilt dat iets er anders uitziet, afhankelijk van waar het zich in het document bevindt. Er zijn een aantal selectors die u hier kunnen helpen, maar voor nu zullen we er slechts een paar bekijken. In ons document zijn twee `<em>` elementen - één in een alinea en de andere in een lijstitem. Om alleen een `<em>` te selecteren die is genest in een `<li>` -element, kan ik een selector gebruiken die de **descendant combinator** wordt genoemd, die eenvoudig de vorm aanneemt van een spatie tussen twee andere selectoren.

Add the following rule to your stylesheet.

```CSS
li em {
  color: rebeccapurple;
}
```

Deze selector selecteert elk `<em>` -element dat zich in (een afstammeling van) een `<li>` bevindt. Dus in je voorbeelddocument zou je moeten zien dat het `<em>` in het derde lijstitem nu paars is, maar het item in de alinea is ongewijzigd.

Uitleg herhaald in video hieronder:

<video width="600" controls>
<source src="locationselector.mkv">
</video>

[Link naar oefening](https://codepen.io/GoldFlow/pen/eYdYpwQ)

---

### Adjacent Sibling Combinator

Iets anders dat u misschien zou willen proberen, is het opmaken van een paragraaf `p` als deze direct na een heading (bv `h1`) op hetzelfde hiërarchieniveau in de HTML komt. Plaats hiervoor een `+` (een **adjacent sibling combinator**) tussen de selectors.

We maken hier een oefening op.
[Je kan de link naar de oefening hier terugvinden.](https://codepen.io/GoldFlow/pen/LYRYGEE)

Probeer deze regel ook aan uw stylesheet toe te voegen:

```CSS
h1 + p {
  font-size: 200%;
}
```

Ik herhaal de theorie & oefening hier uit:

<video width="600" controls>
<source src="adjacentsiblingcombinator.mkv">
</video>

---

### Dingen stylen op basis van staat

Het laatste type styling dat we in deze les zullen bekijken, is de mogelijkheid om dingen te stylen op basis van hun staat. Een eenvoudig voorbeeld hiervan is het stylen van links. Wanneer we een link opmaken, moeten we het [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) (anchor) -element targeten. Dit heeft verschillende toestanden, afhankelijk van of het niet wordt bezocht, bezocht, erover wordt bewogen, gefocust via het toetsenbord of wordt geklikt (geactiveerd). U kunt CSS gebruiken om deze verschillende staten te targeten - de onderstaande CSS geeft niet-bezochte links roze en bezochte (`visited`) links groen.

```CSS
a:link {
  color: pink;
}

a:visited {
  color: green;
}
```

U kunt het uiterlijk van de link wijzigen wanneer de gebruiker erover beweegt, bijvoorbeeld door de onderstreping te verwijderen, wat wordt bereikt door in de volgende regel:

```CSS
a:hover {
  text-decoration: none;
}
```

[Oefening hier](https://codepen.io/GoldFlow/pen/zYKYrKV?editors=1100)

Uitleg wordt herhaald in video hieronder:

<video width="600" controls>
<source src="stateselector.mkv">
</video>


Belangrijk:

We hebben de onderstreping op onze link bij hover verwijderd. U kunt de onderstreping uit alle staten van een link verwijderen. Het is echter de moeite waard om te onthouden dat u op een echte site ervoor wilt zorgen dat bezoekers weten dat een link een link is. Als u de onderstreping op zijn plaats laat, kan dit een belangrijke aanwijzing zijn voor mensen om te beseffen dat op bepaalde tekst in een alinea kan worden geklikt - dit is het gedrag dat ze gewend zijn. Zoals met alles in CSS, is er de mogelijkheid om het document minder toegankelijk te maken met uw wijzigingen - we zullen proberen mogelijke valkuilen op de juiste plaatsen te markeren.

---

## Combinatie van selectors en combinatoren

Het is de moeite om de melden dat u meerdere selectors en combinators samen kunt combineren. Bijvoorbeeld:

```CSS
/* selects any <span> that is inside a <p>, which is inside an <article>  */
article p span { ... }

/* selects any <p> that comes directly after a <ul>, which comes directly after an <h1>  */
h1 + ul + p { ... }
```

U kunt ook meerdere soorten met elkaar combineren. Probeer het volgende aan uw code toe te voegen:

```CSS
body h1 + p .special {
  color: yellow;
  background-color: black;
  padding: 5px;
}
```

Hiermee wordt elk element gestileerd met de klasse `special`, die zich in een `<p>` bevindt, die net na een `<h1>` komt, die zich in een `<body>` bevindt. Amai!

In de originele HTML die we hebben geleverd, is het enige opgemaakte element `<span class = "special">`.

Maak je geen zorgen als dit op dit moment ingewikkeld lijkt - je zult het snel onder de knie krijgen als je meer CSS schrijft.

---

## 2.3. Selectors

### Wat is een selector

We hebben al selectors ontmoet. Een CSS-selector is het eerste deel van een CSS-regel. Het is een patroon van elementen en andere termen die de browser vertellen welke HTML-elementen moeten worden geselecteerd om de CSS-eigenschapswaarden binnen de regel toe te passen. Het element of de elementen die door de selector worden geselecteerd, worden het _subject (onderwerp) of the selector_.

```CSS
    h1 {
        color: blue;
        background-color: yellow;
    }
```

In dit voorbeeld hierboven hebben we een selector gemaakt die als "subject", of als onderwerp dus de h1 tag heeft. In dit voorbeeld gaan we dus voor h1, de tekstkleur blauw maken en de achtergrondkleur geel.

## Selector lists

Als je meer dan één ding hebt dat dezelfde CSS gebruikt, kunnen de individuele selectors worden gecombineerd tot een _selector list_ zodat de regel wordt toegepast op alle individuele selectors. Als ik bijvoorbeeld dezelfde CSS heb voor een `h1` en ook een klasse `.special`, zou ik dit als twee aparte regels kunnen schrijven.

```CSS
h1 { 
  color: blue; 
} 

.special { 
  color: blue; 
}
```

Ik zou deze ook kunnen combineren tot een keuzelijst door er een komma tussen te zetten.

```CSS
h1, .special { 
  color: blue; 
}
```

Witruimte is geldig voor of na de komma. Mogelijk vindt u de selectors ook beter leesbaar als ze allemaal op een nieuwe regel staan.

```CSS
h1, 
.special {
  color: blue; 
}
```
### Oefening: Selector Lists

Probeer in de onderstaande codepen de twee selectors te combineren die identieke declaraties hebben. De visuele weergave moet hetzelfde zijn nadat ze zijn gecombineerd.

- Zorg dat je zeker bent ingelogd
- Na afloop sla de oefening op

[Link naar Selector Lists Start oefening](https://codepen.io/GoldFlow/pen/NWrQQpO)

### Fouten maken bij selectors

Als u selectors op deze manier groepeert, wordt de hele regel genegeerd als een selector ongeldig is.

In het volgende voorbeeld wordt de ongeldige klassenelectorregel genegeerd, terwijl de h1 nog steeds wordt opgemaakt.

```CSS
h1 { 
  color: blue; 
} 

..special { 
  color: blue; 
} 
```
Wanneer ze echter worden gecombineerd, worden noch de `h1` noch de klasse gestileerd, aangezien de hele regel als ongeldig wordt beschouwd.

```CSS
h1, ..special { 
  color: blue; 
} 
```

## Types of selectors

Er zijn een paar verschillende groepen selectors, en als u weet welk type selector u nodig heeft, kunt u het juiste hulpmiddel voor de taak vinden. In de subartikels van dit artikel gaan we dieper in op de verschillende groepen selectors.

### Type, class, and ID selectors

Deze groep bevat selectors.

#### Element Selector

Een selector die gericht is op een HTML-element zoals een `<h1>`.

HTML voorbeeld:
```HTML
<h1>Titel</h1>
```

CSS voorbeeld:
```CSS
h1 { }
```

#### Class Selector

Het bevat ook selectors die gericht zijn op een klasse:

HTML voorbeeld:
```HTML
<p class="box">Enkele deze paragraaf zal geselecteerd worden</p>
<p>Deze paragraaf heeft geen klasse en zal niet geselecteerd worden.</p>
```
CSS Voorbeeld:
```CSS
.box { }
```

#### ID Selector

HTML Voorbeeld:
```HTML
<p id="unique">Enkele deze paragraaf zal geselecteerd worden</p>
<p>Deze paragraaf heeft geen id en zal niet geselecteerd worden.</p>
```
CSS Voorbeeld:
```CSS
#unique { }
```

### Attribute selectors

Deze groep selectors biedt u verschillende manieren om elementen te selecteren op basis van de aanwezigheid van een bepaald attribuut op een element:

```CSS
a[title] { }
```

Of maak zelfs een selectie op basis van de aanwezigheid van een attribuut met een bepaalde waarde:

```CSS
a[href="https://example.com"] { }
```

### Pseudo-classes and pseudo-elements

Deze groep selectors bevat pseudo-klassen, die bepaalde toestanden van een element opmaken. De `:hover` pseudo-class selecteert bijvoorbeeld een element alleen als het door de muisaanwijzer wordt bewogen:

```CSS
a:hover { }
```

Het bevat ook pseudo-elementen, die een bepaald deel van een element selecteren in plaats van het element zelf. Bijvoorbeeld: `:: first-line` selecteert altijd de eerste regel tekst in een element (a `<p>` in het onderstaande geval), en doet alsof een `<span>` rond de eerste opgemaakte regel is gewikkeld en vervolgens geselecteerd.

CSS voorbeeld:
```CSS
p::first-line { }
```

Om eerste element van een bepaald type te selecteren:

CSS voorbeeld:
```CSS
p:first-of-type
```

### Combinators

De laatste groep selectors combineert andere selectors om elementen in onze documenten te targeten. Het volgende selecteert bijvoorbeeld alinea's die directe kinderen zijn van `<article>`  - elementen met behulp van de kindcombinator (`>`):

HTML voorbeeld
```HTML
<article>
    <p>Deze paragraaf zal geselecteerd worden</p>
</article>
<p>Deze paragraaf zal NIET geselecteerd worden</p>
```

CSS voorbeeld:
```CSS
article > p { }
```

---



### Universal selector

De universele selector wordt aangegeven met een asterisk (*). Het selecteert alles in het document (of binnen het bovenliggende element als het wordt samengeketend met een ander element en een onderliggende combinator). In het volgende voorbeeld gebruiken we de universele selector om de marges op alle elementen te verwijderen. In plaats van de standaardstijl die door de browser is toegevoegd - die koppen en alinea's met marges uit elkaar plaatst - staat alles dicht bij elkaar.

```CSS
* {
    margin: 0;
}
```


### OPDRACHT: CSS Dinner

We gaan een oefening maken op Selectors; deze oefening leert je omgaan met selectors & meerbepaald hoe je bepaalde elementen selecteert op een web pagina.

Ga naar [de pagina voor CSS Dinner](https://flukeout.github.io/) en begin de oefeningen te maken.

Bekijk deze video om uitleg te krijgen hoe je de oefening doet.

<video controls width="600">
<source src="uitleg-cssdinner.mkv">
</video>

[Download](uitleg-cssdinner.mkv)