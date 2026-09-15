# ACUM — prezentări interactive live

Aplicație web pentru prezentări interactive live, cu acces al participanților printr-un singur link web unic al sesiunii.

## Flux
1. Prezentatorul deschide aplicația și pornește o sesiune live.
2. ACUM generează automat o adresă web unică de participare.
3. Prezentatorul copiază și trimite linkul participanților.
4. Participanții deschid linkul direct pe telefon, tabletă sau laptop — fără cod și fără QR.
5. Răspunsurile se transmit live către ecranul prezentatorului.

## Include
- Landing Page
- Presenter Dashboard
- editor în 3 coloane
- Poll
- Word Cloud
- Quiz
- Q&A
- Presentation Screen 16:9
- Participant App mobile-first
- Results Dashboard
- Workspace Settings
- votare deschisă / închisă
- reconectare automată
- protecție locală împotriva votului dublu pe același poll

## Realtime
MVP-ul folosește MQTT over WebSocket prin brokerul public HiveMQ pentru sincronizare între dispozitive diferite. Nu mai depinde de `BroadcastChannel` sau de faptul că participantul și prezentatorul sunt în același browser.

## Test rapid
1. Publică directorul `acum-live/` prin GitHub Pages sau alt hosting static HTTPS.
2. Deschide aplicația ca prezentator.
3. Apasă **Pornește live**.
4. Copiază adresa web generată în panoul **Participă live**.
5. Deschide acea adresă pe alt telefon sau într-o fereastră privată.
6. Votează. Rezultatele trebuie să apară în timp real pe ecranul prezentatorului.

## Important pentru producție
Brokerul public este potrivit pentru prototip și demonstrații, nu pentru date sensibile sau utilizare enterprise. Pentru producție recomand un backend propriu (Supabase Realtime, Firebase sau WebSocket server), autentificare, ACL-uri și persistență server-side.
