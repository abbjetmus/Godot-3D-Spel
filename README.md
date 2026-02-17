# Guide till Godot för 3D-spelutveckling

Github Classroom länk: <a href="https://classroom.github.com/a/HTVFY2pk">https://classroom.github.com/a/HTVFY2pk</a>

## Introduktion
Godot är en kraftfull och öppen källkod spelmotor som stöder både 2D och 3D-spelutveckling. Den erbjuder en flexibel nodbaserad arkitektur, inbyggt GDScript-programmeringsspråk och ett lättanvänt gränssnitt.

## Installation
1. Ladda ner Godot från [Godots officiella webbplats](https://godotengine.org/).
2. Installera och öppna programmet.
3. Skapa ett nytt projekt och välj en katalog för ditt spel.

## Grundläggande koncept
### Noder och Scener
- **Allt i Godot bygger på noder.**
- En scen kan innehålla flera noder.
- Exempel på vanliga noder:
  - `Node3D` - Grundläggande nod för 3D-spel
  - `Camera3D` - Hanterar kameran i 3D

### GDScript
- Ett lättviktigt, Python-liknande skriptspråk som används för att programmera logik.
- Exempel på ett enkelt skript:

```gdscript
extends Node3D

func _ready():
    print("Spelet startar!")
```

## 3D-Spelutveckling
### Skapa en spelkaraktär i 3D
1. Lägg till en `Node3D` som root-nod.
2. Lägg till en `MeshInstance3D` och välj en 3D-modell.
3. Lägg till en `CollisionShape3D` för kollisioner.
4. Lägg till en `KinematicBody3D` för rörelse.

### Enkel rörelse i 3D
```gdscript
extends KinematicBody3D

var speed = 5
var velocity = Vector3.ZERO

func _process(delta):
    velocity = Vector3.ZERO
    if Input.is_action_pressed("ui_right"):
        velocity.x += speed
    if Input.is_action_pressed("ui_left"):
        velocity.x -= speed
    move_and_slide(velocity)
```

## Spel resurser i form och extensions och bilder m.m.
Godot har egen sida för resurser (assets) där man kan hitta lämpliga bilder för spelplan och liknande.


<a href="https://godotengine.org/asset-library/asset">https://godotengine.org/asset-library/asset</a>


Här tex asset för hexagonal gräs karta.


<img src="https://docs.godotengine.org/en/stable/_images/assetlib_asset.webp"> 

## Viktiga aspekter
- **Signals och Events:** Använd `signals` för att hantera händelser.
- **Scenhantering:** Återanvänd scener för bättre struktur.
- **Fysikmotor:** Godot har inbyggd fysik för både 2D och 3D.
- **Export:** Exportera spel till Windows, Linux, macOS, Android och HTML5.

## Slutsats
Godot är en kraftfull och flexibel spelmotor som erbjuder verktyg för både 2D och 3D-utveckling. Genom att förstå nodbaserad arkitektur, GDScript och fysikmotorn kan du snabbt skapa spel av hög kvalitet.

## Tutorial: Första 2D Spel
Gå igenom tutorialen ditt första 2D spel: [https://docs.godotengine.org/en/stable/getting_started/first_2d_game/index.html](https://docs.godotengine.org/en/stable/getting_started/first_2d_game/index.html)

För att först få en bekantskap med Godot. Därefter kan ni hoppa på 3D Spel.

Föredrar man video-tutorials är den här serien fantastisk för 2D spel med Godot:

[https://www.youtube.com/playlist?list=PL4cUxeGkcC9iHCXBpxbdsOByZ55Ez4bgF](https://www.youtube.com/playlist?list=PL4cUxeGkcC9iHCXBpxbdsOByZ55Ez4bgF)

## Tutorial: Första 3D Spel
Gå igenom tutorialen ditt första 3D spel: [https://docs.godotengine.org/en/stable/getting_started/first_3d_game/index.html](https://docs.godotengine.org/en/stable/getting_started/first_3d_game/index.html)

Föredrar man video-tutorials är den här serien fantastisk för 3D spel med Godot:

<a href="https://www.youtube.com/playlist?list=PLda3VoSoc_TTp8Ng3C57spnNkOw3Hm_35">https://www.youtube.com/playlist?list=PLda3VoSoc_TTp8Ng3C57spnNkOw3Hm_35</a>

## Projekt Beskrivning
Projektet utförs individuellt och går ut på att ni ska utveckla ett valfritt 3D-spel i Godot.
Tiden är 11 mars - 3 april och innefattar 24 timmar. 
Redovisningsformen är mässa där man får testa varandras spel.

## Kravuppfyllelse på 3D spelet
Ni får återskapa ett känt spel om ni vill, men inte hämta klar kod från nätet.
Eller så väljer ni hitta på ett eget spel. Efter ni har gått igenom tutorialen kan man börja planera spelet steg 0.
### 0. Planering
Planera spelet, skapa ett dokument med beskrivning och skiss hur ni vill att spelet ska fungera och se ut. 
Få godkännande från läraren. Resten är saker som spelet måste uppfylla.
### 1. Grundläggande spelmekanik
Spelarens rörelse – Använd WASD/tangenter eller en joystick för att styra en 3D-karaktär.
Kollisionsdetektion – Se till att spelaren och objekt inte går genom varandra.
Kamera – En enkel tredjepersons- eller förstapersonskamera som följer spelaren.
Grundläggande mål – Exempelvis att nå en specifik plats, samla föremål eller undvika hinder.
Vinst-/förlustvillkor – Enkla regler för att avgöra om spelaren vinner eller förlorar.
### 2. Enkel 3D-grafik
3D-modeller – Grundläggande objekt för spelaren, miljön och fiender (kan vara enkla former som kuber/sfärer).
Grundläggande texturer – Färger eller enkla bilder på modeller för att skapa variation.
Minimala animationer – Enkel gång- eller hopprörelse om spelet har en karaktär.
### 3. Grundläggande användargränssnitt (UI)
Startskärm – En enkel meny med en "Starta"-knapp.
Game over-skärm – Ett meddelande när spelaren vinner eller förlorar.
HUD (valfritt) – Exempelvis hälsobar, poäng eller en timer.
### 4. Enkla ljudeffekter och musik
Ljud för rörelse, hopp, kollisioner eller insamling.
Bakgrundsmusik – Enkel bakgrundslåt eller ljudeffekter för atmosfär.
### 5. Enkel AI eller spelelement
Grundläggande fienderörelse – Fiender kan patrullera eller jaga spelaren.
Samlarföremål – Mynt, kristaller eller andra objekt som ger poäng.
Enkel fysik – Gravitation, hopp eller fall när spelaren går av en plattform.
### 6. Scen- och nivåhantering
Enkla scenövergångar – Flytta mellan olika nivåer eller starta om spelet.
Respawn eller återställning – Om spelaren faller av kartan eller dör, ska spelet kunna återställa scenen.
### 7. Byggas och distribueras
Byggas och distribueras som en .exe fil för andra att kunna testa spelet.

Här är en länk som beskriver hur man genererar en exekverbar fil för Windows:
<a href="http://docs.godotengine.org/en/latest/tutorials/export/exporting_for_windows.html">http://docs.godotengine.org/en/latest/tutorials/export/exporting_for_windows.html</a>

# 🎮 Git LFS för Godot-projekt i GitHub Classroom

Eftersom studenterna arbetar i sina **egna repositories skapade via GitHub Classroom** (som i grunden är vanliga GitHub-repositories) måste **Git LFS aktiveras i varje repository individuellt**.

Nedan är den säkraste och tydligaste konfigurationen specifikt för Godot‑projekt.

---

# ✅ Steg 1 — Installera Git LFS (Varje student gör detta en gång)

Kör följande kommando:

```bash
git lfs install
```

Detta behöver bara göras en gång per dator.

---

# ✅ Steg 2 — Klona sitt Classroom‑repository

```bash
git clone https://github.com/ORG/assignment-repo.git
cd assignment-repo
```

---

# ✅ Steg 3 — Spåra stora Godot‑filtyper

I Godot‑projekt bör man vanligtvis spåra följande filtyper med LFS:

```bash
git lfs track "*.png"
git lfs track "*.jpg"
git lfs track "*.wav"
git lfs track "*.mp3"
git lfs track "*.ogg"
git lfs track "*.import"
git lfs track "*.glb"
git lfs track "*.gltf"
git lfs track "*.ttf"
git lfs track "*.mp4"
```

⚠️ Viktigt:
Spåra **inte** följande filer med LFS:

* `.tscn`
* `.gd`
* `.tres`
* `.project`

Dessa är textfiler och ska versionshanteras med vanlig Git för att möjliggöra korrekt merge‑hantering.

---

# ✅ Steg 4 — Commita spårningsreglerna

```bash
git add .gitattributes
git commit -m "Enable Git LFS for large Godot assets"
git push
```

Detta säkerställer att LFS‑inställningarna sparas i repositoryt.

---

# ✅ Steg 5 — Lägg till stora filer som vanligt

Efter detta kan studenter arbeta normalt:

```bash
git add .
git commit -m "Add game assets"
git push
```

Git LFS hanterar automatiskt uppladdningen av de stora filerna.

---

# 🏫 Viktiga överväganden i undervisningsmiljö

## 🔹 Alternativ A (Rekommenderas): Läraren aktiverar LFS i mall‑repositoryt

Detta är den renaste lösningen:

1. Läraren aktiverar Git LFS i mall‑repositoryt
2. Lägger till `.gitattributes`
3. Skapar därefter Classroom‑uppgiften

Då får alla studenters repositories rätt konfiguration från början.

Fördelar:

* Studenter glömmer inte aktivera LFS
* Inga 100MB‑fel vid push
* Ingen komplicerad historik‑omskrivning behövs

---

## 🔹 Alternativ B: Studenter aktiverar individuellt

Om repositories redan är skapade:

* Varje student kör LFS‑kommandona i sitt repository
* Commitar `.gitattributes`

Det fungerar bra — men måste göras **innan** stora filer läggs till.

---

# 🚨 Mycket viktigt: 100MB‑gränsen

GitHub blockerar filer över 100MB om de inte spåras med LFS.

Om en student:

* Commitar filen först
* Aktiverar LFS efteråt

Kommer push att misslyckas.

Lösning:

```bash
git lfs migrate import --include="*.png,*.wav,*.glb"
```

Detta skriver om historiken. För individuella student‑repositories är det oftast okej, men det kan vara förvirrande för nybörjare.

---

# 💰 Lagrings- och bandbreddsvarning (extra viktigt för spelprojekt)

Spelresurser kan snabbt förbruka mycket lagring.

GitHub har begränsningar för:

* LFS‑lagring
* LFS‑bandbredd

Om till exempel:

* 50 studenter
* Varje repository innehåller 1 GB assets
* Alla klonar ofta

Kan organisationen överskrida sin kvot.

---

# 🔄 Säkrare alternativ vid mycket stora projekt

Vid riktigt stora tillgångar kan man istället:

* Lagra stora ljudpaket externt (t.ex. molnlagring)
* Tillhandahålla nedladdningsskript
* Använda GitHub Releases för stora filer istället för själva repositoryt

---

# 🎯 Rekommendation för er situation

Eftersom detta gäller Godot‑projekt rekommenderas följande:

## ✔ Spåra med Git LFS

* Ljud
* Texturer
* 3D‑modeller
* Video
* Typsnitt

## ❌ Spåra inte med Git LFS

* Scener (`.tscn`)
* Script (`.gd`)
* Projektkonfiguration

---

# 📄 Jag kan även hjälpa med

* En färdig `.gitattributes`‑fil optimerad för Godot
* En kort instruktionstext att dela med studenter
* En enkel och säker klassrumspolicy för hantering av stora assets

Ange gärna:

* Ungefärlig storlek på assets per student
* Antal studenter
* Om projekten är individuella eller gruppbaserade

Så kan jag föreslå den säkraste strukturen för att undvika att överskrida lagrings‑ eller bandbreddsgränser.

