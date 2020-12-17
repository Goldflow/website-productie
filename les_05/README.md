# Les 5: Zelf website hosten + CSS Layout

## 5.1 Hosting

### Netlify

* Login op [Github.com](https://www.github.com)
* ga naar [https://app.netlify.com/](https://app.netlify.com/) en kies login met Github (dus je moet geen nieuwe account maken)

Volg onderstaande gids om te zien hoe je iets host.

<video width="600" controls>
<source src="netlify-host.mkv">
</video>

Hoe een website terug te verwijderen:

<video width="600" controls>
<source src="netlify-delete.mkv">
</video>

### Surge

* Installeer [NodeJS](https://nodejs.org/en/)
* type CMD (of bash op Apple) en voer het volgende commando in: `npm i surge -g`
* navigeer naar de web folder die je wel online zetten en typ: `surge`
* volg de stappen (tip gebruik een zeer eenvoudig paswoord)

Meer informatie hier:

[https://surge.sh/](https://surge.sh/)

## 5.2 CSS Layout

Deze les geeft een samenvatting van enkele van de CSS-lay-outfuncties die we al hebben behandeld in eerdere modules - zoals verschillende [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display ) waarden - en introduceer enkele van de concepten die we in deze module zullen behandelen.

### Vereisten
De basisprincipes van HTML (studie [Inleiding tot HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML)), en een idee van hoe CSS werkt (studie [Inleiding tot CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS).)

### Doelstelling
Om u een overzicht te geven van CSS-pagina lay-out technieken. Elke techniek kan in meer detail worden geleerd in volgende tutorials.

CSS-pagina lay-out technieken stellen ons in staat elementen op een webpagina te nemen en te bepalen waar ze worden gepositioneerd ten opzichte van hun standaardpositie in de normale lay-outstroom, de andere elementen eromheen, hun bovenliggende container of het hoofdvenster / venster. De technieken voor pagina-indeling die we in deze module meer in detail zullen behandelen, zijn

* Normal flow (Normale stroom)
* De eigenschap [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
* Flexbox
* Grid (Raster)
* Floats
* Positioning
* Table layout (Tafel-indeling)
* Multiple-column layout

Elke techniek heeft zijn toepassingen, voor- en nadelen, en geen enkele techniek is ontworpen om afzonderlijk te worden gebruikt. Als u begrijpt waarvoor elke methode is ontworpen, bent u op een goede plek om te begrijpen wat de beste lay-outtool is voor elke taak.

## [Normal flow](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Introduction#Normal_flow "Permalink to Normal flow")

Normal flow (normale stroom) is hoe de browser standaard HTML-pagina's opmaakt als u niets doet om de pagina-indeling te regelen. Laten we eens kijken naar een snel HTML-voorbeeld:

```HTML
<p>I love my cat.</p>

<ul>
  <li>Buy cat food</li>
  <li>Exercise</li>
  <li>Cheer up friend</li>
</ul>

<p>The end!</p>
```

Standaard geeft de browser deze code als volgt weer:

I love my cat.

* Buy cat food
* Exercise
* Cheer up friend

The end!

Merk hier op hoe de HTML wordt weergegeven in de exacte volgorde waarin deze in de broncode voorkomt, met elementen op elkaar gestapeld - de eerste alinea, gevolgd door de ongeordende lijst, gevolgd door de tweede alinea.

De elementen die onder elkaar verschijnen, worden beschreven als _block_-elementen, in tegenstelling tot _inline_-elementen, die naast elkaar verschijnen, zoals de afzonderlijke woorden in een alinea.

**Opmerking**: de richting waarin de inhoud van de blokelementen wordt opgemaakt, wordt beschreven als de blokrichting. De blokrichting wordt verticaal uitgevoerd in een taal zoals Engels, die een horizontale schrijfmodus heeft. Het zou horizontaal werken in elke taal met een verticale schrijfmodus, zoals Japans. De corresponderende Inline Direction is de richting waarin inline inhoud (zoals een zin) zou lopen.

Voor veel van de elementen op uw pagina zal de normale stroom precies de lay-out creëren die u nodig heeft, maar voor complexere lay-outs moet u dit standaardgedrag wijzigen met behulp van enkele van de tools die voor u beschikbaar zijn in CSS. Beginnen met een goed gestructureerd HTML-document is erg belangrijk, omdat je dan kunt werken met de manier waarop dingen standaard zijn ingedeeld in plaats van ertegen te vechten.

De methoden die de indeling van elementen in CSS kunnen veranderen, zijn als volgt:

* **De eigenschap [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)** - Standaardwaarden zoals` block`, `inline` of` inline -block` kan veranderen hoe elementen zich gedragen in normale stroom, bijvoorbeeld door een element op blokniveau te laten gedragen als een inline-element (zie Soorten CSS-boxen voor meer informatie). We hebben ook volledige lay-outmethoden die worden ingeschakeld via specifieke 'weergave'-waarden, bijvoorbeeld [CSS Grid](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids) en [ Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox), die de indeling van elementen in het element waarop ze zijn ingesteld, wijzigen.
* **Floats** - Het toepassen van een [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float) waarde zoals` left` kan ervoor zorgen dat blokniveau-elementen omwikkelen naast één kant van een element, zoals de manier waarop afbeeldingen soms tekst om zich heen laten zweven in tijdschriftlay-outs.
* ** De [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position)

* **De eigenschap [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position)** - Hiermee kunt u nauwkeurig de plaatsing van dozen in andere dozen regelen. `statische` positionering is de standaard in normale stroom, maar u kunt ervoor zorgen dat elementen anders worden ingedeeld met behulp van andere waarden, bijvoorbeeld altijd bevestigd aan de bovenkant van de browser viewport.
* **Tabelopmaak** - functies die zijn ontworpen om de delen van een HTML-tabel op te maken, kunnen worden gebruikt op niet-tabelelementen met behulp van `display: table` en bijbehorende eigenschappen.
* **Multi-column layout** - De [Multi-column layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Columns) eigenschappen kunnen ervoor zorgen dat de inhoud van een blok lay-out in kolommen, zoals u misschien in een krant ziet.

## [The display property](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Introduction#The_display_property "Permalink to The display property")

De belangrijkste methoden om een ​​pagina-indeling in CSS te bereiken, zijn alle waarden van de eigenschap 'weergave'. Met deze eigenschap kunnen we de standaard manier wijzigen waarop iets wordt weergegeven. Alles in de normale stroom heeft de waarde 'weergave', die wordt gebruikt als de standaard manier waarop elementen waarop ze zijn ingesteld zich gedragen. Het feit dat alinea's in het Engels onder elkaar worden weergegeven, is bijvoorbeeld te wijten aan het feit dat ze zijn gestileerd met 'display: block'. Als u een link maakt rond een tekst in een alinea, blijft die link inline met de rest van de tekst en wordt deze niet afgebroken op een nieuwe regel. Dit komt doordat het element [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) standaard` display: inline` is.

U kunt dit standaard weergavegedrag wijzigen. Het element [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) is bijvoorbeeld standaard `display: block`, wat betekent dat lijstitems onder elkaar weergeven in ons Engelse document. Als we de weergavewaarde wijzigen in 'inline', worden ze nu naast elkaar weergegeven, zoals woorden in een zin zouden doen. Het feit dat u de waarde van `display` voor elk element kunt wijzigen, betekent dat u HTML-elementen kunt kiezen voor hun semantische betekenis, zonder dat u zich zorgen hoeft te maken over hoe ze eruit zullen zien. De manier waarop ze eruit zien, is iets dat u kunt veranderen.

Naast de mogelijkheid om de standaardpresentatie te veranderen door een item van `block` naar` inline` en vice versa te veranderen, zijn er enkele grotere lay-outmethodes die beginnen als een waarde van `display`. Als u deze echter gebruikt, moet u in het algemeen aanvullende eigenschappen aanroepen. De twee waarden die voor onze doeleinden het belangrijkst zijn wanneer we de lay-out bespreken, zijn `display: flex` en` display: grid`.

## [Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Introduction#Flexbox "Permalink to Flexbox")

Flexbox is de korte naam voor de module [Flexible Box Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout) Module, ontworpen om het ons gemakkelijk te maken om dingen in één dimensie - als rij of als kolom. Om flexbox te gebruiken, past u `display: flex` toe op het bovenliggende element van de elementen die u wilt opmaken; al zijn directe kinderen worden dan flexitems. We kunnen dit zien in een eenvoudig voorbeeld.

De HTML-opmaak hieronder geeft ons een bevattend element, met een klasse `wrapper`, waarin drie `<div>` elementen. Standaard worden deze weergegeven als blokelementen, onder elkaar, in ons Engelstalige document.

Als we echter `display: flex` aan de ouder toevoegen, rangschikken de drie items zichzelf in kolommen. Dit komt doordat ze _flex items_ worden en worden beïnvloed door enkele initiële waarden die flexbox instelt op de flexcontainer. Ze worden in een rij weergegeven, omdat de initiële waarde van [`flex-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction) ingesteld op hun ouder is` rij`. Ze lijken allemaal uit te rekken tot de hoogte van het hoogste item, omdat de initiële waarde van de [`align-items`](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items ) eigenschap ingesteld op hun ouder is `stretch`. Dit betekent dat de items uitrekken tot de hoogte van de flexcontainer, die in dit geval wordt bepaald door het hoogste item. De items staan ​​allemaal aan het begin van de container, zodat er aan het einde van de rij extra ruimte overblijft.

### Flexbox Voorbeeld 1

```CSS
* {box-sizing: border-box;}

.wrapper > div {
    border-radius: 5px;
    background-color: rgb(207,232,220);
    padding: 1em;
}
```

```CSS
.wrapper {
  display: flex;
}
```

```HTML
<div class="wrapper">
  <div class="box1">One</div>
  <div class="box2">Two</div>
  <div class="box3">Three</div>
</div>
```

[probeer het hier uit](https://codepen.io/GoldFlow/pen/VwKpyKY)

Naast bovenstaande eigenschappen die op de flexcontainer kunnen worden toegepast, zijn er eigenschappen die op de flex items kunnen worden toegepast. Deze eigenschappen kunnen onder andere de manier waarop de items buigen veranderen, waardoor ze kunnen uitzetten en inkrimpen om in de beschikbare ruimte te passen.

Als een eenvoudig voorbeeld hiervan kunnen we de eigenschap [`flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex) aan al onze onderliggende items toevoegen, met een waarde van `1`. Hierdoor zullen alle items groeien en de container vullen, in plaats van aan het einde ruimte te laten. Als er meer ruimte is, worden de items breder; als er minder ruimte is, worden ze smaller. Als u bovendien een ander element aan de opmaak toevoegt, worden de items allemaal kleiner om er ruimte voor te maken - ze zullen de grootte aanpassen om dezelfde hoeveelheid ruimte in te nemen, wat dat ook is.

```CSS
.wrapper {
    display: flex;
}

.wrapper > div {
    flex: 1;
}
```

```HTML
<div class="wrapper">
    <div class="box1">One</div>
    <div class="box2">Two</div>
    <div class="box3">Three</div>
</div>
```

Meer hier over [Flexbox](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Flexbox)

#### Opdracht: Flexbox Froggy

Maak deze oefening om over Flexbox te leren:
[Flexbox Froggy](https://flexboxfroggy.com/#nl)

#### Oefening Flexbox.IO

Op de volgende website, kan je je gratis registreren voor een video cursus om Flexbox te leren. Ga naar de site en registreer je met een mail om de cursus te beginnen:

[https://flexbox.io/](https://flexbox.io/)

## [Grid Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Introduction#Grid_Layout "Permalink to Grid Layout")

Terwijl flexbox is ontworpen voor een eendimensionale lay-out, is rasterlay-out ontworpen voor twee dimensies: dingen uitlijnen in rijen en kolommen.

Nogmaals, u kunt Grid Layout inschakelen met een specifieke waarde van display - `display: grid`. Het onderstaande voorbeeld gebruikt vergelijkbare markeringen als het flex-voorbeeld, met een container en enkele onderliggende elementen. Naast het gebruik van `display: grid`, definiëren we ook enkele rij- en kolomsporen op de bovenliggende pagina met behulp van de `grid-template-rijen` en [`grid-template-columns`](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns) eigenschappen. We hebben drie kolommen van elk '1fr' en twee rijen van '100px' gedefinieerd. Ik hoef geen regels te stellen voor de onderliggende elementen; ze worden automatisch in de cellen geplaatst die ons raster heeft gemaakt.

### Oefening GRID LAYOUT

[link](https://codepen.io/GoldFlow/pen/KKgWZao)

```CSS
.wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 100px 100px;
    grid-gap: 10px;
}
```

```HTML
<div class="wrapper">
    <div class="box1">One</div>
    <div class="box2">Two</div>
    <div class="box3">Three</div>
    <div class="box4">Four</div>
    <div class="box5">Five</div>
    <div class="box6">Six</div>
</div>
```

Als u eenmaal een raster heeft, kunt u uw items er expliciet op plaatsen, in plaats van te vertrouwen op het gedrag van automatische plaatsing dat hierboven wordt weergegeven. In het tweede voorbeeld hieronder hebben we hetzelfde raster gedefinieerd, maar deze keer met drie onderliggende items. We hebben de begin- en eindregel van elk item ingesteld met behulp van de eigenschappen rasterkolom en rasterrij. Dit zorgt ervoor dat de items meerdere sporen beslaan.

```CSS
.wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 100px 100px;
    grid-gap: 10px;
}

.box1 {
    grid-column: 2 / 4;
    grid-row: 1;
}

.box2 {
    grid-column: 1;
    grid-row: 1 / 3;
}

.box3 {
    grid-row: 2;
    grid-column: 3;
}
```

```HTML
<div class="wrapper">
    <div class="box1">One</div>
    <div class="box2">Two</div>
    <div class="box3">Three</div>
</div>
```

Opmerking: deze twee voorbeelden zijn slechts een klein deel van de kracht van Grid layout; Zie ons les Rasterlay-out voor meer informatie.

De rest van deze handleiding behandelt andere lay-outmethoden, die minder belangrijk zijn voor de belangrijkste lay-outstructuren van uw pagina, maar die u toch kunnen helpen bij het uitvoeren van specifieke taken. Als u de aard van elke lay-outtaak begrijpt, zult u snel merken dat wanneer u naar een bepaald onderdeel van uw ontwerp kijkt, het type lay-out dat er het meest geschikt voor is, vaak duidelijk zal zijn.

---

