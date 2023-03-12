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

8. Med kommandoen ```git remote add origin <url-for-repository>``` kan vi nu forbinde det lokale repository med et oprettede
   inde på GitHub. Bemærk at der er lavet en stavefejl i kommandoprompten. Et repository kan have flere 'branches', og man kan se
   hvilken en man er på ved siden af stien (understreget med rødt). Dette bliver relevant senere.
![ScreenShot](pics/8.png)

9. 
![ScreenShot](pics/9.png)
![ScreenShot](pics/10.png)
![ScreenShot](pics/11.png)
![ScreenShot](pics/12.png)
![ScreenShot](pics/13.png)
![ScreenShot](pics/14.png)
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
