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

git lfs (Large File Storage) är ett tillägg till Git som gör det möjligt att hantera stora filer effektivt. För Godot-projekt som ofta innehåller stora tillgångar (assets) som texturer, ljud och 3D-modeller. Det är viktigt att använda Git LFS för att undvika problem med GitHub's 100MB-filgräns.


# ✅ Steg 1 — Installera Git LFS
Kör följande kommando:

```bash
git lfs install
```
# ✅ Steg 2 — Clone repositoryt
Byt ut `<repository-url>` mot URL:en för ditt GitHub Classroom repository:
```bash
git clone <repository-url>
```

# ✅ Steg 3 — Skapa en `.gitattributes`-fil

En `.gitattributes`-fil i projektets rot definierar vilka filtyper som ska spåras med LFS. Exempel:

```gitattributes
# -----------------------------------------------------------------------------
# Godot + Git LFS
# -----------------------------------------------------------------------------

# Large binary assets (store in LFS)
*.png  filter=lfs diff=lfs merge=lfs -text
*.jpg  filter=lfs diff=lfs merge=lfs -text
*.jpeg filter=lfs diff=lfs merge=lfs -text
*.webp filter=lfs diff=lfs merge=lfs -text
*.tga  filter=lfs diff=lfs merge=lfs -text
*.bmp  filter=lfs diff=lfs merge=lfs -text
*.hdr  filter=lfs diff=lfs merge=lfs -text
*.exr  filter=lfs diff=lfs merge=lfs -text

*.wav  filter=lfs diff=lfs merge=lfs -text
*.ogg  filter=lfs diff=lfs merge=lfs -text
*.mp3  filter=lfs diff=lfs merge=lfs -text
*.flac filter=lfs diff=lfs merge=lfs -text

*.mp4  filter=lfs diff=lfs merge=lfs -text
*.mov  filter=lfs diff=lfs merge=lfs -text
*.webm filter=lfs diff=lfs merge=lfs -text

*.glb  filter=lfs diff=lfs merge=lfs -text
*.gltf filter=lfs diff=lfs merge=lfs -text
*.fbx  filter=lfs diff=lfs merge=lfs -text
*.blend filter=lfs diff=lfs merge=lfs -text
*.obj  filter=lfs diff=lfs merge=lfs -text
*.dae  filter=lfs diff=lfs merge=lfs -text

*.ttf  filter=lfs diff=lfs merge=lfs -text
*.otf  filter=lfs diff=lfs merge=lfs -text

*.res  filter=lfs diff=lfs merge=lfs -text

# Godot import artifacts can be big
*.ctex filter=lfs diff=lfs merge=lfs -text
*.stex filter=lfs diff=lfs merge=lfs -text
*.tex  filter=lfs diff=lfs merge=lfs -text

# Godot-specific: keep these as text (normal version handeling)
*.gd     text eol=lf
*.gdshader text eol=lf
*.tscn   text eol=lf
*.tres   text eol=lf
*.godot  text eol=lf
project.godot text eol=lf

# Common text formats
*.json text eol=lf
*.yml  text eol=lf
*.yaml text eol=lf
*.md   text eol=lf
*.txt  text eol=lf
```

# ✅ Steg 4 — Commita spårningsreglerna

```bash
git add .gitattributes
```

## OBS, om detta görs efter att stora filer redan har commitats, måste man migrera dem till LFS:

## ⚠️⚠️⚠️ Detta kommer skriva över git historiken, det rekommenderas att göra en backup av repository innan

På windows kan följande kommando användas OBS: PowerShell:
```ps1
$include = (Get-Content .gitattributes |
  Where-Object { $_ -notmatch '^\s*#' -and $_ -match 'filter=lfs' } |
  ForEach-Object { ($_ -split '\s+')[0] }
) -join ','

"Include: $include"
git lfs migrate import --everything --include="$include"
```

Om detta görs efter en push behöver man även pusha igen med `--force`:

```bash
git push --force
```



# ✅ Steg 5 — Lägg till stora filer som vanligt

Efter det kan man lägga till alla filer som vanligt, och de som matchar reglerna i `.gitattributes` kommer att spåras av LFS:

```bash
git add .
git commit -m "Add game assets"
git push
```