# Git Workshop

Dette repoet inneholder tre velkjente sanger, hver lagret i sin txt-fil. Dere skal nå sammarbeide to og to for å fullføre sangene i utvikler-fashion :)

Gå sammen to og to og start på oppgavene under. Gjør gjerne oppgavene sammen, selv om de refereres til hver av dere. Og ikke nøl med å spørre om hjelp hvis dere står fast!

## Oppgave 1 - Kopier (fork) GitHub repositoriet

**Person 1:**

- Sjekk at du er logget inn i GitHub og trykk på `fork` øverst i høyre hjørne.
- På siden som kommer opp, skriv inn et navn for repoet, for eksempel `hybrida-bedpres`
- Trykk på `Create fork`

Nå har person 1 laget en kopi/fork av repoet i sin GitHub. Neste steg er at Person 1 gir sin kjære samarbeidspartner tilgang til repoet. Dette gjøres ved å:

- Gå til `Settings` i menyen i repoet på GitHub
- Trykk på `Collaborators`
- Under `Manage Access`, trykk på `Add People`
- Skriv inn brukernavnet på Person 2 og trykk `Add to this repository`

Nå er alt klart for at dere kan bruke Git til effektivt samarbeid.

## Oppgave 2 - Clone repositoret lokalt

**Både Person 1 og Person 2:**

- Åpne terminalen på hver deres maskin og naviger til Desktop.
- Clone repoet lokalt på hver deres maksin ved å kjøre følgende kommando i terminalen (bytt ut <person_1_username> med GitHub-brukernavnet til Person 1 og <repo_name> med navnet på repoet dere velgte i Oppgave 1):

```
git clone https://github.com/<person_1_username>/<repo_name>.git
```

## Oppgave 3 - Branching

Når flere samarbeider på et prosjekt med Git er det vanlig å lage hver sin `branch` hvor man gjør endringer på en kopi av koden. Dette som en trygghet på at man kan gjøre feil uten at det påvirker andre på prosjektet.

Dere skal nå lage hver deres branch og fullføre sangtekstene nu klinger og ja vi elsker. For å sjekke hvilke branches som finnes kjør følgende kommando i terminalen:

```
git branch
```

Skriv `q` for å gå ut at branch-visningen.

**Person 2:**

Person 2 skal endre nu_klinger.txt, men først må det lages en ny branch hvor endringene kan gjøres. Lag en ny branch kalt `nu_klinger` ved å kjøre følgende kommando i terminalen:

```
git branch nu_klinger
```

Bytt til den nye branchen ved å kjøre følgende kommando i terminalen:

```
git switch nu_klinger
```

Nå kan Person 2 åpne filen nu-klinger.txt og lime inn refrenget (vist under) i bunn av filen.

> Studenter i den gamle stad, ta vare på byens ry! (klapp x2)
> Husk på at jenter, øl og dram var kjempenes meny.
> Og faller I alle mann alle, skal det gjalle fra alle mot sky.
> La'kke byen få ro, men la den få merke den er en studenterby.
> Og øl og dram, og øl og dram, og øl og dram, og øl og dram.

Lagre filen og lukk den.

Nå er vi klare til å sende denne endringen til GitHub!
Kjør følgende kommandoer i terminalen:

```
git add nu-klinger.txt
```

```
git commit -m "la inn refrenget på nu klinger"
```

```
git push --set-upstream origin nu_klinger
```

Flott, endringene er pushet til branchen `nu_klinger`! La oss merge `nu_klinger` med `master`.
Bytt tilbake til master-branchen ved å kjøre følgende kommando i terminalen:

```
git switch master
```

Merge nu_linker-branchen inn i master ved å kjøre følgende kommando i terminalen:

```
git merge nu_klinger
```

Og tilslutt, push til GitHub:

```
git push
```

Nå er nu klinger ferdig for denne gang og det er Person 1 sin tur til å gjøre ferdig ja vi elsker!

## Oppgave 4 - Branching

**Person 1:**
Pass på at du står i master-branchen og pull endringene fra din samarbeidspartner ved å kjøre følgende kommando i terminalen:

```
git pull
```

Sjekk at nu_klinger.txt har blitt endret.

Lag en ny branch som heter `nasjonalsang` ved å kjøre følgende kommando i terminalen:

```
git branch nasjonalsang
```

Bytt til den nye branchen ved å kjøre følgende kommando i terminalen:

```
git switch nasjonalsang
```

Åpne filen ja-vi-elsker.txt og lim inn verset (vist under) i bunn av filen.

> Elsker, elsker det og tenker på vår far og mor og den saganatt som senker drømme på vår jord.

Lagre filen og lukk den.

Nå er vi klare til å sende denne endringen til GitHub!
Kjør følgende kommandoer i terminalen:

```
git add ja-vi-elsker.txt
```

```
git commit -m "videreutviklet Ja, vi elsker dette landet"
```

```
git push --set-upstream origin nasjonalsang
```

Nå kan endringene merges inn i master. Bytt til master-branchen:

```
git checkout master
```

Merge endringene inn i master:

```
git merge nasjonalsang
```

Og push endringene til GitHub:

```
git push
```

## Oppgave 5 - Merge Conflicts

En kjent utfordring når man samarbeider i team er merge conflicts. Disse oppstår gjerne når flere personer har gjort endringer i samme fil. Da vet ikke Git hvilke endringer som skal inkluderes, og man får en merge conflict.

Nå skal vi simulere en merge conflict ved at Person 1 og Person 2 skal legge til en ny linje i `dans-paa-bordet.txt` i hver sin branch, for så å merge disse inn i master-branchen. Før dere starter, pass på at begge står i master-branchen og at dere har pullet de siste endringene.

Først kan Person 1 legge til en ny linje i `dans-paa-bordet.txt` i en ny branch kalt `person_1_branch`:

```
git branch person_1_branch
```

```
git switch person_1_branch
```

Legg til følgende tekst i dans-paa-bordet.txt (eller hva du vil):

> Je'kke fransk men hun liker min kissing

Lagre og lukk filen.
Push endringene til GitHub:

```
git add dans-paa-bordet.txt
```

```
git commit -m "Person 1 endrer dans-paa-bordet.txt"
```

```
git push --set-upstream origin person_1_branch
```

Bytt tilbake til master-branchen:

```
git switch master
```

Nå kan Person 2 gjøre det samme, men i en ny branch kalt person_2_branch, og legg inn en annen tekst i `dans-paa-bordet.txt`. For eksempel teksten under:

> Hun e'kke en engel men hun er en blessing

Nå har altså de to branchene person_1_branch og person_2_branch ulik tekst på linje 6 i filen `dans-paa-bordet.txt`. Hva skjer når vi nå skal merge dette inn i master?

Nå kan Person 1 pulle de siste endringene mens man står i master-branchen:

```
git pull
```

Også kan person_1_branch merges inn i master:

```
git merge person_1_branch
```

Deretter, merge `person_2_branch` inn i master ved å kjøre følgende kommando:

```
git merge person_2_branch
```

Aiaiai, merge conflict! Hvordan fikser vi dette?

Åpne filen ddans-paa-bordet.txt i en valgfri tekst-editor (for eksempel Visual Studio Code, Pycharm, TextEdit eller Notepad). Her ser vi at git har skrevet inn noe rart i filen. Her må dere bestemme hvilken av linjene som skal taes med, og slette den andre (med de tilhørende rare linjene). Etter dette burde filen se ut som dette hvis dere valgte å beholde endringene fra `person_2_branch`:

> Mi amor, danser for seg selv
>
> Og alle boys vil bli med henne hjem
>
> Men hun danser for seg selv
>
> Ballin'
>
> Mokel
>
> Hun e'kke en engel men hun er en blessing

Nice, nå kan vi pushe dette til master:

```
git add git add dans-paa-bordet.txt
```

```
git commit -m "fikset merge conflict"
```

```
git push
```

Og master-branchen er oppdatert med de siste endringene!
