# TaskBoard TV

Board Kanban de echipă, gândit pentru un ecran TV/monitor lăsat deschis permanent, cu editare live de pe telefon sau laptop. Este o singură pagină HTML de sine stătătoare (fără build, fără dependențe de server) — `index.html` și `taskboard-tv.html` sunt identice; păstrează-le sincronizate dacă editezi manual una dintre ele.

## Ce conține

- Coloane Kanban (De făcut / În lucru / Gata) cu filtrare pe responsabil
- Calendar cu perioadele de concediu evidențiate
- Panou de anunțuri
- Bandă defilantă cu concediile echipei + o bandă opțională cu știri (Google News prin `rss2json.com`)
- Gestionare responsabili (echipă) pentru autocompletare pe task-uri și concedii

## Persistență

Când pagina rulează în interiorul Claude (`window.claude.use("artifact")`), editările se publică live pentru toți cei care au board-ul deschis. Când rulează în afara acelui mediu (de exemplu hostată static, ca pe `pplx.app`), editările sunt salvate automat în `localStorage`-ul browser-ului respectiv, astfel încât să reziste la refresh; tab-urile deschise pe același browser se sincronizează între ele automat.

## Stabilitate

- Un singur render/eveniment defect nu mai blochează tot board-ul (erorile sunt prinse și logate în consolă, nu lasă ecranul înghețat).
- Refresh-ul automat la fiecare 30 de minute sare peste re-randare cât timp cineva scrie efectiv într-un câmp, ca să nu piardă un draft netrimis.
- Banda de știri ține minte ultimele titluri primite cu succes și le arată în continuare dacă proxy-ul extern e temporar indisponibil, în loc să afișeze mereu "indisponibil".
