# Par izmantoto datu kopu
CIC-IDS2017 datu kopa ir izstrādāta, lai nodrošinātu daudzveidīgu un reprezentatīvu tīkla trafika informāciju, kas piemērota ielaušanās atklāšanas sistēmu (Intrusion Detection Systems – IDS) izstrādei un novērtēšanai. Tā aptver mūsdienu tīkla vidi, ietverot vairāk nekā 2,8 miljonus tīkla pakešu, kas iegūtas reālā tīkla infrastruktūrā septiņu dienu laikā.
Datu kopā apkopots gan normāls (labdabīgs) tīkla trafiks, gan dažādi kiberuzbrukumu scenāriji, tostarp: Brute Force, Heartbleed, Botnet, DoS, DDoS, Web Attack, un Infiltration. Jāatzīmē, ka datu kopa ir būtiski nelīdzsvarota – ievērojama daļa ierakstu attiecas uz labdabīgo trafiku, kamēr uzbrukumu piemēru ir relatīvi maz.
Kopumā datu kopa sastāv no 2 830 743 ierakstiem (rindām) un 79 atribūtiem (kolonnām). No tiem 78 ir skaitliskas pazīmes, savukārt viena sleja satur kategorisku mainīgo – mērķa klasifikatoru.
## Tika izmantota tikai Wednesday-workingHours.pcap_ISCX.csv dati
Sākotnēji tika plānots izmantot visas astoņas datu kopas, taču K-Nearest Neighbors (KNN) algoritms, kas ir aprēķinu ziņā intensīvs un resursietilpīgs (jo tas veic attālumu aprēķinus starp visiem datu punktiem), izrādījās neefektīvs lielas datu kopas apstrādē. Apstrādes laikā, pat pēc aptuveni 2000 sekundēm (vairāk nekā pusstundas), netika iegūts rezultāts par algoritma precizitāti. Tas norāda uz būtisku datora resursu nepietiekamību šāda mēroga datu analīzei, izmantojot KNN metodi.
Tāpēc, lai nodrošinātu vienlīdzīgus apstākļus visiem salīdzināmajiem rīkiem – gan mākslīgā intelekta metodēm, gan tradicionālajiem IDS risinājumiem (Snort, Suricata) –, analīzē tika izmantota tikai vienas dienas datu kopa: Wednesday-workingHours. Šāda pieeja ļāva strādāt ar identisku datu saturu gan AI algoritmiem (CSV formātā), gan IDS rīkiem (PCAP formātā), tādējādi nodrošinot metodoloģiski korektu salīdzinājumu.

Par datu kopām: https://www.unb.ca/cic/datasets/ids-2017.html

# Koda darbības princips
1. Sākotnēji tika ielādēta un izmantota tikai viena CIC-IDS2017 datu apakškopa – Wednesday-workingHours.pcap_ISCX.csv.
2. Datu kopas analīze - veikta sākotnējā datu analīze, iekļaujot dimensiju un trūkstošo vērtību pārbaudi.
3. Datu tīrīšana - dublēto ierakstu noņemšana, trūkstošo un bezgalīgo vērtību apstrāde, kolonnu nosaukumu normalizācija.
4. Datu kopas uzbrukumu vizualizācija - 
5. Datu sadalīšana treniņu un testēšanas kopās (70/30) - 
6. Decision Tree algoritms
7. KNN algoritms
8. Gaussian Naive Bayes algoritms

# Izmantotie avoti koda izstrādei
1. https://github.com/noushinpervez/Intrusion-Detection-CICIDS2017
2. https://github.com/rahul-38-26-0111-0003/Network-based-Intrusion-Detection-Systems/tree/master
