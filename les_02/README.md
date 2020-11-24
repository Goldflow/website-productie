# Les 2: Selectors

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

## 2.2. Selectors

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

Deze groep bevat selectors die gericht zijn op een HTML-element zoals een `<h1>`.

```CSS
h1 { }
```

Het bevat ook selectors die gericht zijn op een klasse:

```CSS
.box { }
```

of een ID:

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

```CSS
p::first-line { }
```

### Combinators

De laatste groep selectors combineert andere selectors om elementen in onze documenten te targeten. Het volgende selecteert bijvoorbeeld alinea's die directe kinderen zijn van `<article>`  - elementen met behulp van de kindcombinator (`>`):

```CSS
article > p { }
```
---

### OPDRACHT: CSS Dinner

We gaan een oefening maken op Selectors; deze oefening leert je omgaan met selectors & meerbepaald hoe je bepaalde elementen selecteert op een web pagina.

Ga naar [de pagina voor CSS Dinner](https://flukeout.github.io/) en begin de oefeningen te maken.

[Bekijk deze video om uitleg te krijgen hoe je de oefening doet.](uitleg-cssdinner.mkv)

