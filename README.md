# README — Mirror av tankomilund.se (tre funktionslägen)

## Innehåll
- [Översikt](#översikt)
- [Mappstruktur](#mappstruktur)
- [Vad som ändrats](#vad-som-ändrats)
- [Användning](#användning)
  - [✔️ Fungerar lokalt — öppna `index.html` direkt](#️-fungerar-lokalt--öppna-indexhtml-direkt)
  - [🌐 Kan servas lokalt — kör via en lokal webbserver](#-kan-servas-lokalt--kör-via-en-lokal-webbserver)
  - [📦 Rå källa — orörd originalversion](#-rå-källa--orörd-originalversion)


---

## Översikt
Det här projektet är en **lokal spegling av tankomilund.se**, uppdelad i tre olika varianter för olika behov:

1. **Fungerar lokalt** — fungerar helt utan server, allt pekar på lokala filer.  
2. **Kan servas lokalt** — för körning via en enkel webbserver, behåller animationer och originalskript.  
3. **Rå källa** — exakt rå kopia av den speglade källan, utan några ändringar.

---

## Mappstruktur
```
/Fungerar lokalt/        # Ren, omskriven version för filsystem (utan Webflow)
  index.html
  /pendla/*.html
  /cdn.../

/Kan servas lokalt/      # Komplett version som kräver server
  index.html
  /pendla/*.html

/Rå källa/               # Orörd spegling (true original scrape)
  index.html
  /pendla/*.html
  + all originalskript (inkl. webflow.js, cookiebot, analytics)
```

---

## Vad som ändrats
### Fungerar lokalt
- Webflow, jQuery och cookie-scripts borttagna.  
- Länkar ändrade till `pendla/<slug>.html`.  
- `openSite()` skriptet modifierat för att länka lokalt.  
- Menyn omskriven i ren HTML/CSS.

### Kan servas lokalt
- Behåller Webflow-skript, animeringar och JS-logik.  
- Kräver att startas via en lokal server.  
- Samma HTML-struktur som originalet, men referenser uppdaterade till lokala resurser.

### Rå källa
- 1:1-kopia av originalet.  
- Inga omskrivna sökvägar.  
- Innehåller **originalscriptet**
- Laddar fortfarande externa resurser direkt från `https://cdn.prod.website-files.com/…`

---

## Användning

### ✔️ Fungerar lokalt — öppna `index.html` direkt
1. Gå till mappen **Fungerar lokalt**.  
2. Dubbelklicka på `index.html`.  
3. Navigering och ”Ge mig resetips” fungerar helt utan server.  

### 🌐 Kan servas lokalt — kör via en lokal webbserver
1. Öppna mappen **Kan servas lokalt**.  
2. Kör någon av följande kommandon:

   **Python**
   ```bash
   cd "Kan servas lokalt"
   python -m http.server 8000
   ```
   **Node.js**
   ```bash
   cd "Kan servas lokalt"
   npx http-server -p 8000
   ```
   eller använd *Live Server* i VS Code.

3. Gå till `http://localhost:8000`.

### 📦 Rå källa — orörd originalversion
Denna mapp innehåller **den rena, speglade källan**.  
Alla länkar, script och CDN-referenser pekar fortfarande på `www.tankomilund.se`.

- För utveckling eller jämförelse — inte tänkt att köras lokalt utan nätverk.  
- Öppna `index.html` för att se exakt hur speglingen såg ut före omskrivning.  
- Scriptet `openSite()` länkar till den riktiga sidan på internet.

---
