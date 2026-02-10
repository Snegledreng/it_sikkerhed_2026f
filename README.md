# Software sikkerhed 2026f
Dette er et skoleprojekt på Zealand Næstved.  
Tryk på et emne for at læse mere.

<details>
  <summary>03/02/26 UniTestingPython</summary>

  Hvordan test resultater ser ud når repo lige er blevet klonet. 
  <img width="1884" height="1125" alt="image" src="https://github.com/user-attachments/assets/a246002c-0a9c-4763-a1f5-247f2d00df1d" />

  Jeg har ændret tasks.json til at virke på linux i .venv.
  Tasks ser sådan ud nu:
  <img width="1029" height="745" alt="image" src="https://github.com/user-attachments/assets/f00094c5-365d-4360-a85d-7f3b286f2615" />

  Efter nogle rettelser, passer to tests nu, og den som crasher bliver skippet.
  <img width="1884" height="1125" alt="image" src="https://github.com/user-attachments/assets/00b099be-a3fe-4e71-b651-c19776120636" />
</details>

<details>
  <summary>10/02/26 Kryptering</summary>
  
  *hvorfor er det smart at bruge en flat_file_db?*  
  Den er nem at transportere, da der ikke er nogen serveropsætning, og den kan implementeres på forskellige måder, uden den store forskel.  
  > Personligt foretrækker jeg SQLite, da det er nemt at lave en ORM til SQLite, når man arbejder med udvikling, og hurtigt at pege den på en rigtig SQL-server senere.

  *Screenshot af virkende unit tests:*  
  <img width="1009" height="238" alt="image" src="https://github.com/user-attachments/assets/da0ed79e-9409-4d4d-88c7-61197a54f26a" />
  *screenshot af eksempel på navngivning og brug af "given, when, then"-brug i tests:*  
  <img width="676" height="555" alt="image" src="https://github.com/user-attachments/assets/f2a40a88-e4a4-40ce-8bdb-274358a084bb" />

  ---
  Jeg har haft problemer med selve implementeringen af kryptering og hashing i C#, men jeg vil her forklare hvorfor og hvornår man bør gøre det

  *Hvornår og hvorfor kryptere man data?*  
  Man bør kryptere data inden det smides i databasen. (*især personfølsom data skal krypteres*)  
  Dette gøres i tilfældet af at databasen bliver lækket, og gør at den ikke er brugbar for dem som får adgang til dataen.

  *Hvornår og hvorfor dekrypterer man data?*  
  Man bør kun dekryptere data når det skal bruges til f.eks. at blive vist i UI, eller man skal lave beregninger på dem.  
  Det skal dekrypteres for at blive brugbart.

  *Hvornår og hvorfor fjerner man dekrypteret data fra hukommelsen?*  
  Det bør fjernes når man er færdig med at vise det, eller lave beregninger på det.  
  Dette skal gøres for at sikre at uvedkommende (*hackere*) ikke kan lave et memory dump af computeren det ligger på.

  
</details>
