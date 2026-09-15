# ACUM — prezentări interactive live

Prototip funcțional de aplicație românească pentru prezentări interactive live, inspirată de categoria Mentimeter / Slido, dar cu identitate vizuală proprie.

## Include
- Landing Page
- Dashboard Presenter
- Presentation Editor cu 3 coloane
- Poll, Word Cloud, Quiz și Q&A
- Presentation Screen 16:9
- Participant App mobile-first cu cod 7291
- Results Dashboard
- Workspace Settings
- stări live, votare închisă și autosave local
- sincronizare între tab-uri prin BroadcastChannel + localStorage

## Test rapid
1. Deschide `index.html`.
2. Intră în Dashboard și pornește prezentarea.
3. Într-un al doilea tab deschide ruta `#/participant`.
4. Introdu codul `7291`.
5. Votează / trimite cuvinte / întrebări și urmărește actualizarea live.

## Notă tehnică
Acesta este un MVP front-end fără build step. Pentru producție, persistența locală trebuie înlocuită cu backend realtime (de exemplu Supabase/Firebase/WebSocket), autentificare și workspaces multi-user.
