# Commandolijst DevOps

---

### Git Basiscommando's

| Commando | Eventuele argumenten | Uitleg |
| --- | --- | --- |
| `git --help` | Geen of `<subcommando>` (bv. `git commit --help`) | Toont algemene documentatie en syntax van Git. Wanneer gecombineerd met een subcommando, opent het de gedetailleerde hulppagina (man page) van dat specifieke commando. In man pages navigeer je met `h` voor hulp en `/` om te zoeken.|
| `git init` | *Geen* | Initialiseert een nieuwe Git-repository in de huidige map door de verborgen `.git`-folder aan te maken. **Let op:** voer dit nooit uit in submappen van een bestaande repo of niet-projectmappen. Bij fatale fouten kan deze map verwijderd worden om opnieuw te beginnen.|
| `git config` | `user.name "<naam>"`<br> <br>`user.email "<email>"`<br><br>`--global` | Configureert gebruikersgegevens die gekoppeld worden aan commits. De vlag `--global` past dit toe voor alle projecten van de gebruiker; laat dit weg als je verschillende identiteiten (werk/privé/school) nodig hebt. |
| `git status` | `-u` | Toont de huidige status van de werkmap en staging area (welke bestanden zijn gewijzigd, untracked of klaar voor commit). De vlag `-u` geeft extra gedetailleerde informatie over untracked bestanden. *"Working tree clean"* betekent dat er geen verschillen zijn met de laatste commit.|
| `git add` | `<filenaam>` of `.` | Plaatst wijzigingen in de *staging area* ("in potlood noteren" dat er iets gewijzigd is). Let op waarschuwingen rond regeleindes (LF vs. CRLF op Windows/Linux), wat later bij Docker belangrijk kan zijn.|
| `git commit` | `-m "<bericht>"` | Legt de wijzigingen uit de staging area definitief vast in de projectgeschiedenis ("in pen noteren") en kent een unieke commit-hash toe. Met de vlag `-m` geef je direct een commit-boodschap mee zonder een teksteditor te openen.|
| `git log` | `--oneline`<br><br>`--graph`<br><br>`--abbrev-commit`<br><br>`--color --pretty=format:...` | Toont de chronologische commitgeschiedenis (recentste bovenaan, oudste onderaan). Vlaggen tonen beknopte informatie op één regel (`--oneline`), een visuele vertakkingsboom (`--graph`), ingekorte commit-hashes (`--abbrev-commit`) of aangepaste kleurenschema's.|
| `git tag` | `<tagnaam>` (bv. `v1`) | Kent een leesbare naam (label) toe aan de recentste of een specifieke commit in plaats van de onvoorspelbare hashcode. Eén commit kan meerdere tags bevatten.|
| `git show` | `<tagnaam>` | Toont de details en wijzigingen van een specifieke tag of commit.|
| `git reset` | `--soft <commit>` (bv. `HEAD^`)<br><br>`--hard <commit>` (bv. `HEAD^`) | Draait eerdere commits terug naar een opgegeven punt. Met `--soft` worden commits ongedaan gemaakt maar blijven je bestandswijzigingen behouden (staged). Met `--hard` worden zowel de commits als alle bestandswijzigingen onherroepelijk gewist en teruggezet naar die eerdere toestand.|
| `git diff` | Geen of tussen twee commits/tags (bv. `<tag1> <tag2>`) | Toont regel voor regel de verschillen tussen bestanden, staging area of commits (standaard: groen voor toevoegingen, rood voor verwijderingen).|
| `git checkout` | `<commit/tag/branch>` (bv. `v1`, `main`, `master`) | Verplaatst de repository-wijzer (HEAD) naar een andere toestand, tag of branch om code uit het verleden te inspecteren zonder de latere geschiedenis te wissen. Met `git checkout main` keer je terug naar de recentste toestand.|

---

### Belangrijke aanvullende concepten (geen directe commando's)

* **`.gitignore`**: Bestand waarin patronen, mappen of bestandsnamen worden gedefinieerd die niet getracked mogen worden (bv. gevoelige gegevens of build artifacts). Dit bestand wordt gecommit en gedeeld met teamleden.


* **`.git/info/exclude`**: Doet hetzelfde als `.gitignore`, maar geldt enkel lokaal voor jezelf en wordt nooit mee gecommit of gedeeld (handig voor persoonlijke instellingen en AI-labo's).