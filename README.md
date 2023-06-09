# Hvordan man bruger Git

1. Ved at benytte 'Git Bash here...' åbnes en kommandoprompt, der ser ud som følgende:
![ScreenShot](pics/1.png)

2. 'Git Bash' svare til Windows kommandoprompten 'cmd', og de ses her side om side.
   'Git' kan det samme som 'cmd' med et ekstra VCS (Version Control System) lag oveni, der kan styre såkaldte 'repositories',
   hvilket er en samling af filer, der løber kan trackes og opdateres. Det vil sige, at flere forskellige brugere kan hente,
   ændre, fjerne eller tilføje filer. I 'Git' cmd'en (kommandoprompten som er åbnet med 'Git Bash here...') vinduet kan
   man skrive ```mkdir testRepo``` hvorved prompten vil lave en ny mappe kaldet 'testRepo'.
![ScreenShot](pics/2.png)

3. Da stien på Git stadig er for skrivebordet kan den nye mappe tilgås med ```cd testRepo```. Det kan nu ses, at stien i
   Git opdateres, og at den nu er inde i mappen testRepo.
![ScreenShot](pics/3.png)

4. Git kan tracke både lokale og remote repositories, og det sker _ikke_ automatisk, at disse to forbindes. Derfor skal man
   både oprette et 'lokalt' repository, som man så kan forbinde med et 'remote' repository på f.eks. GitHub eller lignende.
   Da stien for Git er inde i mappen testRepo, kan vi indlede et nyt lokalt repository med kommandoen ```git init```.
   Man kan være sikker på, at et lokalt repository er blevet oprettet ved at '.git' mappen dukker op.
![ScreenShot](pics/4.png)

5. Mappen er normalt skjult, og man kan se den ved at ændre på følgende indstilling i kontrolpanelet.
![ScreenShot](pics/5.png)

6. Vi har nu oprettet et lokalt repository, som vi gerne vil forbinde til et remote. Bemærk, at alle stier med en '.git' mappe
   er repositories. Inde på GitHub opretter vi et remote repository kaldet 'testRepo'.
![ScreenShot](pics/6.png)

7. Vi har nu følgende: et tomt remote repository og et tomt lokalt repository.
![ScreenShot](pics/7.png)

8. Med kommandoen ```git remote add origin <url-for-repository>``` kan vi nu forbinde vores lokale repository med et oprettede
   inde på GitHub. Bemærk at der er lavet en stavefejl i kommandoprompten. Et repository kan have flere 'branches', og man kan se
   hvilken en man er på ved siden af stien (understreget med rødt). Dette bliver relevant senere.
![ScreenShot](pics/8.png)

9. Med kommandoen ```git status``` kan vi se om alle filer inde i det lokale repository er trackede eller om der
   mangler nogle fra det remote repository, hvis vores lokale ikke er up-to-date. Lige nu er både det remote
   samt det lokale repository tomt.
![ScreenShot](pics/9.png)

10. Vi vil nu gerne prøve at tilføje noget. ```git add --all``` benyttes til at filøje filer. Hvis vi prøver at benytte
    kommandoen kan vi se, at intet filføjes, hvis vi bruger ```git add --all```, da det lokale repo som sagt er tomt.
![ScreenShot](pics/10.png)

11. Vi opretter nu en tom fil (typen og om den indeholder noget er irrelevant), som vi gerne vil tracke og pushe
    over i vores remote repository. Filen kan tilføjes med  ```>.gitkeep```. Vi burde nu have oprettet en fil
    der kan trackes med ```git add --all```.
![ScreenShot](pics/11.png)

12. Filer man gerne vil tracke kan tilføjes enkeltvis eller som sagt med ```git add --all```. Efterfølgende kan vi
    prøve at lave en status på hvilke filer som er trackede med ```git status```, og kan se at filen er blevet tilføjet.
![ScreenShot](pics/12.png)

13. Vi benytter nu ```git commit -m "Din besked her"``` til at 'pakke' alle de filer vi gerne vil have tracke ned, så
    de er klar til at blive 'skubbet' ud eller pushet til vores remote repository. Se commitsene som en slags øjebliks-
    billeder, hvor man altid kan gå tilbage til senere hen, hvis man vil slette fremtidige ændringer. Med en 
    ```git status``` ses nu, at vi har gemt de filer vi gerne ville tracke (nothing to commit, working tree clean).
![ScreenShot](pics/13.png)

14. Se bort fra 'remote add origin' i Git indtastet nedenfor. Vi synkroniserer nu vores lokale repository med det remote ved at skrive
    ```git push --all```. Hvis GitHub nu refreshes burde den nye '.gitkeep. fil dukke op.
![ScreenShot](pics/14.png)

15. ```git log``` kan tilgås, så man kan se en liste over alle tidligere commits. Et commit identificeres med den såkalde
    'hash', som er den lange kombination af bogstaver af tal som ses ud for commitet. Denne skal benyttes, hvis man ønsker
    at gendanne tidlivere versioner af filerne eller programmet. Tryk ```q``` på keyboardet for at gå ud af 'log'-tilstanden
    i Git.
![ScreenShot](pics/15.png)

16. Vi vil nu gerne lave en ny mappe for en person, der kan tilføje sine filer eller sin løsning til en opgave.
    Vi sørger for at Git-kommandoprompten er på den rigtige sti, og opretter en mappe med ```mkdir person1```.
    Hvis vi nu prøver at lave en status kan vi se, at den siger 'nothing to commit' selvom mappen er tilføjet.
    Der er igen fordi, at Git tracker filer og _ikke_ mapper! Vi skal derfor oprette en fil i mappen for, at
    den kan trackes.
![ScreenShot](pics/16.png)

17. Vi går ind i den nye mappe med ```cd person1```. Vi opretter en fil med ```>.gitkeep``` og går nu tilbage til vores
    'testRepo' mappe med ```cd -```. En status vil nu smide en besked om, at vi har en mappe med en eller flere filer, der
    ikke er blevet tilføjet.
![ScreenShot](pics/17.png)

18. Vi tilføjer nu undermappen og den trackede fil med ```git add --all```, ```git commit -m "First Commit"``` og
    ```git push --all```. Hvis GitHub refreshes kan vi nu se, at vores lokale repository er blevet 'pushet' til vores
    remote repository og at mappen nu kan tilgås der.
![ScreenShot](pics/18.png)

19. Hvis man er flere personer, som gerne vil pushe sin opgaveløsning, er det ikke smart, at alle konstant opdaterer
    'hoved'-branchen. Hovedbranchen skal helst bestå af færdige opgaver med en mappe for hvert gruppemedlem, og dennes
    endelige løsning her for ellers kan det blive rodet, hvis løsninger haves i forskellige branches (forgreninger) med
    udgangspunkt i main- eller master-branchen. Derfor kan vi oprette en ny branch med ```git branch person2```. Branchen
    tilgås med ```git checkout person2```, og denne skal tracke en ny mappe vi har oprettet (med en .gitkeep fil i).
    Fra tidligere ved vi, at vi kan se hvilken branch vi er i ud fra parantesen ved siden af stien i kommandoprompten.
![ScreenShot](pics/19.png)

20. Vi tilføjer nu 'person2' med ```git add --all```, ```git commit -m "On branch 'person2'"``` og
    ```git push --all```. Hvis GitHub refreshes kan vi nu se, at der _ikke_ er blevet tilføjet nogle filer til 'master'-
    branchen.
![ScreenShot](pics/20.png)

21. Vores remote repository burde nu opdateres til at indeholde to branches: master og person2. Hver af disse kan tilgås
    ved at vælge branchen og mapperne/filerne kan ses ved at trykke 'Show Code', hvis de ikke dukker op. Loggen viser
    desuden commit med den besked vi har skrevet (understreget med rødt), og branchen ud for hashen.
![ScreenShot](pics/21.png)

22. Nedenfor ses de to branches åbnet i hver sin browser for at se, hvilke filer som er tracket hvor. Som det kan ses,
    indeholder branchen 'person2' både 'person1' og 'person2' mapperne, mens 'master' kun indeholder 'person1'. Vi vil
    nu gerne prøve at samle disse, og pushe vores løsning over i hovedbranchen.
![ScreenShot](pics/22.png)

23. Vi bruger nu ```git checkout master ``` til at switche branch. Læg mærke til at mapperne i vores lokale
    repository opdateres (da vi er på 'master' som kun tracker 'person1' mappen).
![ScreenShot](pics/23.png)

24. 'master' branchen merges nu med 'person2' med ```git merge person2```.
![ScreenShot](pics/24.png)

25. Vores remote repository kan nu opdateres og master branchen burde indeholde alle mapperne (har glemt at trykke
    'View code' på billedet).
![ScreenShot](pics/25.png)

26. Vi vil nu gerne slette den branch vi har merged, da den kun tracker den enkelte opgaveløsning, og ikke opdateres løbende.
    Der er ingen grund til at beholde den, da vi har alt vi skal bruge på master branchen, og da vi ved næste opgave
    bare kan lave en ny vilkårlig branch ud fra master, tilføje vores løsning, og merge den. Det er bedst at gøre dette,
    da vi på denne måde også slipper for at løbe ind i problemer hvis man skal først skal til at opdatere den gamle, tilføje
    sin kode og så pushe den igen. Vi sletter branchen lokalt med ```git branch -d person2```.
![ScreenShot](pics/26.png)

27. Branchen vil stadig være på vores remote repository, og kan slettes med ```git push origin -d person2```
![ScreenShot](pics/27.png)

   Du kan nu finde ud af, at oprette et lokalt samt remote repository, og synkronisere mellem disse. Desuden kan du oprette branches,
   slette dem og merge dem med hinanden. Husk at sørge for at din lokale branch er på samme udgangspunkt som din remote, da en af
   dine andre gruppemedlemmer kan have tilføjet kode i mellemtiden. Dit lokale repository kan opdateres hvis der er sket ændringer
    med ```git pull --all```. Søg altid efter info på nettet, hvis du oplever problemer eller fejl - det meste kan findes på nettet!
   Guiden er lavet uden tidligere erfaring med Git eller GitHub.
    
   Hvis gruppen ønsker at gendanne en tidligere master branch kan I bruge disse kommandoer (svar fra StackOverflow):
   https://stackoverflow.com/questions/1895059/revert-to-a-commit-by-a-sha-hash-in-git/15563149#15563149
