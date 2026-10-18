# Individuell loggbok – Microservices Webshop
Namn: Yunus Uludag

## Vårt arbetssätt
Läraren är produktägare och tillhandahåller produktbackloggen. På måndagar går vi igenom uppgifterna, uppskattar deras storlek och svårighetsgrad och noterar poäng. Därefter lägger vi in de valda uppgifterna i Trello och fördelar ansvaret gemensamt. Vi har korta daily scrums för att stämma av läget och synliggöra hinder. På fredagens sprint review visar vi resultatet för läraren, jämför med sprintmålet och tar emot feedback. I separata retrospektiv följer vi upp gruppens arbetssätt.

## Sprint 1 – vecka 39, 21–25 september 2026

### Vad jag arbetade med
Jag verifierade att jag kunde köra frontend lokalt (FE-04). Gruppen etablerade repository, CI och branchskydd. Jag gjorde inga egna frontendcommits under sprinten.

### Eventuella problem och hur jag löste dem
Inga problem uppstod under denna sprint.

### Samarbete och agilt arbete
Jag deltog i backloggenomgång, estimering och gemensam ansvarsfördelning. Planeringen och våra daily scrums gav mig en tydligare uppfattning om hur agilt arbete fungerar i praktiken och hur mitt arbete hänger ihop med gruppens.

## Sprint 2 – vecka 40, 28 september–2 oktober 2026

### Vad jag arbetade med
Jag skapade välkomstsidan med användarnamn och roller (FE-10), committad den 2 oktober. Jag byggde även produktvisning från backend med felhantering, hantering av tom produktlista och USD-priser (FE-11). Detta committades lördagen den 3 oktober, efter ordinarie sprintslut. Arbetet gav mig mer praktisk erfarenhet av sessionsdata och datahämtning med React Router.

### Eventuella problem och hur jag löste dem
En missuppfattning gjorde att min påbörjade loginlösning överlappade Martins arbete. Min PR stängdes och jag byggde istället välkomstsidan vidare på hans implementation.

### Samarbete och agilt arbete
Jag deltog i sprintplaneringen och löpande avstämningar. Genom att fortsätta på gruppens gemensamma loginlösning kunde jag fokusera på välkomstsidan istället för att behålla parallella implementationer.

## Sprint 3 – vecka 41, 5–9 oktober 2026

### Vad jag arbetade med
Jag skapade adminsidans produktöversikt (FE-17), med produkttabell, hantering av tom lista och återanvändbar rollkontroll. Ändringarna committades den 8 oktober.

### Eventuella problem och hur jag löste dem
Efter feedback på min PR förenklade jag behörighetskontrollen. Jag återanvände befintlig autentisering och samlade rollkontrollen i gemensam middleware, så att fler adminsidor kan använda den utan duplicerad kod. Det gjorde mig mer uppmärksam på projektets befintliga struktur.

### Samarbete och agilt arbete
Jag deltog i planering, daily scrums, sprint review och retro. Kodgranskningen bidrog konkret till en mer återanvändbar lösning och visade värdet av att låta andra granska arbetet före merge.

## Sprint 4 – vecka 42, 12–16 oktober 2026

### Vad jag arbetade med
Jag skapade adminformuläret för nya produkter (FE-20), inklusive category och imageUrl, validering, backendanrop med JWT och bekräftelse efter skapande. Detta committades den 13–14 oktober. Den 15 oktober committade jag kategorifiltrering på produkt- och adminsidan samt styling. Jag verifierade också lokalt mejlutskick, vilket alla gruppmedlemmar testade individuellt.

### Eventuella problem och hur jag löste dem
Jag felsökte saknade miljövariabler och databasproblem efter backenduppdateringen. Gamla testprodukter säkerhetskopierades och återskapades med de nya fälten. Det tydliggjorde att uppdaterad kod även kan kräva förändringar i konfiguration och befintlig data. Vid mergekonflikter kombinerade jag gruppens funktioner med min styling. TypeScript-kontroll, build och befintliga tester kompletterades med manuell testning.

### Samarbete och agilt arbete
Jag deltog i planeringen och avstämningarna samt granskade kamraternas PR:er. Jag uppmärksammade bland annat null-hantering i sökningen, som rättades. Det visade att grön CI inte ersätter granskning av olika datafall. Jag upplever att våra reviews och retros har förbättrat kommunikationen och effektiviteten genom att vi följer upp både resultatet och arbetssättet.
