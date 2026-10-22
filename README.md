Ohjelmointivälineet ja versionhallinta IC250107-3004 kurssin lopputyö

Tämä repositorio toimii harjoittelualustana tälle lopputyölle.

Harjoituksen tavoite on oppia ja harjoitella Gitin keskeisiä sekä edistyneitä toimintoja terminaali-ympäristössä. Tarkoituksena minulla on toteuttaa harjoitukset suurimmaksi osaksi omissa haaroissaan, että lopputyö pysyy selkeänä. Käytin tehtävässä Gitiä, Git Bashia (VS Coden terminaalissa), GitHubia etärepositoriona ja SSH-yhteyttä kloonaukseen.

Tässä on lista käytetyistä komennoista, jotka keräsin VS Coden terminaalin historiasta.

"echo"
"echo .. > .gitignore"
"git clone"
"ssh -T"
"cd"
"git status"
"git add"
"git commit -m"
"git commit --amend -m"
"git log --oneline"
"git push"
"git push --all origin"
"git push origin <TAGI>"
"git pull"
"git switch"
"git switch -c"
"git branch"
"git merge"
"git merge --abort"
"git stash"
"git stash list"
"git stash pop"
"git revert HEAD"
"git reset --hard HEAD~1"
"git reflog"
"git cherry-pick"
"git tag"
"git tag -a"
"git show"
"git rebase main"
"history | grep git"
"rm"

Ongelmien ratkaisu:

- Merge-konflikti (info.txt): molemmat haarat loivat saman tiedoston eri sisällöllä. Avasin tiedoston VS Codessa, valitsin Accept Both Changes, tallensin ja tein "git add" ja "git commit".
- Yhdistäminen väärässä haarassa: yhdistin vahingossa haaran toiseen haaraan mainin sijaan. Peruin sen komennolla "git merge --abort" ja tein yhdistämisen uudelleen mainissa.
- Väärin kirjoitettu commit-viesti: korjasin viimeisimmän viestin komennolla "git commit --amend -m".
- "git commit" ilman "-m":ää: viesti tulkittiin tiedoston nimeksi ja tuli virhe. Ratkaisin lisäämällä "-m" -komentoon.
- Väärä haaran nimi mergessä: kirjoitin haaran nimen väärin päin ja Git ilmoitti, ettei haaraa löydy. Tarkistin nimet komennolla "git branch".
- "git stash" ei tallettanut mitään: tiedosto oli uusi eikä Git seurannut sitä. Lisäsin ja commitoin tiedoston ensin, ja sen jälkeen stash toimi.
- Pull Requestin tarkistus jäi latausruutuun: GitHub tarkisti taustalla. Odotin ja päivitin sivun ja homma toimi.

Mitä opin?

Tehtävä oli alussa melko hankala, koska en ollut aiemmin käyttänyt Gitiä tai GitHubia enkä opiskellut aihetta entuudestaan. Käytin apuna oppaita, internetiä ja opettajan kalvoja. Asiat alkoivat vähitellen hieman selkeytyä, mutta ne vaativat paljon toistoja ja harjoittelua tulevaisuudessa. Lopputyön tekeminen vei osaltani aikaa melko paljon, mutta mielestäni selviydyin siitä kunnialla maaliin.

Revert ja reset: "git revert" peruu commitin tekemällä uuden commitin, joka kumoaa edellisen muutokset. Historia säilyy ennallaan, joten se sopii myös jaetuille haaroille. "git reset" siirtää haaraa taaksepäin ja muuttaa historiaa, joten sitä pitää käyttää mielestäni varovaisemmin. Kokeilin tehtävässä kumpaakin vaihtoehtoa.

Stash: "git stash" tallettaa keskeneräiset muutokset hetkeksi sivuun, jolloin voi tehdä muuta ilman commitointia. "git stash pop" palauttaa muutokset takaisin. Opin myös, että stash ei ota mukaan uusia tiedostoja, joita ei ole commitoitu.

Cherry-pick: "git cherry-pick" kopioi yksittäisen commitin toisesta haarasta nykyiseen haaraan ilman, että koko haaraa yhdistetään. Siitä on mielestäni hyötyä, kun tarvitsee vain yhden korjauksen tai muutoksen.

Rebase: "git rebase main" siirtää haaran commitit mainin uusimman tilan päälle. Historiasta tulee suora eikä siihen synny ylimääräisiä merge-committeja kuten mergessä.

Pull Request: Pull Requestilla ehdotetaan muutosten yhdistämistä mainiin GitHubissa. Muutokset voi tarkistaa ennen yhdistämistä, ja GitHub kertoo, onko haarojen välillä konflikteja. Mielestäni se on hyödyllinen ja tarpeellinenkin tiimityöskentelyssä.

.gitignore: ".gitignore"-tiedostoon kirjoitetaan tiedostot, joita Git ei saa seurata. Se on tärkeä esimerkiksi salaisten tiedostojen kanssa, koska ne eivät silloin päädy vahingossa GitHubiin. Loin .gitignore-tiedoston komennolla echo ja kirjoitin siihen ohitettavan tiedoston nimen. Testasin toiminnan git status -komennolla.

Merge-konflikti: Opin ratkaisemaan sen VS Codessa valitsemalla säilytettävän sisällön, lisäämällä tiedoston ja tekemällä commitin.

Amend: "git commit --amend -m" korjaa viimeisimmän commitin viestin, kun sitä ei ole vielä pushattu. Opin, että viestin voi korjata ilman uutta committia.

Merge --abort: "git merge --abort" peruu kesken jääneen yhdistämisen ja palauttaa tilan ennen mergeä. Siitä oli apua, kun yhdistin vahingossa väärässä haarassa.

Kokonaisuutena opin (kantapään kautta :) ), että Git on turvallinen työkalu, koska lähes kaiken voi perua tai korjata. Komentojen muistaminen vaatii kuitenkin erittäin paljon harjoittelua, että sisäistää mitä mistäkin oikeasti tapahtuu.

Tekijä Sami Varis
opnro 2608086