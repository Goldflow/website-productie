# Les 3: Grondbeginselen van HTML-tekst

Een van de kerntaken van HTML is structuur en betekenis aan een tekst geven (ook gekend onder de term [semantiek](https://developer.mozilla.org/en-US/docs/Glossary/semantiek)), zodat een browser de tekst correct kan weergeven. Dit artikel legt uit hoe [HTML](https://developer.mozilla.org/nl/docs/Glossary/HTML) gebruikt kan worden om een pagina te structureren door er koppen en paragrafen aan toe te voegen, woorden te benadrukken, lijsten te creëren en meer.

Vereisten: | Basiskennis HTML die je kunt terugvinden in [Beginnen met HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started).      
---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------
Doel:      | Je leert hoe je een tekst kunt opmaken en hoe je er structuur en betekenis aan kunt geven – inclusief paragrafen, koppen, lijsten, tekst benadrukken en citaten.

## 3.1 De basis: Koppen en Paragrafen

Een gestructureerde tekst bestaat meestal uit koppen of hoofdingen en paragrafen, ongeacht of je nu een verhaal leest, een krant, een leerboek, een magazine enz.

![Een voorbeeld van een voorpagina van een krant, dat het gebruik van koppen, subkoppen en paragrafen laat zien.](https://mdn.mozillademos.org/files/12371/newspaper_small.jpg "Een voorbeeld van een voorpagina van een krant, dat het gebruik van koppen, subkoppen en paragrafen laat zien.")

Een gestructureerde inhoud maakt de leeservaring gemakkelijker en aangenamer.

In HTML moet elke paragraaf ingesloten worden door een [`<p>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/p "Het <p>-element van HTML vertegenwoordigt een paragraaf van tekst. Paragrafen worden meestal vertegenwoordigd in visuele media als blokken tekst, die worden gescheiden van aangrenzende blokken door verticale witruimte en/of inspringing op de eerste regel. Paragrafen zijn elementen op blokniveau.")-element zoals hieronder:

```HTML
<p>Ik ben een paragraaf, laat me je dat vertellen.</p>
```

Elke hoofding moet worden ingesloten door een kop-element:

```HTML
<h1>Ik ben de titel van het verhaal.</h1>
```

Er bestaan zes kop-elementen – [`<h1>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/h1 ""), [`<h2>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/h2 ""), [`<h3>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/h3 ""), [`<h4>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/h4 ""), [`<h5>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/h5 "") en [`<h6>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/h6 ""). Elk element staat voor een verschillend inhoudelijk niveau in het document; `<h1>` vertegenwoordigt de belangrijkste kop, `<h2>` vertegenwoordigt een ondertitel, `<h3>` vertegenwoordigt een ondertitel die zich nog een niveau lager bevindt, enzovoort.

### De implementatie van structurele hiërarchie

We beginnen met een voorbeeld: in een verhaal zou `<h1>` voor de titel van het verhaal worden gebruikt, `<h2>`'s zouden de titel van elk hoofdstuk vertegenwoordigen, `<h3>`'s zouden de ondertitels van elk hoofdstuk vertegenwoordigen, enzovoort.

```HTML
<h1>De Verpletterende Verveling</h1>

<p>door Chris Mills</p>

<h2>Hoofdstuk 1: De donkere nacht</h2>

<p>Het was een donkere nacht. Ergens riep een uil 'oehoe'. Het regende pijpenstelen op de ...</p>

<h2>Hoofdstuk 2: De eeuwige stilte</h2>

<p>Onze protagonist kon uit de schaduwachtige figuur zelfs geen gefluisterd woord krijgen ...</p>

<h3>Het fantoom spreekt</h3>

<p>Meerdere uren waren voorbijgegaan, toen het fantoom plots rechtop ging zitten en schreeuwde: "Heb alsjeblieft erbarmen met mijn ziel!"</p>
```

Jij bent degene die beslist wat je gebruikte elementen uitdrukken, zolang de hiërarchie logisch is. Je hoeft enkel met een paar goede gewoontes rekening te houden als je zulke structuren creëert:

* Bij voorkeur gebruik je slechts één `<h1>` per pagina – dit is de hoogste kop en alle andere zitten eronder in de hiërarchie.
* Zorg ervoor dat je de koppen in de hiërarchie in de juiste volgorde gebruikt. Gebruik geen `<h3>`'s voor ondertitels die dan gevolgd worden door `<h2>`'s om titels onder die ondertitels te vertegenwoordigen. Dat houdt geen steek en zal eigenaardige resultaten veroorzaken.
* Van de zes beschikbare niveaus zou je moeten proberen er niet meer dan drie per pagina te gebruiken, behalve als je vindt dat het nodig is. Documenten met vele niveaus (d.w.z. een diepe koppenhiërarchie) worden onhandelbaar en moeilijk om in te navigeren. In zo'n geval is het aan te raden om de inhoud over meerdere pagina's te spreiden.

### Waarom hebben we structuur nodig

Om deze vraag te beantwoorden, gaan we eerst [text-start.html](https://github.com/mdn/learning-area/blob/master/html/introduction-to-html/html-text-formatting/text-start.html) bekijken – het startpunt van ons voorbeeld waarmee we in dit artikel gaan werken (een lekker hummusrecept). Je kunt het beste een kopie van dit bestand op je lokale machine opslaan, want je zult het later voor de oefeningen nodig hebben. De body van dit document bevat in dit stadium verschillende delen – de inhoud is op geen enkele manier opgemaakt, maar de onderdelen zijn met regeleindes van elkaar gescheiden (op Enter/Return gedrukt om naar de volgende regel te gaan).

Als je het document echter in je browser opent, zul je zien dat de tekst er als één grote brok in zit!

![Een webpagina die een muur van onopgemaakte tekst laat zien, omdat er geen elementen op de pagina zijn om deze te structureren.](https://mdn.mozillademos.org/files/14827/Screen%20Shot%202017-03-29%20at%2009.20.35.png "Een webpagina die een muur van onopgemaakte tekst laat zien, omdat er geen elementen op de pagina zijn om deze te structureren.")

De reden hiervoor is simpel: er staan geen elementen in om de inhoud te structureren, dus weet de browser niet wat een kop is en wat een paragraaf. En bovendien is er dit:

* Gebruikers die een webpagina bekijken, hebben de neiging die snel te scannen op zoek naar relevante inhoud, vaak door eerst slechts de koppen te lezen. (Gewoonlijk [brengen we slechts een zeer korte tijd door op een webpagina](http://www.nngroup.com/articles/how-long-do-users-stay-on-web-pages/).) Als ze in een paar seconden niets nuttigs kunnen vinden, zullen ze waarschijnlijk gefrustreerd raken en ergens anders naartoe gaan.
* Zoekmachines die je pagina indexeren beschouwen de inhoud van de koppen als belangrijke sleutelwoorden die de positie van de pagina in de ranglijsten van de zoekresultaten beïnvloeden. Zonder koppen zal je pagina zwak presteren wat de [SEO](https://developer.mozilla.org/en-US/docs/Glossary/SEO) (_Search Engine Optimization_, "zoekmachine-optimalisatie") betreft.
* Mensen met een ernstige visuele beperking lezen vaak geen webpagina's; in plaats daarvan luisteren ze ernaar. Dit wordt mogelijk gemaakt door een [schermlezer](https://nl.wikipedia.org/wiki/Schermlezer). Deze software verschaft snelle toegang tot een tekstinhoud. Een van de gebruikte technieken houdt in dat een overzicht van het document gegeven wordt door de koppen voor te lezen, zodat de gebruikers de informatie die ze nodig hebben snel kunnen vinden. Als er geen koppen zijn, worden ze gedwongen om het volledige document hardop te laten voorlezen.
* Om inhoud op te maken met [CSS](https://developer.mozilla.org/nl/docs/Glossary/CSS), of om interessante dingen met [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/JavaScript) te doen, is het nodig om de relevante inhoud in elementen in te bedden zodat CSS/JavaScript de inhoud doelgericht kan benaderen.

Het is dus nodig om onze inhoud structureel op te maken.

### Oefening: Onze inhoud structuur geven

We vallen direct met de deur in huis met een live voorbeeld op CodePen.

Voeg in het voorbeeld hieronder elementen aan de ruwe tekst in het HTML-veld toe, zodat die als een kop en twee paragrafen in het resultaat scherm verschijnt.

-> Maak van eerste lijn een titel en 2e en 3e lijn een paragraaf.

[Link naar oefening](https://codepen.io/GoldFlow/pen/dypoqZx)

### Waarom hebben we semantiek nodig

Overal om ons heen vertrouwen we op semantiek – we rekenen op eerdere ervaringen die ons vertellen wat de functie van een alledaags object is; als we iets zien, weten we wat zijn functie zal zijn. Dus we verwachten bijvoorbeeld dat een rood verkeerslicht "stop" betekent en een groen verkeerslicht "vertrek". De dingen kunnen zeer snel ingewikkeld worden als de foute semantiek wordt toegepast. (Zijn er landen die rood gebruiken om "vertrek" uit te drukken? Ik hoop van niet.)

In dezelfde geest moeten we er zeker van zijn dat we de juiste elementen gebruiken om betekenis aan onze tekst, een functie of weergave te geven. In deze context is het [`<h1>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/h1 "The documentation about this has not yet been written; please consider contributing!")-element dus ook een semantisch element, het geeft aan de betreffende tekst de rol (of betekenis) van "een hoofdtitel van je pagina".

```HTML
<h1>Dit is een belangrijke hoofdtitel</h1>
```

Standaard zal de browser dit element een groter lettertype geven om het er als een kop te laten uitzien (alhoewel je het met CSS kunt stylen om het elke look te geven die je wil). Nog belangrijker is dat zijn semantische waarde op meer dan één manier zal worden gebruikt, door bijvoorbeeld zoekmachines en schermlezers (zoals hierboven vermeld).

Aan de andere kant kun je elk element er als een hoofdtitel laten _uitzien_. Bekijk het volgende eens:

```HTML
<span style="font-size: 32px; margin: 21px 0;">Is dit een hoofdtitel?</span>
```

Dit is een [`<span>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/span "The documentation about this has not yet been written; please consider contributing!")-element. Er steekt geen semantiek in. Je gebruikt het element om inhoud te omhullen als je er CSS op wil toepassen (of om er iets mee te doen met JavaScript) zonder er extra betekenis aan te geven. (Je zult er later in de cursus meer over leren.) We hebben wat CSS op het element toegepast om het er als een hoofdtitel te laten uitzien, maar aangezien het geen semantische waarde heeft, zal het geen van de hierboven beschreven extra voordelen krijgen. Het is een goed idee om het relevante HTML-element voor die taak te gebruiken.

## 3.2 Lijsten

Nu gaan we onze aandacht op lijsten richten. Lijsten zijn overal in ons leven – van je boodschappenlijst tot de lijst met aanwijzingen die je onbewust elke dag gebruikt om naar huis te geraken, tot de lijsten met instructies die je in deze handleidingen volgt! Lijsten zijn ook overal op het Web, en er bestaan drie verschillende types.

### Ongeordend

Ongeordende lijsten worden gebruikt om lijsten op te maken waarbij de volgorde van de onderdelen niet belangrijk is – als voorbeeld nemen we een boodschappenlijst.

```HTML
melk
eieren
brood
hummus
```

Elke ongeordende lijst begint met een [`<ul>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/ul "The documentation about this has not yet been written; please consider contributing!")-element – je plaatst het rond alle lijstonderdelen:

```HTML
<ul>
melk
eieren
brood
hummus
</ul>
```

De laatste stap is om elk lijstonderdeel in een [`<li>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/li "The documentation about this has not yet been written; please consider contributing!")-element in te pakken:

```HTML
<ul>
  <li>melk</li>
  <li>eieren</li>
  <li>brood</li>
  <li>hummus</li>
</ul>
```

#### Actief leren: Een ongeordende lijst opmaken

Probeer het live voorbeeld hieronder te bewerken om zo je eigen ongeordende lijst te maken.

[Actief leren: Een geordende lijst opmaken](https://codepen.io/GoldFlow/pen/zYKGmYQ)

### Geordend

Geordende lijsten zijn lijsten waarvan de volgorde van de onderdelen _wel_ belangrijk is – als voorbeeld nemen we een reeks instructies om de weg mee uit te leggen:

```HTML
Rijd naar het einde van de weg
Sla rechtsaf
Rijd rechtdoor bij de eerste twee rotondes
Sla linksaf bij de derde rotonde
De school staat 300 meter verder aan je rechterkant
```

De opmaakstructuur is gelijk aan die voor ongeordende lijsten, behalve dat je de lijstonderdelen in een [`<ol>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/ol "The documentation about this has not yet been written; please consider contributing!")-element (i.p.v. een `<ul>`) moet inpakken:

```HTML
<ol>
  <li>Rijd naar het einde van de weg</li>
  <li>Sla rechtsaf</li>
  <li>Rijd rechtdoor bij de eerste twee rotondes</li>
  <li>Sla linksaf bij de derde rotonde</li>
  <li>De school staat 300 meter verder aan je rechterkant</li>
</ol>
```

#### Actief leren: Een geordende lijst opmaken

Bewerk het live voorbeeld hieronder om je eigen geordende lijst te maken.

[Actief leren: Een geordende lijst opmaken](https://codepen.io/GoldFlow/pen/zYKGmYQ)


### Actief leren: Maak onze receptpagina op

Oké, op dit punt beschik je over alle informatie die je nodig hebt om onze voorbeeldpagina op te maken. Je kunt ervoor kiezen om een locale kopie van ons [text-start.html](https://github.com/mdn/learning-area/blob/master/html/introduction-to-html/html-text-formatting/text-start.html) startbestand op te slaan en het werk daar te doen, of je kunt het in het bewerkbare voorbeeld hieronder doen. Het is waarschijnlijk beter om het locaal te doen, want dan kun je je werk opslaan. Als je het in het bewerkbare voorbeeld doet, zal het verloren gaan als je de pagina later heropent. Beide hebben voor- en nadelen.

[maak een recept pagina na](https://codepen.io/GoldFlow/pen/yLaNRgZ)

### Lijsten nesten

Het is helemaal prima om de ene lijst in een andere te nesten. Je wil wellicht wat subonderdelen onder een hoogste-niveau-lijstonderdeel hebben. Laten we de tweede lijst van ons receptvoorbeeld bekijken:

```HTML
<ol>
  <li>Pel de knoflook en hak in grove stukken.</li>
  <li>Verwijder alle zaden en de steel van de peper en hak in grove stukken.</li>
  <li>Doe alle ingrediënten in een keukenmachine.</li>
  <li>Pureer alles tot een pasta.</li>
  <li>Als je grove hummus met stukjes wil, pureer dan heel even.</li>
  <li>Als je gladde hummus wil, pureer dan wat langer.</li>
</ol>
```

Aangezien er een nauw verband is tussen de laatste twee onderdelen en hetgene dat eraan voorafgaat (ze lezen als sub-instructies of keuzes bij de voorafgaande instructie), kan het logisch zijn om ze in hun eigen ongeordende lijst te nesten, en die lijst in het huidige vierde lijstelement te plaatsen. Dat ziet er dan zo uit:

```HTML
<ol>
  <li>Pel de knoflook en hak in grove stukken.</li>
  <li>Verwijder alle zaden en de steel van de peper en hak in grove stukken.</li>
  <li>Doe alle ingrediënten in een keukenmachine.</li>
  <li>Pureer alles tot een pasta.
    <ul>
      <li>Als je grove hummus met stukjes wil, pureer dan heel even.</li>
      <li>Als je gladde hummus wil, pureer dan wat langer.</li>
    </ul>
  </li>
</ol>
```

Ga naar het vorige "Actief leren"-voorbeeld en werk de tweede lijst op deze manier bij.

## 3.3 Nadruk en belangrijkheid

In menselijke taal benadrukken we vaak bepaalde woorden om de betekenis van een zin te veranderen, en willen we vaak bepaalde woorden als belangrijk of op een bepaalde manier anders markeren. HTML bevat diverse semantische elementen die ons in staat stellen om tekstuele inhoud met zulke effecten op te maken. In deze sectie gaan we een paar van de meest gebruikelijke bekijken.

### Nadruk

Als we in gesproken taal ergens de nadruk op willen leggen, _beklemtonen_ we bepaalde woorden, waarmee we op subtiele wijze de betekenis van wat we zeggen veranderen. In geschreven taal kunnen we op vergelijkbare wijze woorden benadrukken door ze cursief te maken. De twee volgende zinnen hebben bijvoorbeeld verschillende betekenissen.

Ik ben blij dat je niet te laat was.

Ik ben _blij_ dat je niet _te laat_ was.

De eerste zin klinkt oprecht opgelucht omdat de persoon niet te laat was. De tweede zin klinkt daarentegen sarcastisch of passief-aggressief; hij drukt irritatie uit omdat de persoon een beetje te laat aankwam.

In HTML gebruiken we het [`<em>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/em "The documentation about this has not yet been written; please consider contributing!")-element (_emphasis_, nadruk) om zulke gevallen te markeren. Behalve dat het het document interessanter om te lezen maakt, wordt dit element ook herkend door schermlezers en met een andere intonatie uitgesproken. Browsers stylen het element standaard als cursief, maar je kunt het beter niet gebruiken puur voor cursivering. Gebruik daarvoor een [`<span>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/span "The documentation about this has not yet been written; please consider contributing!")-element en wat CSS, of wellicht een [`<i>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/i "The documentation about this has not yet been written; please consider contributing!")-element (zie hieronder).

```HTML
<p>Ik ben <em>blij</em> dat je niet <em>te laat</em> was.</p>
```

### Zeer belangrijke woorden

Om belangrijke woorden te benadrukken, hebben we de neiging om ze in gesproken taal te beklemtonen en om ze in geschreven taal **vet** te maken. Bijvoorbeeld:

Deze vloeistof is **uiterst toxisch**.

Ik reken op je. **Wees niet** te laat!

In HTML gebruiken we het [`<strong>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/strong "The documentation about this has not yet been written; please consider contributing!")-element (_strong importance_, sterke belangrijkheid) om zulke gevallen op te maken. Behalve dat het het document nuttiger, wordt ook dit element herkend door schermlezers en met een andere intonatie uitgesproken. Browsers stylen het element standaard als vette tekst, maar je kunt het beter niet gebruiken puur om vette styling te verkrijgen. Daarvoor kun je beter een [`<span>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/span "The documentation about this has not yet been written; please consider contributing!")-element en wat CSS gebruiken, of wellicht een [`<b>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/b "Het HTML B-element (<b>) representeert een stuk tekst dat qua stijl verschilt van gewone tekst, maar zonder dat het enig belang of relevantie toevoegt. Het is gebruikelijk dat het element wordt toegepast om sleutelwoorden in een samenvatting of productnamen in een recensie vetgedrukt weer te geven. Het element voor datzelfde ook gebruikt voor andere tekst die normaal vetgedrukt wordt weergegeven. Een laatste voorbeeld is het gebruik om de eerste zin van een artikel vetgedrukt te laten zien.")-element (zie hieronder).

```HTML
<p>Deze vloeistof is <strong>uiterst toxisch</strong>.</p>

<p>Ik reken op je. <strong>Wees niet</strong> te laat!</p>
```

Indien gewenst kun je belangrijkheid en nadruk ook in elkaar nesten:

```HTML
<p>Deze vloeistof is <strong>uiterst toxisch</strong> –
als je hem drinkt, <strong>kun je <em>sterven</em></strong>.</p>
```

### Actief leren: Laten we belangrijk zijn

In deze sectie geven we een bewerkbaar voorbeeld. Probeer nadruk en grote belangrijkheid toe te voegen aan de woorden waarvan je denkt dat die ze nodig hebben, gewoon om wat te oefenen.

- link naar oefening moet nog geplaatst worden

### Cursief, vet, onderstrepen...

De elementen die we tot nu toe hebben besproken, hebben duidelijk omschreven semantische waarden. De situatie rond [`<b>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/b "Het HTML B-element (<b>) representeert een stuk tekst dat qua stijl verschilt van gewone tekst, maar zonder dat het enig belang of relevantie toevoegt. Het is gebruikelijk dat het element wordt toegepast om sleutelwoorden in een samenvatting of productnamen in een recensie vetgedrukt weer te geven. Het element voor datzelfde ook gebruikt voor andere tekst die normaal vetgedrukt wordt weergegeven. Een laatste voorbeeld is het gebruik om de eerste zin van een artikel vetgedrukt te laten zien."), [`<i>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/i "The documentation about this has not yet been written; please consider contributing!") en [`<u>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/u "The documentation about this has not yet been written; please consider contributing!") is iets ingewikkelder. Ze onstonden zodat mensen tekst vet, cursief of onderstreept konden maken, in een tijdperk dat CSS nog nauwelijks of helemaal niet ondersteund werd. Dit soort elementen, die enkel de presentatie en niet de semantiek beïnvloeden, staan bekend als **formele elementen** (_presentational elements_ in het Engels) en kunnen beter niet meer gebruikt worden, omdat, zoals we reeds hebben gezien, semantiek belangrijk is voor de toegankelijkheid, SEO, enz.

HTML5 verschafte nieuwe definities voor `<b>`, `<i>` en `<u>` met nieuwe nogal verwarrende semantische rollen.

Dit is de beste vuistregel: het is waarschijnlijk geschikt om `<b>`, `<i>` of `<u>` te gebruiken als je een betekenis wil overbrengen die traditioneel wordt toegekend aan vette, cursieve of onderstreepte tekst, op voorwaarde dat er geen geschikter element is. Het is echter van cruciaal belang dat de toegankelijkheid nooit uit het oog verloren wordt. Het concept cursivering is niet erg nuttig voor mensen die een schermlezer gebruiken, of voor mensen die een ander schrijfsysteem dan het Latijnse alfabet gebruiken.

* [`<i>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/i "The documentation about this has not yet been written; please consider contributing!") wordt gebruikt om een betekenis over te brengen die traditioneel met cursieve tekst wordt weergegeven: woorden uit een andere taal, taxonomische aanduidingen, technische termen, een gedachte...
* [`<b>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/b "Het HTML B-element (<b>) representeert een stuk tekst dat qua stijl verschilt van gewone tekst, maar zonder dat het enig belang of relevantie toevoegt. Het is gebruikelijk dat het element wordt toegepast om sleutelwoorden in een samenvatting of productnamen in een recensie vetgedrukt weer te geven. Het element voor datzelfde ook gebruikt voor andere tekst die normaal vetgedrukt wordt weergegeven. Een laatste voorbeeld is het gebruik om de eerste zin van een artikel vetgedrukt te laten zien.") wordt gebruikt om een betekenis over te brengen die traditioneel met vette tekst wordt weergegeven: sleutelwoorden, productnamen, de eerste zin van een hoofdstuk...
* [`<u>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/u "The documentation about this has not yet been written; please consider contributing!") wordt gebruikt om een betekenis over te brengen die traditioneel met onderstreepte tekst wordt weergegeven: eigennamen, fout gespelde woorden...

Een vriendelijke waarschuwing over onderstreping: **Mensen associëren onderstreping sterk met hyperlinks.** Daarom kun je op het Web het beste slechts hyperlinks onderstrepen. Gebruik het `<u>`-element als het semantisch geschikt is, maar overweeg CSS te gebruiken om de standaard onderstreping te veranderen in iets dat geschikter is voor het Web. Het voorbeeld hieronder illustreert hoe je dat kunt doen.

```HTML
<!-- wetenschappelijke benamingen -->
<p>
  De robijnkeelkolibrie (<i>Archilochus colubris</i>)
  is de meest voorkomende kolibrie in het Oosten van Noord-Amerika.
</p>

<!-- vreemde woorden -->
<p>
  Het menu was een zee van exotische woorden zoals <i lang="uk-latn">vatrushka</i>,
  <i lang="id">nasi goreng</i> en <i lang="fr">soupe à l'oignon</i>.
</p>

<!-- een bekende spelfout -->
<p>
  Op een dag zal ik beter leren <u>spelen</u>.
</p>

<!-- Sleutelwoorden in een reeks instructies markeren -->
<ol>
  <li>
    <b>Snijd</b> twee sneden van het brood.
  </li>
  <li>
    <b>Leg</b> een schijfje tomaat en een blaadje
    sla tussen de sneetjes brood.
  </li>
</ol>
```

## 3.4 Hyperlinks maken

Hyperlinks zijn heel belangrijk – ze maken van het web _een Web_. Dit artikel toont de vereiste syntaxis voor het maken van een koppeling en bespreekt de beste werkwijzen om met koppelingen te werken.

Vereisten: | Basiskennis van HTML, zoals beschreven in [Beginnen met HTML](https://developer.mozilla.org/nl/docs/Learn/HTML/Introduction_to_HTML/Getting_started). Kennis over HTML-tekstopmaak, zoals beschreven in [Grondbeginselen van HTML-tekst](https://developer.mozilla.org/nl/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals).
---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Doel:      | U leert hoe u een hyperlink op een doeltreffende manier aan uw inhoud kunt toevoegen en meerdere bestanden met elkaar kunt verbinden.                                                                                                                                                                                                  

### Wat is een hyperlink?

Hyperlinks zijn een van de meest opwindende vernieuwingen die het web ons biedt. Eigenlijk horen ze er al sinds het allereerste begin bij, maar zij zijn wat van het web _een Web_ maakt - hiermee kunnen we onze documenten met andere documenten (of met een andere informatiebron) verbinden. Ook kunnen we specifieke onderdelen van documenten met elkaar verbinden, en we kunnen apps op een eenvoudig webadres beschikbaar maken (in tegenstelling tot ‘native’ apps, die op voorhand moeten worden geïnstalleerd). Bijna alle webinhoud kan in een koppeling worden omgezet, zodat wanneer hierop wordt geklikt (of deze op een andere manier wordt geactiveerd), de webbrowser naar een ander webadres zal gaan ([URL](https://developer.mozilla.org/en-US/docs/Glossary/URL).)

**Noot**: een URL wijst ook naar HTML-bestanden, tekstbestanden, afbeeldingen, tekstdocumenten, video- en audiobestanden en alles wat er op het web kan leven. Als de browser niet weet hoe deze het bestand moet weergeven of behandelen, zal worden gevraagd of u het bestand wilt openen of downloaden (in dat geval kunt u er later uw ding mee doen). Als u wordt gevraagd het bestand te openen, wordt de verantwoordelijkheid voor die taak doorgegeven naar een geschikte systeemeigen app op het apparaat.

De startpagina van de BBC bijvoorbeeld bevat een groot aantal koppelingen die niet alleen naar meerdere nieuwsartikelen wijzen, maar ook naar verschillende gebieden van de website (navigatiefunctionaliteit), aanmeldings-/registratiepagina’s (gebruikershulpmiddelen) en meer.

![frontpage of bbc.co.uk, showing many news items, and navigation menu functionality](https://mdn.mozillademos.org/files/12405/bbc-homepage.png)

### Anatomie van een koppeling

Een eenvoudige koppeling wordt gemaakt door de tekst (of andere inhoud, zie [Koppelingen op blokniveau](https://developer.mozilla.org/nl/docs/Learn/HTML/Introduction_to_HTML/Hyperlinks_maken#Koppelingen_op_blokniveau)) die u in een koppeling wilt omzetten binnen een [`<a>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/a "Het HTML <a> element (of anker element) maakt een hyperlink naar andere web pagina's, bestanden, lokaties binnen dezelfde pagina, email-adressen of een andere URL.")-element op te nemen, en dat element een `[href](https://developer.mozilla.org/nl/docs/Web/HTML/Element/a#attr-href)`-attribuut te geven (ook bekend als een **Hypertext Reference** of **target**) dat het webadres zal bevatten waarnaar u de koppeling wilt laten wijzen.

```HTML
<p>Ik ben een koppeling naar
<a href="https://www.mozilla.org/nl/">de Mozilla-startpagina</a> aan het maken.
</p>
```

Dit geeft het volgende resultaat:

Ik ben een koppeling naar [de Mozilla-startpagina](https://www.mozilla.org/nl/) aan het maken.

### Ondersteunende informatie toevoegen met het title-attribuut

Een andere attribuut dat u mogelijk aan uw koppelingen wilt toevoegen is `title`; dit is bedoeld voor extra nuttige informatie over de koppeling, zoals het type informatie dat de pagina bevat, of zaken waarvan u zich bewust moet zijn. Voorbeeld:

```HTML
<p>Ik ben een koppeling naar
<a href="https://www.mozilla.org/nl/"
   title="De beste plek om meer informatie over Mozilla’s
          missie te vinden en hoe u daaraan kunt bijdragen">de Mozilla-startpagina</a> 
aan het maken.</p>
```

De code hierboven zorgt ervoor dat de title als een tooltip verschijnt als u de muisaanwijzer boven een koppeling houdt:

Ik ben een koppeling naar [de Mozilla-startpagina](https://www.mozilla.org/nl/ "De beste plek om meer informatie over Mozilla’s missie te vinden en hoe u daaraan kunt bijdragen") aan het maken.

**Noot**: een hyperlink-titel zal alleen verschijnen als u de muis erboven houdt. Dit betekent dat mensen die een toetsenbord gebruiken om in een webpagina te navigeren moeite zullen hebben om de informatie in de tooltip te lezen. Als de informatie van een titel echt nodig is om de pagina te kunnen gebruiken, zou u die moeten aabieden op een manier die voor alle gebruikers toegankelijk is. U kunt de informatie bijvoorbeeld in de normale tekst van de webpagina zetten.

### Actief leren: uw eigen voorbeeldkoppeling maken

[oefening](https://codepen.io/GoldFlow/pen/PoGqxpV)

### Koppelingen op blokniveau

We hebben al vermeld dat u ongeveer alle inhoud in een hyperlink kunt omzetten, zelfs [elementen op blokniveau](https://developer.mozilla.org/nl/Learn/HTML/Introduction_to_HTML/Getting_started#Blok-_versus_inline-elementen). Als u een afbeelding in een koppeling zou willen omzetten, kon u die afbeelding gewoon tussen `<a></a>`-labels zeten.

```HTML
<a href="https://www.mozilla.org/nl/">
  <img src="mozilla-image.png" alt="mozilla-logo dat naar de mozilla-startpagina verwijst">
</a>
```

**Noot**: in een later artikel zult u nog veel meer over het gebruik van afbeeldingen op het web ontdekken.

## Een snelle uitleg over URL’s en paden

Om het doel van een hyperlink volledig te begrijpen, moet u URL’s en bestandspaden begrijpen. Deze sectie verschaft u de informatie die u daarvoor nodig hebt.

Een URL, of Uniform Resource Locator, is gewoon een string (tekst) die bepaalt waar iets op het web kan worden gevonden. Mozilla’s Nederlandstalige startpagina bijvoorbeeld bevindt zich op `https://www.mozilla.org/nl/`.

URL’s gebruiken paden om bestanden te vinden. Paden tonen ons waar een bestand zich in een bestandssysteem bevindt. Laten we een eenvoudig voorbeeld van een mapstructuur bekijken (zie de map [creating-hyperlinks](https://github.com/mdn/learning-area/tree/master/html/introduction-to-html/creating-hyperlinks).)

![Een eenvoudige mapstructuur. De bovenliggende map heet creating-hyperlinks en bevat twee bestanden met de naam index.html en contacts.html, en twee mappen met de naam projects en pdfs, die respectievelijk een bestand index.html en een bestand project-brief.pdf bevatten](https://mdn.mozillademos.org/files/12409/simple-directory.png)

De **hoofdmap** van deze mapstructuur heet `creating-hyperlinks`. Als u op uw lokale computer aan een website werkt, zult u een map hebben waarbinnen de volledige website zich bevindt. In de hoofdmap hebben we een bestand `index.html` en een `contacts.html`. Op een echte website zou `index.html` onze startpagina of landingspagina zijn (een webpagina die als het startpunt voor een website of een bepaalde sectie van een website dient).

In onze hoofdmap zitten ook twee andere mappen – `pdfs` en `projects`. In elk van hen steekt één bestand – respectievelijk een PDF-bestand (`project-brief.pdf`) en een `index.html-bestand`. Twee `index.html`-bestanden kunnnen dus heel goed in één project bestaan, zolang ze op verschillende locaties in het bestandsysteem zijn opgeslagen. Bij veel websites is dit het geval. De tweede `index.html` is misschien de landingspagina voor projectgerelateerde informatie. (Tussen haakjes: een **landingspagina** is een pagina op uw website die specifiek is ingericht voor bezoekers die op die pagina binnenkomen (landen). De bezoeker kan op uw pagina landen via een zoekopdracht of bijvoorbeeld een online- of offlinecampagne die hem of haar naar die specfieke pagina stuurt.)

* **Dezelfde map**: stel dat u een hyperlink aan het bestand `index.html` op het hoogste niveau wilt toevoegen. De hyperlink in deze index.html wijst naar `contacts.html.` U hoeft dan alleen de bestandsnaam van het bestand waarnaar u wilt verwijzen op te geven, omdat dit zich in dezelfde map bevindt als het huidige bestand. De URL is dus gewoon `contacts.html`:

    ```
    <p>Wilt u contact opnemen met een staflid?
    Details vindt u op onze <a href="contacts.html">contactpagina</a>.</p>
    ```

* **Afdalen naar submappen**: stel dat u opnieuw een hyperlink aan het bestand `index.html` in de hoofdmap wilt toevoegen, maar deze keer wijst de hyperlink naar `projects/index.html`. In dat geval zou u omlaag naar de map `projects` moeten gaan voordat u het bestand aangeeft waarnaar u wilt verwijzen. Dit doet u door eerst de naam van de map te noteren, dan een voorwaartse schuine streep te schrijven, en dan de naam van het bestand. De URL zal er dus zo uitzien: `projects/index.html`:

    ```
    <p>Bezoek mijn <a href="projects/index.html">project-startpagina</a>.</p>
    ```

* **Teruggaan naar bovenliggende mappen**: als u een hyperlink in `projects/index.html` wilt plaatsen en u wilt dat die koppeling naar `pdfs/project-brief.pdf` wijst, moet u een niveau omhoog gaan, en dan opnieuw omlaag naar de map `pdf`. ‘Naar een bovenliggende map gaan’ wordt aangegeven via twee puntjes – `..` – dus de te gebruiken URL is `../pdfs/project-brief.pdf`:

    ```
    <p>Een hyperlink naar mijn <a href="../pdfs/project-brief.pdf">projectsamenvatting</a>.</p>
    ```

**Noot**: zo nodig kunt u meerdere instanties van deze eigenschappen in complexe URL’s combineren, bijvoorbeeld `../../../complex/pad/naar/mijn/bestand.html`.

### Documentfragmenten

Het is mogelijk om naar een specifiek deel van een HTML-document te verwijzen. Dit specifieke deel noemen we een **documentfragment**. Om dit te doen hebt u een `[id](https://developer.mozilla.org/nl/docs/Web/HTML/Global_attributes#attr-id)`-attribuut nodig. U moet het toekennen aan het element waarnaar u uw hyperlink wilt laten wijzen. Het is meestal zinvol om er een geschikte kop voor te gebruiken. Die kop zal er ongeveer zo uitzien:

```
<h2 id="E-mailadres">E-mailadres</h2>
```

Om dan naar dat specifieke `id` te verwijzen, voegt u de inhoud van het id aan het einde van de URL toe, voorafgegaan door een hekje (#). Voorbeeld:

```
<p>Wilt u ons een brief schrijven? Gebruik dan ons <a href="contacts.html#e-mailadres">e-mailadres</a>.</p>
```

U kunt het documentfragment zelfs aan _een ander deel van hetzelfde document_ koppelen:

```
<p>Het<a href="#e-mailadres">e-mailadres van ons bedrijf</a> vindt u onderaan de pagina.</p>
```

### Absolute versus relatieve URL’s

Twee termen die u op het web zult tegenkomen zijn **absolute URL** en **relatieve URL:**

**Een absolute URL** wijst naar de absolute locatie op het web. Die locatie houdt ook het [protocol](https://developer.mozilla.org/nl/docs/Glossary/Protocol) en de [domain name](https://developer.mozilla.org/en-US/docs/Glossary/domain_name) in. Stel bijvoorbeeld dat een pagina `index.html` wordt geüpload naar een map die `projects` heet. Als die zich in de hoofdmap (root in het Engels) van een webserver bevindt en het domein van de website is `http://www.example.com`, zou u de pagina op `http://www.example.com/projects/index.html` kunnen vinden. (Of zelfs alleen `http://www.example.com/projects/`, want de meeste webservers zoeken naar een landingspagina zoals `index.html` die ze kunnen laden als deze niet in de URL wordt vermeld.)

Een absolute URL zal altijd naar dezelfde locatie wijzen, waar deze ook wordt gebruikt.

**Een relatieve URL** wijst naar een locatie die _relatief_ is ten opzichte van het bestand vanwaar u verwijst. De koppeling ziet eruit zoals de URL’s die we in de vorige sectie hebben bekeken. Als u bijvoorbeeld een koppeling van ons voorbeeld `http://www.example.com/projects/index.html` naar een PDF-bestand in dezelfde map wilt maken, zou de URL alleen uit de bestandsnaam bestaan – bv. `project-brief.pdf` – extra informatie is dan niet nodig. Als de PDF beschikbaar was in de submap binnen `projects` met de naam `pdfs`, zou de relatieve koppeling `pdfs/project-brief.pdf` zijn (de equivalente absolute URL zou er dan zo uitzien: `http://www.example.com/projects/pdfs/project-brief.pdf`).

Een relatieve URL kan naar verschillende plekken wijzen, afhankelijk van de locatie van het bestand waarin de koppeling wordt vermeld zich bevindt. Als we bijvoorbeeld ons bestand `index.html` uit de map `projects` zouden halen en dit in de hoofdmap van de website zouden plaatsen (het hoogste niveau, geen submappen), zou `pdfs/project-brief.pdf` nu naar `http://www.example.com/pdfs/project-brief.pdf` wijzen en niet naar `http://www.example.com/projects/pdfs/project-brief.pdf`.

## Optimale methoden voor het werken met koppelingen

Er bestaan een aantal ‘beste werkwijzen’ die u kunt volgen als u een hyperlink maakt. Die werkwijzen gaan we hieronder bekijken.

### Verwoord uw koppelingen duidelijk

Het is makkelijk om een paar koppelingen op uw pagina te plaatsen, maar dat is niet genoeg. We moeten onze hyperlinks _toegankelijk_ maken voor alle lezers, ongeacht hun huidige context en hulpmiddelen van hun voorkeur. Voorbeeld:

* Mensen die een schermlezer gebruiken, springen graag van koppeling naar koppeling en lezen die zonder op de context in te gaan.
* Zoekmachines gebruiken hyperlinktekst om doelbestanden te indexeren. Het is dus een goed idee om sleutelwoorden in uw koppelingstekst te gebruiken. Deze sleutelwoorden beschrijven de plek waar de koppeling u naartoe brengt.
* Visuele lezers scannen de tekst in plaats van elk woord te lezen en hun blik zal op pagina-eigenschappen worden gericht die er echt uitspringen, zoals koppelingen. Ze zullen de beschrijvende tekst in een koppeling nuttig vinden.

We bekijken een specifiek voorbeeld:

_**Goede** koppelingstekst:_ [Download Firefox](https://firefox.com/)

```HTML
<p><a href="https://firefox.com/">
  Download Firefox
</a></p>
```

_**Slechte** koppelingstekst:_ [Klik hier](https://firefox.com/) om Firefox te downloaden

```HTML
<p><a href="https://firefox.com/">
  Klik hier
</a>
om Firefox te downloaden</p>
```

Andere tips:

* Herhaal de URL niet als onderdeel van de koppelingstekst – URL’s zijn lelijk en klinken nog lelijker als ze letter voor letter door een schermlezer worden voorgelezen.
* Zeg niet ‘koppeling’ of ‘verwijst naar’ in de koppelingstekst – dit is alleen maar ruis. Schermlezers vertellen gebruikers dat er een koppeling is. Visuele gebruikers zullen weten dat er een koppeling staat, omdat een koppeling standaard wordt onderstreept en ook in een andere kleur zal staan. (Deze conventie kan dus beter niet worden doorbroken, want gebruikers zijn eraan gewend.)
* Houd uw koppelingstekst zo kort mogelijk – lange koppelingen irriteren schermlezergebruikers nog het meest, omdat die naar het hele verhaal moeten luisteren.
* Minimaliseer het gebruik van meerder kopieën van dezelfde tekst die naar verschillende plaatsen wordt verwezen. Dit kan problemen veroorzaken bij gebruikers van schemrlezers, want zij zullen een koppelingen vaker buiten de context ervan lezen – diverse koppelingen met het label ‘klik hier’, ‘klik hier’, ‘klik hier’ zouden verwarrend zijn.

### Gebruik relatieve koppelingen waar mogelijk

Als u de beschrijving hierboven leest, denkt u misschien dat het een goed idee is om altijd absolute koppelingen te gebruiken. Ze kunnen niet defact raken als een pagina van plaats verandert, en relatieve koppelingen zullen dat wel doen. Niettemin is het beter een relatieve koppeling te gebruiken waar dat mogelijk is als u naar locaties _op dezelfde website_ verwijst (Als u naar _een andere website_ verwijst, zult u een absolute koppeling nodig hebben):

* Ten eerste is het veel makkelijker om uw code te scannen – relatieve URL’s zijn in het algemeen veel korter dan absolute URL’s, wat het lezen van code veel makkelijker maakt.
* Ten tweede is het gebruik van relatieve URL’s veel efficiënter. Als u een absolute URL gebruikt, zoekt de browser eerst de echte locatie van de server op door de domeinnaam op de [DNS](https://developer.mozilla.org/nl/docs/Glossary/DNS)-server op te zoeken, vervolgens gaat de browser naar de server waar het bestand zich op bevindt, en pas daarna vindt deze het gevraagde bestand. Een relatieve URL laat de browser naar het gevraagde bestand op dezelfde server zoeken. Als u dus absolute URL’s gebruikt waar relatieve URL’s voldoende zijn, laat u uw browser constant extra werk doen, wat betekent dat deze minder efficiënt werkt.

### Koppelingen naar browservreemde bronnen – gebruik duidelijke wegwijzers

Als u hyperlinks schrijft naar een bron die men downloadt (zoals een PDF- of Word-document), streamt (zoals video of audio) of die een ander potentieel onverwacht effect heeft (een pop-upvenster opent of een Flash-film laadt), voeg dan duidelijke bewoording toe om elke verwarring te vermijden. Het kan zeer bijvoorbeeld zeer vervelend worden:

* Als u een lage bandbreedte hebt, op een koppeling klikt en er onverwacht een download van een meerdere megabytes begint.
* Als u Flash Player niet hebt geïnstalleerd, op een koppeling klikt en u plotseling naar een pagina wordt gebracht die Flash vereist.

Laten we een paar voorbeelden bekijken en wat voor tekst we in dit soort gevallen kunnen gebruiken:

```HTML
<p><a href="http://www.example.com/large-report.pdf">
  Het omzetrapport downloaden(PDF, 10MB)
</a></p>

<p><a href="http://www.example.com/video-stream/">
  De video bekijken (stream opent in apart tabblad, HD-kwaliteit)
</a></p>

<p><a href="http://www.example.com/car-game">
  Het autospel spelen (vereist Flash-software)
</a></p>
```

### Gebruik het download-attribuut als u naar een download verwijst

Als u een koppeling naar een bron schrijft die beter kan worden gedownload dan deze in de browser te openen, kunt u het `download`-attribuut gebruiken en de koppeling een standaard bestandsnaam geven om de download mee op te slaan. Hier is een voorbeeld met een downloadkoppeling naar de Windows-versie van Firefox 39:

```HTML
<a href="https://download.mozilla.org/?product=firefox-39.0-SSL&os=win&lang=nl"
   download="firefox-39-installer.exe">
  Download Firefox 39 voor Windows
</a>
```

## Actief leren: een navigatiemenu maken

Voor deze oefening willen we dat u een paar pagina’s naar elkaar laat verwijzen met een navigatiemenu. Zo kunt u een website maken die uit meerdere pagina’s bestaat. Dit is een gebruikelijke manier – dezelfde paginastructuur wordt op elke pagina herhaald, inclusief het navigatiemenu. Als u dus op de koppelingen klikt, hebt u de indruk dat u op dezelfde plek blijft en dat er verschillende inhoud wordt getoond.

U hebt lokale kopieën van de volgende vier pagina’s nodig, alle vier in dezelfde map (zie ook de map [navigation-menu-start](https://github.com/mdn/learning-area/tree/master/html/introduction-to-html/navigation-menu-start) voor een volledige lijst):

* [index.html](https://github.com/mdn/learning-area/blob/master/html/introduction-to-html/navigation-menu-start/index.html)
* [projects.html](https://github.com/mdn/learning-area/blob/master/html/introduction-to-html/navigation-menu-start/projects.html)
* [pictures.html](https://github.com/mdn/learning-area/blob/master/html/introduction-to-html/navigation-menu-start/pictures.html)
* [social.html](https://github.com/mdn/learning-area/blob/master/html/introduction-to-html/navigation-menu-start/social.html)

Wat u moet doen:

1.  Voeg een ongeordende lijst toe op de aangegeven plek op één pagina, die de namen bevat van de pagina’s waarnaar wordt verwezen. Een navigatiemenu is gewoonlijk niet meer dan een lijst met koppelingen, dus semantisch gezien is dit in orde.
2.  Zet alle paginanamen om naar een hyperlink naar die pagina.
3.  Kopieer het navigatiemenu naar de drie andere pagina’s.
4.  Op elke pagina verwijdert u de koppeling naar zichzelf – dat is alleen maar verwarrend en zinloos, en het ontbreken van een koppeling is een goede visuele herinnering aan de pagina waarop u zich nu bevindt.

Het voltooide voorbeeld zou er ongeveer zo moeten uitzien:

![Een voorbeeld van een eenvoudig HTML-navigatiemenu, met startmenu, afbeeldingen, projecten en sociale menu-items](https://mdn.mozillademos.org/files/12411/navigation-example.png)

**Noot**: als u vastloopt, of er niet zeker van bent dat u het allemaal juist hebt, kunt u de map [navigation-menu-marked-up](https://github.com/mdn/learning-area/tree/master/html/introduction-to-html/navigation-menu-marked-up) bekijken om het juiste antwoord te zien.

## E-mailkoppelingen

Het is mogelijk om koppelingen of knoppen te maken die een nieuwe e-mailbericht openen, als erop wordt geklikt. Dit is mogelijk door het gebruik van het [`<a>`](https://developer.mozilla.org/nl/docs/Web/HTML/Element/a "Het HTML <a> element (of anker element) maakt een hyperlink naar andere web pagina's, bestanden, lokaties binnen dezelfde pagina, email-adressen of een andere URL.")-element en het URL-schema `mailto:`.

In de meest eenvoudige en gebruikelijke vorm duidt een ‘`mailto:`-koppeling’ gewoon het e-mailadres van de bedoelde ontvanger aan. Voorbeeld:

```HTML
<a href="mailto:nowhere@mozilla.org">E-mail nergens naartoe verzenden</a>
```

Het resultaat is een koppeling die er zo uitziet: [E-mail nergens naartoe verzenden](mailto:nowhere@mozilla.org).

In feite is het e-mailadres zelfs optioneel. Als u het weglaat (dat wil zeggen, uw `[href](https://developer.mozilla.org/nl/docs/Web/HTML/Element/a#attr-href)` is gewoon "mailto:"), zal een nieuw venster voor uitgaande e-mail worden geopend door het e-mailprogramma van de gebruiker waarin nog geen bestemmingsadres is ingevuld. Dit is vaak nuttig voor het ‘Delen’ van koppelingen waarop gebruikers kunnen klikken om een e-mailbericht naar een zelfgekozen e-mailadres te sturen.

### Details toevoegen

Behalve het e-mailadres kunt u nog andere informatie toevoegen. In feite kunnen alle kopregels van een standaardmail worden toegevoegd aan de `mailto`-URL die u opgeeft. De meest gebruikelijke zijn ‘subject’ (onderwerp), ‘cc’, en ‘body’ (body is de inhoud, body is geen echt headerveld, maar u kunt er een korte inhoud van het nieuwe e-mailbericht mee opgeven). Elk veld en de waarde ervan wordt als zoekterm opgegeven.

Hier is een voorbeeld met cc, bcc, subject en body:

```HTML
<a href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&amp;subject=The%20subject%20of%20the%20email &amp;body=The%20body%20of%20the%20email">
  E-mail verzenden met cc, bcc, subject en body
</a>
```

**Noot:** de waarden van elk veld moeten URL-gecodeerd zijn, d.w.z. met niet-afdrukbare tekens (onzichtbare tekens zoals tabs, enters en pagina-einden) en spaties [‘percent-escaped’](http://en.wikipedia.org/wiki/Percent-encoding)). Let ook op het gebruik van het vraagteken (`?`) om de hoofd-URL van de ingevoerde waarden te scheiden, en de ampersand (&) om de velden in de `mailto:`-URL van elkaar te scheiden. Dit is standaard URL-zoeknotatie. U kunt de [De GET-methode](https://developer.mozilla.org/nl/docs/Learn/HTML/Forms/Sending_and_retrieving_form_data#De_GET-methode) lezen als u meer over URL-querynotatie wilt weten.)

Dit zijn enkele voorbeelden van `mailto`-URL’s:

* mailto:
* mailto:nowhere@mozilla.org
* mailto:nowhere@mozilla.org,nobody@mozilla.org
* mailto:nowhere@mozilla.org?cc=nobody@mozilla.org
* mailto:nowhere@mozilla.org?cc=nobody@mozilla.org&subject=Dit%20is%20het%20onderwerp
