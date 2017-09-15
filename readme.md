# NoNpDrm Plugin by TheFloW

## Features
- Exports PS Vita content license keys as fake licences.
- Bypasses expiration of PlayStation Plus and other timed licenses.
- Allows you to run trial versions as full versions.
- Allows sharing PFS encrypted content (unmodified non decrypted games) across multiple PS Vita accounts and devices using generated fake license files.
- Imported games behave as purchased games and allow the use of game updates seemlessly downloaded from the Sony Interactive Entertainment Network (PlayStation Network) as long as these updates run on firmware 3.60 and lower.
- Games can also be stripped of their PFS encryption using tools such as Vitamin just as any other purchased games would.
- Using purchased applications on deactivated devices.

In a nutshell, this plugin allows you to bypass DRM protection on any PS Vita content.

### This software WILL NOT
- Allow modifications to your games/applications.
- Work with PFS decrypted content (such as games dumped using applications such as Vitamin or MaiDumpTool).
- Enable you to run applications/use content without a valid license or a fake license file.
- Work with PlayStation Portable or PlayStation 1 titles (should you wish to play such titles, you may want to look into the [Adrenaline software](https://github.com/TheOfficialFloW/Adrenaline/releases)).
- Work with applications that only run on firmware 3.61 or later.

## Legal Disclaimer
- The removal and distribution of DRM content and/or circumventing copy protection mechanisms for any other purpose than archiving/preserving games you own licenses for is illegal.  
- This software is meant to be strictly reserved for your own **PERSONAL USE**.
- The author does not take any responsibility for your actions using this software.

## Software Requirements
This software will only work on PlayStation Vita, PlayStation Vita TV, PlayStation TV devices running on firmware 3.60, the taiHEN framework and HENkaku need to be running on your device, for more information please connect to https://henkaku.xyz/  
For all the possibilities described below, you should use [VitaShell v1.6](https://github.com/TheOfficialFloW/VitaShell/releases) or higher for faster transfers.  
VitaShell lets you mount your PS Vita's Memory Card or Game Card to your PC over USB.  
On a PS TV device, you can mount a USB flash drive and copy files to `uma0:`.

## Installation
Download the latest [nonpdrm.skprx](https://github.com/TheOfficialFloW/NoNpDrm/releases), copy it to `ux0:tai` and modify the `ux0:tai/config.txt` file to add the path to the module under `*KERNEL` as follows

```
*KERNEL
ux0:tai/nonpdrm.skprx
```

If you know what you are doing, you may change this path to an arbitrary location as long as it matches the exact location of the module. 
You may also edit the `ur0:tai/config.txt` instead assuming you do not have a config.txt file inside the `ux0:tai/` folder

## Creating the fake license
In order to generate a fake license file containing the application's rif key, you must first launch the application with the NoNpDrm plugin enabled.  
The fake licenses for the applications will then be stored at
- `ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif`
- `ux0:nonpdrm/license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif` (for additional content)

## Sharing Digital Applications
- If you wish to use the application on the same device but on a different account, simply copy the fake license `6488b73b912a753a492e2714e9b38bc7.rif` to
  `ux0:license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif`.
- If you wish to use the application on a different device, transfer the content of `ux0:app/TITLE_ID` to your PC and copy the fake license `ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif` file as `TITLE_ID/sce_sys/package/work.bin` **You need to overwrite the original work.bin**

**Note**: on games obtained through the PlayStation Store, `work.bin` is tied to your Sony Interactive Entertainment (also known as PlayStation Network) account and contains your account ID. The fake license does however **NOT** contain any personal information.

## Sharing Game Cards
Transfer the `gro0:app/TITLE_ID` folder and its content to `ux0:app/TITLE_ID` or to your computer and save the fake license
`ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif` as `TITLE_ID/sce_sys/package/work.bin`.

For faster transfers you can mount the Game Card over USB. To do so, open VitaShell (See the Software Requirements section of this documentation), press the START button of your PS Vita, in the `Main settings` menu, select `Game Card` next to the `USB device` option and press START once again to close the settings tab.  
Now connect your PS Vita to your computer over USB and press the SELECT button.

**Note**: Mounting Game Cards over USB does not work on PlayStation TV or PlayStation Vita TV devices.

## Sharing Additional Content
You may share any additonal content across devices from `ux0:addcont/TITLE_ID/DLC_FOLDER` or, on selected card games, from `grw0:addcont/TITLE_ID/DLC_FOLDER`  
To do so, copy the fake license `ux0:nonpdrm/license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif` to `ux0:license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif`.

## Sharing Game Updates
While you may simply copy the content of `ux0:patch/TITLE_ID` or `grw0:patch/TITLE_ID` (in the case of selected card titles), game updates can be downloaded and installed directly from the PlayStation Network (unless the newest update is not compatible on 3.60).

## Installing shared applications
- Digital Application and Game Cards must be stored at the following location: `ux0:app/TITLE_ID`
- Additional contents must be stored at the following location: `ux0:addcont/TITLE_ID/DLC_FOLDER` and their associated licenses must be copied to
  `ux0:license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif`.
- Game Updates must be stored at the following location: `ux0:patch/TITLE_ID`.

Open VitaShell (version 1.6 or later) and press △ in the `home` section of VitaShell and choose `Refresh livearea`.  
This will trigger the installation if the files have been placed correctly and the licenses within `work.bin` files are valid.

## Overview
Should you decide to store your game contents on your computer, it is recommended to use the same structure as `ux0:` as shown below:

```
├───addcont
│   └───TITLE_ID
│   │   └───DLC_FOLDER
├───app
│   └───TITLE_ID
│   │   └───sce_sys
│   │       └───package
│   │           └───work.bin (copied or overwritten from ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif)
├───license
│   └───addcont
│   │   └───TITLE_ID
│   │       └───DLC_FOLDER
│   │           └───6488b73b912a753a492e2714e9b38bc7.rif (copied from ux0:nonpdrm/license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif)
├───patch
│   └───TITLE_ID
```

## Source code
The source code is located within the `src` directory and is licensed under `GPLv3`.

## Troubleshooting
- "I am getting a `C1-2758-2` error when trying to run a game/application" - Your game has not been copied properly and at least one of the file is corrupt, please copy it again and retry.
- "I am getting a `C1-6703-6` error when trying to run a game/application" - You are running NoNpDrm from a Devkit/Testkit (PDEL/PTEL) these devices are not currently supported.
- "I am getting a `C0-9250-6` error when trying to run a game/application" - The `nonpdrm.skprx` module is not loaded, make sure the path to the module is written in `ur0:tai/config.txt` or `ux0:tai/config.txt` if the later exists on your device.
- "I am getting a `NP-6182-7` error when trying to run a game/application" - This error occured only once during our test while attempting to run an expired PlayStation Plus timed application, attempting to run the game once more fixed the issue, we never managed to reproduce this error, should you manage to consistently reproduce this issue, please open an issue on github.
- "My game/application displays as a trial version in the livearea" - This happens because you copied a game/application featuring a trial mode, without or with an invalid/corrupt `work.bin`.
- "I somehow messed up the installation, how can I reinstall a game?" - You can delete the (fake) license at `ux0:license/app/TITLE_ID` and use the refresh option in VitaShell.

## Donation
All my work is voluntary and nonprofit, however you can support my work by making a small donation - no matter how small, I'd be very thankful! Just be careful what you write to me in the message ;)  
[Donation Link](https://www.paypal.me/PSVitaTheFloW)

## Special thanks
- Thanks to Team molecule for HENkaku and thanks to [yifanlu](https://twitter.com/yifanlu) for taiHEN
- Thanks to [Mathieulh](https://twitter.com/Mathieulh) for beta testing and helping me writing this readme

Italian translate
Plugin NoNpDrm di TheFloW

Caratteristiche

Esporta le chiavi di licenza dei contenuti PS Vita come le false licenze.
Bypasserà la scadenza di PlayStation Plus e di altre licenze temporanee.
Consente di eseguire versioni di prova come versioni complete.
Consente la condivisione di contenuti crittografati PFS (giochi non decodificati non modificati) su più account e dispositivi PS Vita utilizzando file di licenza generati generati.
I giochi importati si comportano come giochi acquistati e consentono l'utilizzo di aggiornamenti di gioco senza alcun problema scaricati dalla Sony Interactive Entertainment Network (PlayStation Network) a condizione che questi aggiornamenti siano eseguiti su firmware 3.60 e inferiore.
I giochi possono anche essere spogliati della loro crittografia PFS utilizzando strumenti come la vitamina, proprio come qualsiasi altro gioco acquistato.
Utilizzo di applicazioni acquistate su dispositivi disattivati.
In poche parole, questo plugin ti permette di ignorare la protezione DRM su qualsiasi contenuto PS Vita.

Questo software NON

Consenti modifiche ai tuoi giochi / applicazioni.
Lavorare con i contenuti decodificati PFS (come i giochi scaricati utilizzando applicazioni come Vitamina o MaiDumpTool).
Consente l'esecuzione di applicazioni / utilizzo di contenuti senza una licenza valida o un file di licenza falso.
Lavorare con i titoli PlayStation Portable o PlayStation 1 (se volete giocare a tali titoli, potresti guardare il software Adrenaline ).
Lavorare con applicazioni che eseguono solo il firmware 3.61 o successivo.
Disclaimer legale

La rimozione e la distribuzione di contenuti DRM e / o l'elusione di meccanismi di protezione della copia per qualsiasi altro scopo che l'archiviazione / la conservazione dei giochi che possiedono licenze è illegale.
Questo software è destinato ad essere strettamente riservato per il tuo uso personale PERSONAL .
L'autore non si assume alcuna responsabilità per le tue azioni utilizzando questo software.
Requisiti software

Questo software funzionerà solo su PlayStation Vita, PlayStation Vita TV, dispositivi PlayStation TV in esecuzione su firmware 3.60, il framework taiHEN e HENkaku devono essere in esecuzione sul tuo dispositivo, per ulteriori informazioni si prega di collegarsi a https://henkaku.xyz/
Per tutti le possibilità descritte di seguito, è necessario utilizzare VitaShell v1.6 o superiore per trasferimenti più veloci. 
VitaShell ti permette di montare la scheda di memoria o la scheda di gioco di PS Vita sul tuo PC tramite USB. 
Su un dispositivo TV PS, è possibile montare un'unità flash USB e copiare i file su uma0:.

Installazione

Scaricare l'ultima nonpdrm.skprx , copiarla ux0:taie modificare il ux0:tai/config.txtfile per aggiungere il percorso al modulo *KERNELcome segue

*KERNEL
ux0:tai/nonpdrm.skprx
Se sai cosa stai facendo, puoi cambiare questo percorso in una posizione arbitraria finché corrisponda alla posizione esatta del modulo. Puoi anche modificare l' ur0:tai/config.txtopzione supponendo di non avere un file config.txt all'interno della ux0:tai/cartella

Creazione della licenza falsa

Per generare un file di licenza falso contenente la chiave rif rif. Dell'applicazione, è necessario innanzitutto avviare l'applicazione con il plug-in NoNpDrm abilitato. 
Le licenze false per le applicazioni saranno quindi memorizzate in

ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif
ux0:nonpdrm/license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif (per ulteriori contenuti)
Condivisione di applicazioni digitali

Se si desidera utilizzare l'applicazione sullo stesso dispositivo, ma su un altro account, è sufficiente copiare la licenza falsa 6488b73b912a753a492e2714e9b38bc7.rifa ux0:license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif.
Se si desidera utilizzare l'applicazione su un dispositivo diverso, trasferire il contenuto ux0:app/TITLE_IDsul PC e copiare il ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.riffile di licenza falso in quanto TITLE_ID/sce_sys/package/work.bin è necessario sovrascrivere l'originale work.bin
Nota : sui giochi ottenuti tramite PlayStation Store, work.binè legato all'account Sony Interactive Entertainment (noto anche come PlayStation Network) e contiene il tuo ID account. La licenza falsa tuttavia NON contiene informazioni personali.

Condivisione di carte di gioco

Trasferire la gro0:app/TITLE_IDcartella e il suo contenuto su ux0:app/TITLE_IDo sul computer e salvare la licenza falsa ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rifcome TITLE_ID/sce_sys/package/work.bin.

Per trasferimenti più veloci è possibile montare la Game Card su USB. A tale scopo, aprire VitaShell (vedere la sezione Requisiti software di questa documentazione), premere il pulsante START della PS Vita nel Main settingsmenu, selezionare Game Cardaccanto USB deviceall'opzione e premere di nuovo START per chiudere la scheda impostazioni. 
Ora collegare il tuo PS Vita al computer tramite USB e premere il pulsante SELECT.

Nota : il montaggio delle schede di gioco tramite USB non funziona su dispositivi PlayStation TV o PlayStation Vita TV.

Condivisione di contenuti aggiuntivi

Si può condividere qualsiasi contenuto addizionale su più dispositivi da ux0:addcont/TITLE_ID/DLC_FOLDERo, a giochi di carte selezionati, dalla grw0:addcont/TITLE_ID/DLC_FOLDER
A tale scopo, copiare la licenza falso ux0:nonpdrm/license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rifa ux0:license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif.

Condivisione di aggiornamenti di giochi

Mentre si può semplicemente copiare il contenuto ux0:patch/TITLE_IDo grw0:patch/TITLE_ID(in caso di titoli di carte selezionati), gli aggiornamenti di gioco possono essere scaricati e installati direttamente dalla PlayStation Network (a meno che l'aggiornamento più recente non sia compatibile con 3.60).

Installazione di applicazioni condivise

L'applicazione digitale e le carte di gioco devono essere memorizzate nel seguente luogo: ux0:app/TITLE_ID
I contenuti aggiuntivi devono essere memorizzati nella posizione seguente: ux0:addcont/TITLE_ID/DLC_FOLDERle relative licenze devono essere copiate ux0:license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif.
Gli aggiornamenti di gioco devono essere conservati al seguente indirizzo: ux0:patch/TITLE_ID.
Aprire VitaShell (versione 1.6 o successiva) e premere △ nella homesezione di VitaShell e scegliere Refresh livearea. 
Questo innescherà l'installazione se i file sono stati inseriti correttamente e le licenze all'interno dei work.binfile sono valide.

Panoramica

Se si decide di memorizzare il contenuto del gioco sul computer, si consiglia di utilizzare la stessa struttura ux0:come illustrato di seguito:

├───addcont
│   └───TITLE_ID
│   │   └───DLC_FOLDER
├───app
│   └───TITLE_ID
│   │   └───sce_sys
│   │       └───package
│   │           └───work.bin (copied or overwritten from ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif)
├───license
│   └───addcont
│   │   └───TITLE_ID
│   │       └───DLC_FOLDER
│   │           └───6488b73b912a753a492e2714e9b38bc7.rif (copied from ux0:nonpdrm/license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif)
├───patch
│   └───TITLE_ID
Codice sorgente

Il codice sorgente si trova all'interno della srcdirectory ed è sotto licenza GPLv3.

Risoluzione dei problemi

"Ottengo un C1-2758-2errore quando si tenta di eseguire un gioco / applicazione" - Il tuo gioco non è stato copiato correttamente e almeno uno dei file è danneggiato, si prega di ripeterlo e riprovare.
" C1-6703-6Ottengo un errore quando si tenta di eseguire un gioco / applicazione" - Esegui NoNpDrm da un Devkit / Testkit (PDEL / PTEL) questi dispositivi non sono attualmente supportati.
"Ottengo un C0-9250-6errore quando si tenta di eseguire un gioco / applicazione" - Il nonpdrm.skprxmodulo non viene caricato, assicurarsi che il percorso al modulo sia scritto ur0:tai/config.txto ux0:tai/config.txtse esiste più avanti sul dispositivo.
"Ottengo un NP-6182-7errore quando si tenta di eseguire un gioco / applicazione" - Questo errore si è verificato solo una volta durante il nostro test durante il tentativo di eseguire un'applicazione temporanea di PlayStation Plus scaduta, tentando di eseguire il gioco ancora una volta risolto il problema, non siamo mai riusciti a riprodurre questo errore, se riesci a riprodurre in modo coerente questo problema, apri un problema su github.
"Il mio gioco / applicazione viene visualizzato come versione di prova nella livearea". Ciò accade perché hai copiato un gioco / un'applicazione con una modalità di prova senza o con un invalid / corrotto work.bin.
"In qualche modo ho messo l'installazione, come posso reinstallare un gioco?" - È possibile eliminare la licenza (falsa) ux0:license/app/TITLE_IDe utilizzare l'opzione di aggiornamento in VitaShell.
Donazione

Tutto il mio lavoro è volontario e non profit, tuttavia puoi sostenere il mio lavoro facendo una piccola donazione - non importa quanto piccola, sarei molto grato! Basta prestare attenzione a quello che mi scrivi nel messaggio;) 
Donation Link

Ringraziamenti speciali

Grazie alla molecola di squadra per HENkaku e grazie a yifanlu per taiHEN
Grazie a Mathieulh per il test beta e mi ha aiutato a scrivere questo readme
