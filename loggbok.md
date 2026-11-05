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
En missuppfattning gjorde att min påbörjade loginlösning överlappade en gruppmedlems arbete. Min PR stängdes och jag byggde istället välkomstsidan vidare på den befintliga implementationen.

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

## Sprint 5 – vecka 43, 19–23 oktober 2026

### Vad jag arbetade med
Vi delade upp gatewayuppgiften i mindre Trello-kort. Jag ansvarade för controllerklassen, forwardPost och POST-endpoints för produkter och ordrar. Jag kopplade dessa till vår gemensamma GatewayProxyService, så att body, Authorization och Content-Type vidarebefordras till rätt tjänst. Ändringarna committades den 20 oktober. Den 22 oktober committade jag även CSRF-konfigurationen för gatewayen. Projektet kompilerade och det befintliga starttestet gick igenom.

### Eventuella problem och hur jag löste dem
Maven Wrapper fungerade inte vid import av det klonade projektet. Jag bytte till IntelliJ:s bundled Maven 3 och kunde läsa in beroendena. Jag undersökte också CSRF och följde anropen genom tjänsterna. Det gav mig en tydligare förståelse för skillnaden mellan gatewayens vidarebefordring och backendtjänsternas JWT-verifiering.

När POST-anrop blockerades behövde vi undersöka var i flödet stoppet uppstod. Jag följde hur säkerhetsinställningarna påverkade anropen och genomförde ändringen i gatewayen. Erfarenheten gjorde mig mer uppmärksam på att varje tjänst har sin egen säkerhetskonfiguration och att ett fungerande anrop till en tjänst inte automatiskt innebär att hela kedjan fungerar.

### Samarbete och agilt arbete
Uppdelningen gjorde att vi kunde arbeta parallellt, men våra metoder behövde passa ihop i den gemensamma serviceklassen. Jag återanvände gruppens send-metod och anpassade mina delar till den gemensamma lösningen. Uppdelningen krävde därför både individuellt ansvar och avstämning kring hur delarna skulle kopplas samman.

Jag granskade också en gruppmedlems PR. Där upptäcktes ofullständiga konfigurationsuttryck som rättades före merge. Det visade hur kodgranskning kan fånga problem som ett grönt byggresultat inte alltid upptäcker. Granskningen blev ett sätt för oss att gemensamt ta ansvar för kvaliteten även i delar som någon annan hade skrivit.

Under fredagens retro deltog jag i diskussionen om tidsbrist och stress inför det återstående arbetet. Vi tog med oss detta till nästa sprint för att följa upp planeringen och hur mycket vi hann färdigställa. För mig blev det tydligare hur retrospektivet kan användas för att påverka nästa arbetsperiod genom att identifiera sådant som behöver förändras.

## Sprint 6 – vecka 44, 26–30 oktober 2026

### Vad jag arbetade med
Jag undersökte hur Vitest, React Testing Library och MSW används tillsammans och dokumenterade skillnaden mellan komponenttest, frontend-integrationstest och end-to-end-test (FE-38). Därefter konfigurerade jag MSW med mockade svar för /auth/me och /products, så att API-svaren kan styras utan att backend körs (FE-39). Jag kompletterade även med tester för lyckad och misslyckad inloggning. Detta committades den 29 oktober.

Den 30 oktober committade jag integrationstester för produkthämtningen (FE-40). Testerna renderar App och kontrollerar att en inloggad användare ser produkterna, att ett felmeddelande visas när hämtningen misslyckas och att produkter inte visas när den mockade användarsessionen saknas. Genom att täcka både lyckade anrop och felsituationer kunde jag verifiera hur sidan beter sig under olika förutsättningar.

Jag skrev också Javadoc för relevanta klasser och publika metoder i order-service (FE-46) samt en README med tjänstens ansvar, tekniker, databas, miljövariabler och startinstruktioner (FE-43). Dokumentationen committades den 29 oktober. Arbetet krävde att jag följde tjänstens befintliga kod och konfiguration för att beskrivningarna skulle stämma med hur den faktiskt fungerade.

Jag undersökte även Stripe med koppling till betalningskorten FE-14, FE-19 och FE-31 och dokumenterade vad integrationen kräver samt vad jag genomförde. Jag skapade en separat payment-service för testbetalningar och kopplade betalningsflödet till beställningar och lagerreservationer. Arbetet fortsatte i egna projektkopior efter sprintens slut. Efter avstämning med läraren redovisar jag även denna individuella vidareutveckling här.

I projektkopiorna lade jag dessutom till kontoregistrering, kontoborttagning och en förenklad lösenordsåterställning för demoappen. Jag förbättrade produktkortens layout och återkopplingen när produkter läggs i varukorgen samt skapade gemensamt utformade statussidor för backendtjänsterna. Jag anpassade CI och Docker-publiceringen till mina repositories, driftsatte tjänsterna på Render och uppdaterade dokumentationen.

### Eventuella problem och hur jag löste dem
Frontendens befintliga inloggning använde sessionsdata, medan uppgiften även krävde mockning av /auth/me. Jag anpassade testmiljön så att det mockade användarsvaret gav produktsidan den autentiserade kontext som den behöver. Det gjorde att produkthämtningen kunde testas utan att ändra den befintliga inloggningslösningen. Jag fick en tydligare förståelse för hur frontendens beteende kan testas separat från backendens autentisering och vilka delar som fortfarande behöver verifieras i hela systemet.

Vid betalningstestning genomfördes betalningen i Stripe, men beställningen blev kvar som väntande. Jag följde händelsen i Stripe och upptäckte att webhooken skickades till fel adress. Efter korrigering och omsändning av händelsen uppdaterades beställningen. Felsökningen visade att jag behövde följa bekräftelsen hela vägen från Stripe till beställningen för att avgöra var flödet stannade.

Jag kompletterade även flödet med möjlighet att avbryta en väntande betalning och frigöra reserverat lager. Det gjorde hanteringen tydligare när kunden lämnade betalningen utan att slutföra den. Arbetet gav mig bättre förståelse för hur betalningsstatus, beställning och lager behöver hållas konsekventa mellan tjänsterna.

Vid driftsättningen felsökte jag även miljövariabler och frontendens inställning för tillåtna ursprung. Jag testade därefter hela betalningsflödet i den driftsatta miljön. Det gjorde mig mer uppmärksam på att lokal testning behöver kompletteras med kontroll av den miljö där applikationen ska användas, eftersom adresser och konfiguration skiljer sig åt.

### Samarbete och agilt arbete
Jag deltog i sprintplaneringen, våra daily scrums samt fredagens review och retro. Vid planeringen använde vi planning poker där vi först gjorde egna uppskattningar. När bedömningarna skilde sig åt diskuterade vi vad som gjorde uppgiften större eller mindre. Det hjälpte oss att upptäcka olika uppfattningar om arbetets omfattning och beroenden innan vi fördelade uppgifterna. Jag kunde därmed jämföra min egen bedömning med gruppens och få en tydligare bild av vad uppgifterna krävde.

Vi följde också upp föregående retros diskussion om tidsbrist. Under sprinten färdigställde vi de planerade uppgifterna och kunde ta in ytterligare arbete. På fredagens retro gick vi igenom resultatet och kunde konstatera att grupprojektets återstående uppgifter var klara. Det gav oss möjlighet att jämföra det faktiska utfallet med vår planering och följa upp den oro som hade lyfts veckan innan.

Vi fördelade dokumentationsarbetet inom gruppen, och jag ansvarade för order-servicens Javadoc och README. När dokumentationen var färdig jämförde jag den med övriga tjänsters för att bekräfta att vi hade en gemensam struktur. På så sätt kombinerade vi individuellt ansvar med en gemensam kontroll av slutresultatet.

Vid granskningen av min PR diskuterade vi om testadressen behövde innehålla port 5173. Jag förklarade att testerna använder MSW och inte kräver en körande utvecklingsserver. Efter avstämningen godkändes och mergades PR:n. Diskussionen gav oss en gemensam förståelse för testernas upplägg och omfattning. För mig innebar granskningen också att jag behövde kunna motivera lösningen och förklara vad testerna faktiskt verifierar.

Betalningsfunktionen och den övriga individuella vidareutvecklingen genomförde jag i egna projektkopior. Där kunde jag själv följa ändringar genom frontend, gateway och backend och ta ansvar för att hela flödet fungerade. Det gav mig möjlighet att tillämpa erfarenheterna från grupparbetet och fatta egna beslut om implementation, testning och driftsättning.

Den 5 november stämde jag av arbetet med läraren, som föreslog att betalningsundersökningen och implementationen skulle ingå i sprint 6.
