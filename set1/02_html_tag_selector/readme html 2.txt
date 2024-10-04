Prima pagina


Paginile web sunt construite folosind 2 tehnologii de baza: HTML si CSS



HTML ofera posibilitatea de a adauga continut, simplu text, imagini, tabele, liste, link-uri fara a face prea mult pentru a le stiliza si aseza in pagina.

CSS se ocupa de stilizare, asta insemnand setarea proprietatilor pentru elementele HTML din document: dimensiune, asezare in pagina, culoare, font, background si multe altele, sunt multe proprietati CSS care au aparut de-a lungul anilor pentru a acoperi nevoile de stilizare.

HTML este prescurtarea de la HypeText Markup Language, care pe scurt semnifica limbaj care marcheaza continutul unui document.

CSS provine de la Cascade Style Sheet insemnand foi de stiluri care se aplica in ‘cascada’. Cascade aici inseamna ca toate regulile dintr-o foaie de stiluri se aplica de la prima pana la ultima. Daca un element e stilizat de 2 ori, ultima stilizare are prioritate. 

Mai multe detalii despre cascade si specificity

(https://developer.mozilla.org/en-US/docs/Web/CSS/Cascade)

Mai exista o posibilitate de aplicare a ideii de cascada. Unele proprietati au posibilitatea sa fie mostenite de elementele descendenti.
Adica daca este setata pentru un element HTML parinte, acea proprietate se va aplica si pentru elementele descendenti (se aplica in cascada asupra descendentilor).

Mai multe referitor la mostenire (inheritance) pe site-ul MDN
(https://developer.mozilla.org/en-US/docs/Web/CSS/Inheritance)

Cele doua limbaje sunt independente. Ca regula generala nu vom scrie CSS in interiorul unui fisier HTML (desi se poate). Vom cauta sa le tinem separate.

Deoarece nu se poate aplica CSS decat pentru elemente HTML mai intai se studiaza limbajul HTML.








Termeni folositi pentu limbajul HTML



Vom intalni adesea termenii de element, tag(eticheta) si atribut.

Elemente
Elementele HTML sunt componenetele sau obiectele dintr-un document HTML. Ne vom referi la ele dupa cum este si rolul lor. Titluri (headings), paragrafe(paragraphs), imagini(images), liste(lists), link-uri (links). Pot fi elemente care sa contina alte elemente. Cele din interior se cheama ‘nested’, in romana vom incerca sa le denumim doar descendenti. Nest inseamna cuibar dar nested are semnificatia de a contine ceva la modul general, e o analogie la modul cum pasarile stau in interiorul cuibului. Elementele “cuib” le vom denumi elemente parinte (parent element, parent node) iar cele din interiorul elementului parinte se vor chema descendenti (children, child nodes)

Tot timpul vom avea de a face cu aceasta ierarhie. Elementul body va fi parinte pentru toate elementele din document iar un element section sau main va contine paragrafe, titluri, imagini etc.

Tag-uri
 Elementele sunt create folosind tag-uri (etichete). Un tag are forma <nume-tag>

In mod normal vom avea elemente sub forma
<tag>...continut text ...</tag>
de exemplu paragrafe

<p>Un paragraf</p>

Partea de la inceput <tag> se numeste ‘tag de deschidere, iar partea de final, </tag>, se numeste tag de inchidere. Diferenta e data de existenta simbolului slash ‘/’.

Nu toate elementele au tag de inchidere. Acolo unde nu exista text se poate fara tag de inchidere, de exemplu pentru imagini:

<img src=”imagine1.jpg” />

Simbolul slash folosit in tag-ul de deschidere simbolizeaza ca se si inchide, nu mai e nevoie de un tag de inchidere dedicat.

Obs
Un astfel de element care nu are decat tag de deschidere nu poate fi parinte pentru alte elemente, nu are unde sa le contina. Descendentii pot fi adaugati doar intre tag-ul de deschidere si cel de inchidere nu in atribute.

Atribute
Desi tag-ul <img> nu are tag de inchidere, are insa o alta componenta care ajuta la adaugarea de informatii si anume atribut.
In elementul imagine

<img src =”imagine1.jpg” />

exista o componenta denumita atribut, atributul src cu valoarea “imagine1.jpg”. 

Informatia necesara pentru afisarea unui element imagine e redusa, doar numele fisierului imagine, deci se prefera inserarea informatiei direct in interiorul tag-ului folosind un atribut, in acest caz atributul “src” (source). Asta inseamna si faptul ca neavand continut care sa fie delimitat de tag-ul de inchidere, tag-ul de inchidere nu mai este necesar.

Atributul are astfel un nume (src) si o valoare (imagine1.jpg).
 src = “imagine1.jpg”. 

Pot fi mai multe atribute intr-un tag. Doar pentru exemplificare se poate folosi un atribut mai vechi ‘width’. 
Obs: Atributul width nu mai este folosit acum, rolul lui a fost preluat de proprietatea CSS width. 

Atributul width poate seta latimea imaginii:

<img src = “imagine1.jpg” width = “320” />

permite setarea latimii imaginii la 320 pixeli

Putem avea atribute si in tag-urile obisnuite, cele cu tag de inchidere

De exemplu pentru link-uri
<a href = “http://www.w3schools.com”>
Invata HTML </a>

Aici continutul care se afla in interiorul tag-ului va fi textul vizibil pentru link “Invata HTML” dar link-ul propriu-zis este stocat in atributul href care contine adresa unde trimite link-ul, “http://www.w3schools.com”

Obs: Atat elementul imagine(<img>) cat si elementul link (<a>) sunt doar exemplificative pentru atribute, vom reveni la ele.

Astfel forma generala pentru un tag este:

<tag attr1 = ” val1 ” attr1 = ” val2 ”...> 
  ...contintut text, imagine sau alte elemente HTML
</tag>

sau

<tag attr1 = “val1” attr2 = “val2” />






CSS (Cascade Style Sheet)



Termeni folositi pentru limbajul CSS

Pe langa termenii folositi in cazul limbajului HTML exista cativa termeni pe care ii vom folosi in mod curent pentru CSS: selectori, proprietati si valori (selectors, properties, values).

Selectori (selectors)

Orice element vizibil adaugat in pagina web poate fi stilizat. Un selector se refera la un anumit element oricare ar fi el. Deoarece pot fi sute sau chiar mii de elemente intr-o pagina, selectorii pot fi complecsi, depinzand cat de precisi dorim sa fim cand ii ‘selectam’ pentru stilizare. Daca dorim sa selectam toate paragrafele din pagina atunci selectorul este simplu in acest caz, fiind tipul de element si anume ‘p’ . Va selecta toate paragrafele <p> din pagina.

Pentru a selecta toate tilurile <h1> vom folosi ‘h1’ iar pentru toate link-urile vom folosi ‘a’

In interiorul sectiunii CSS selectorii sunt insotiti de acolade {...} care reprezinta un container cu stilurile care sunt aplicate acelui selector.

p {...}

Proprietati(properties)

Odata ce un element este selectat, in blocul determinat de acolade se vor afla proprietatile care vor aplica stiluri pentru acel element.

p {
   color:   ....  ;
   font-size:  .... ;
}

Valoare
Fiecare proprietate este urmata de simbolul ‘:’ si apoi valoarea proprietatii. Dupa valoare se adauga ‘;’.

Un selector urmat de un bloc de proprietati si valori reprezinta o  un set de reguli CSS.


p {
   color: green;
   font-size: 14px;
}

 Este obligatoriu ‘;’ la finalul fiecarei reguli. Dace nu este adaugat ‘;’ la finalul regulii CSS, regulile care urmeaza sunt ignorate







Utilizarea selectorilor


Selectorii indica ce elemente HTML sunt stilizate. Cei mai utilizati selectori sunt:
selectorul element type
selectorul class
selectorul ID

Selectorul ‘element type’ indica elementele dupa tipul lor. De exemplu daca dorim sa selectam toate paragrafele si sa le coloram in verde vom folosi selectorul ‘p’

p { color : green; }

In acest fel toate paragrafele din document vor fi colorate in verde

<p>paragraf1</p>
<p>paragraf2</p>

rezultat:
paragraf1
paragraf2

Selectorul ‘class’

Nu intotdeauna ne dorim sa selectam toate elementele de un anumit tip. De obicei dorim sa ‘selectam’ doar o anumita ‘clasa’ de elemente. Clasa va avea un nume care va fi atasat elementului folosind atributul ‘class’

De exemplu dorim din 4 paragrafe doar doua sa fie colorate in verde

.verde { color : green; }

<p class=”verde”>paragraf1</p>
<p>paragraf2</p>
<p class=”verde”>paragraf3</p>
<p>paragraf4</p>

rezultat:

paragraf1
paragraf2
paragraf3
paragraf4

O clasa este denumita de catre noi si poate avea orice nume. Inainte de nume se adauga simbolul punct ‘.’ , in acest fel am transmis browser-ului ca este o clasa si nu un selector tip element

Selectorul de tip ID

ID-ul se adauga ca si in cazul clasei cu un atribut ‘id’

ID-ul este unic si se utilizeaza atunci cand dorim sa selectam un singur element.

#titlul-principal {
    color: red;
    font-size:20px;
}

.titlu-h2 {
   color: gray;
   font-size: 16px;
}

<h1 id=”titlul-principal”> Welcome! </h1>

<h2 class=”titlu-h2”> Prima sectiune </h2>
...
<h2 class=”titlu-h2”> A doua sectiune </h2>

rezultat:
Welcome

Prima sectiune
....
A doua sectiune

In acest caz titlul principal e unic si putem folosi un selector ID pentru el.

Titlurile de nivel 2 pot fi mai multe si atunci putem folosi selector de tip clasa pentru fiecare titlu.

Un selector de tip ID poate fi denumit oricum dar trebuie sa aiba la inceputul numelui simbolul diez ‘#’ / hash.





Adaugare CSS in pagina

Regulile CSS in general sunt stocate in fisiere separate in afara fisierului HTML. Apoi fisierul CSS poate fi integrat in pagina folosind tag-ul <link> in interiorul tag-ului <head>

Daca fisierul cu reguli CSS se numeste “stiluri.css” atunci in atributul href din <link> se adauga numele fisierului, “stiluri.css”. Sau calea la fisier “./stiluri.css”, in acest caz folderul in care se afla fisierul HTML.

Daca fisierul “stiluri.css” se afla intr-un alt folder, de exemplu folderul “styles” contine fisierul “stiluri.css”, va trebui sa oferim calea completa: href = “./styles/stiluri.css”

<head>
  <link rel = “stylesheet” href = “stiluri.css”>
</head>

Obs. Veti putea adauga elementul link folosind optiunea autocomplete atunci cand tastati ‘link’


Mai exista posibilitatea crearii unui tag <style> in interiorul lui <head> si acolo pot fi adaugate reguli CSS. Nu este considerata o idee buna pentru proiecte mai mari dar pentru teste si proiecte mici poate fi folosita.

<head>
  <style>
....reguli CSS
  </style>
</head>


Exista si posibilitatea adaugarii de stiluri pentru fiecare element in parte folosind atributul style(stilizare inline). Valoarea lui style va fi formata din lista de proprietati CSS si valori. Nu este insa o metoda recomandata.

Ex:
<p style = “color: red;”>paragraf stilizat inline </p>


Ex1: headings h1, h2, paragrafe p

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>tag-uri si atribute</title>
</head>

<body>
    <!-- elementele de tip heading si paragraf fac parte din aceeasi clasa de elemente pentru adaugat text -->
    <h1>Bine ai venit</h1>
    <h2>Prima pagina web</h2>
    <p>Aici este text obisnuit</p>

    <img src = "./imagine.jpg" width="320">  <!-- o imagine cu dimensiunea pe latime de 320 pixeli -->
</body>

</html>


Ex2: Stiluri CSS interne

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adaugare CSS in pagina</title>
    <style>
        #titlul-principal {
            color: red;
            font-size: 20px;
        }

        .titlu-h2 {
            color: gray;
            font-size: 16px;
        }
    </style>
</head>

<body>
    <h1 id="titlul-principal"> Adaugare de stiluri CSS </h1>
    <p><strong>Exista 3 metode:</strong></p>
    <p>stiluri interne, stiluri inline si stiluri externe</p>

    <h2 class="titlu-h2"> Stiluri interne </h2>
    <p>Se adauga folosind tag-ul <strong>'style' </strong>in elementul head</p>

    <h2 class="titlu-h2"> Stiluri externe</h2>
    <p>Se adauga folosind tag-ul <strong>link</strong> si se specifica la href numele fisierului .css</p>

    <h2 class="titlu-h2">Stiluri inline</h2>
    <p>Stilurile inline nu sunt recomandate, nu le vom folosi. Totusi le veti vedea uneori pe Internet in exemple de
        mici dimensiuni. Sunt adaugate intr-un element folosind atributul <strong>style</strong></p>
</body>

</html>


Ex3: Stiluri CSS externe, tag-ul link

fisier extern stiluri.css

#titlul-principal {
    color: red;
    font-size: 20px;
}

.titlu-h2 {
    color: gray;
    font-size: 16px;
}


fisierul index.html are referinta la stiluri.css prin intermediul tag-ului link

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adaugare CSS in pagina</title>


     <!-- tag-ul link reprezinta referinta la fisierul .css -->
    <link rel="stylesheet" href="./stiluri.css">


</head>

<body>
    <h1 id="titlul-principal"> Adaugare de stiluri CSS </h1>
    <p><strong>Exista 3 metode:</strong></p>
    <p>stiluri interne, stiluri inline si stiluri externe</p>

    <h2 class="titlu-h2"> Stiluri interne </h2>
    <p>Se adauga folosind tag-ul <strong>'style' </strong>in elementul head</p>

    <h2 class="titlu-h2"> Stiluri externe</h2>
    <p>Se adauga folosind tag-ul <strong>link</strong> si se specifica la href numele fisierului .css</p>

    <h2 class="titlu-h2">Stiluri inline</h2>
    <p>Stilurile inline nu sunt recomandate, nu le vom folosi. Totusi le veti vedea uneori pe Internet in exemple de
        mici dimensiuni. Sunt adaugate intr-un element folosind atributul <strong>style</strong></p>
</body>

</html>