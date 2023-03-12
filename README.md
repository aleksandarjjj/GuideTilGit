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
![ScreenShot](pics/16.png)
![ScreenShot](pics/17.png)
![ScreenShot](pics/18.png)
![ScreenShot](pics/19.png)
![ScreenShot](pics/20.png)
![ScreenShot](pics/21.png)
![ScreenShot](pics/22.png)
![ScreenShot](pics/23.png)
![ScreenShot](pics/24.png)
![ScreenShot](pics/25.png)
![ScreenShot](pics/26.png)
![ScreenShot](pics/27.png)
