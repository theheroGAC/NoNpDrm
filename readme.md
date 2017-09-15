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

<h1>Plugin NoNpDrm di TheFloW</h1>
<h2><a id="user-content-features" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#features" aria-hidden="true"></a>Caratteristiche</h2>
<ul>
 	<li>Esporta le chiavi di licenza di contenuto di PS Vita come licenze false.</li>
 	<li>Bypasserà la scadenza di PlayStation Plus e di altre licenze temporanee.</li>
 	<li>Consente di eseguire versioni di prova come versioni complete.</li>
 	<li>Consente la condivisione di contenuti crittografati PFS (giochi non decodificati non modificati) su più account e dispositivi PS Vita utilizzando file di licenza generati generati.</li>
 	<li>I giochi importati si comportano come giochi acquistati e consentono l'utilizzo di aggiornamenti di gioco senza alcun problema scaricati dalla Sony Interactive Entertainment Network (PlayStation Network) a condizione che questi aggiornamenti siano eseguiti su firmware 3.60 e inferiore.</li>
 	<li>I giochi possono anche essere spogliati della loro crittografia PFS utilizzando strumenti come la vitamina, proprio come qualsiasi altro gioco acquistato.</li>
 	<li>Utilizzo di applicazioni acquistate su dispositivi disattivati.</li>
</ul>
In poche parole, questo plugin ti permette di ignorare la protezione DRM su qualsiasi contenuto PS Vita.
<h3><a id="user-content-this-software-will-not" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#this-software-will-not" aria-hidden="true"></a>Questo software NON</h3>
<ul>
 	<li>Consenti modifiche ai tuoi giochi / applicazioni.</li>
 	<li>Lavorare con i contenuti decodificati PFS (come i giochi scaricati utilizzando applicazioni come Vitamina o MaiDumpTool).</li>
 	<li>Consente l'esecuzione di applicazioni / utilizzo di contenuti senza una licenza valida o un file di licenza falso.</li>
 	<li>Lavorare con i titoli PlayStation Portable o PlayStation 1 (se volete giocare a tali titoli, potresti guardare il <a href="https://github.com/TheOfficialFloW/Adrenaline/releases">software Adrenaline</a> ).</li>
 	<li>Lavorare con applicazioni che eseguono solo il firmware 3.61 o successivo.</li>
</ul>
<h2><a id="user-content-legal-disclaimer" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#legal-disclaimer" aria-hidden="true"></a>Disclaimer legale</h2>
<ul>
 	<li>La rimozione e la distribuzione di contenuti DRM e / o l'elusione di meccanismi di protezione della copia per qualsiasi altro scopo che l'archiviazione / la conservazione dei giochi che possiedono licenze è illegale.</li>
 	<li>Questo software è destinato ad essere strettamente riservato per il tuo uso personale <strong>PERSONAL</strong> .</li>
 	<li>L'autore non si assume alcuna responsabilità per le tue azioni utilizzando questo software.</li>
</ul>
<h2><a id="user-content-software-requirements" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#software-requirements" aria-hidden="true"></a>Requisiti software</h2>
Questo software funzionerà solo su PlayStation Vita, PlayStation Vita TV, dispositivi PlayStation TV in esecuzione su firmware 3.60, il framework taiHEN e HENkaku devono essere in esecuzione sul tuo dispositivo, per ulteriori informazioni si prega di collegarsi a <a href="https://henkaku.xyz/">https://henkaku.xyz/</a>
Per tutti le possibilità descritte di seguito, è necessario utilizzare <a href="https://github.com/TheOfficialFloW/VitaShell/releases">VitaShell v1.6</a> o superiore per trasferimenti più veloci.
VitaShell ti permette di montare la scheda di memoria o la scheda di gioco di PS Vita sul tuo PC tramite USB.
Su un dispositivo TV PS, è possibile montare un'unità flash USB e copiare i file su <code>uma0:</code>.
<h2><a id="user-content-installation" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#installation" aria-hidden="true"></a>Installazione</h2>
Scaricare l'ultima <a href="https://github.com/TheOfficialFloW/NoNpDrm/releases">nonpdrm.skprx</a> , copiarla <code>ux0:tai</code>e modificare il <code>ux0:tai/config.txt</code>file per aggiungere il percorso al modulo <code>*KERNEL</code>come segue
<pre><code>*KERNEL
ux0:tai/nonpdrm.skprx
</code></pre>
Se sai cosa stai facendo, puoi cambiare questo percorso in una posizione arbitraria finché corrisponda alla posizione esatta del modulo. Puoi anche modificare l' <code>ur0:tai/config.txt</code>opzione supponendo di non avere un file config.txt all'interno della <code>ux0:tai/</code>cartella
<h2><a id="user-content-creating-the-fake-license" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#creating-the-fake-license" aria-hidden="true"></a>Creazione della licenza falsa</h2>
Per generare un file di licenza falso contenente la chiave rif rif. Dell'applicazione, è necessario innanzitutto avviare l'applicazione con il plug-in NoNpDrm abilitato.
Le licenze false per le applicazioni saranno quindi memorizzate in
<ul>
 	<li><code>ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif</code></li>
 	<li><code>ux0:nonpdrm/license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif</code> (per ulteriori contenuti)</li>
</ul>
<h2><a id="user-content-sharing-digital-applications" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#sharing-digital-applications" aria-hidden="true"></a>Condivisione di applicazioni digitali</h2>
<ul>
 	<li>Se si desidera utilizzare l'applicazione sullo stesso dispositivo, ma su un altro account, è sufficiente copiare la licenza falsa <code>6488b73b912a753a492e2714e9b38bc7.rif</code>a <code>ux0:license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif</code>.</li>
 	<li>Se si desidera utilizzare l'applicazione su un dispositivo diverso, trasferire il contenuto <code>ux0:app/TITLE_ID</code>sul PC e copiare il <code>ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif</code>file di licenza falso in quanto <code>TITLE_ID/sce_sys/package/work.bin</code> <strong>è necessario sovrascrivere l'originale work.bin</strong></li>
</ul>
<strong>Nota</strong> : sui giochi ottenuti tramite PlayStation Store, <code>work.bin</code>è legato all'account Sony Interactive Entertainment (noto anche come PlayStation Network) e contiene il tuo ID account. La licenza falsa tuttavia <strong>NON</strong> contiene informazioni personali.
<h2><a id="user-content-sharing-game-cards" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#sharing-game-cards" aria-hidden="true"></a>Condivisione di carte di gioco</h2>
Trasferire la <code>gro0:app/TITLE_ID</code>cartella e il suo contenuto su <code>ux0:app/TITLE_ID</code>o sul computer e salvare la licenza falsa<code>ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif</code>come <code>TITLE_ID/sce_sys/package/work.bin</code>.

Per trasferimenti più veloci è possibile montare la Game Card su USB. A tale scopo, aprire VitaShell (vedere la sezione Requisiti software di questa documentazione), premere il pulsante START della PS Vita nel <code>Main settings</code>menu, selezionare <code>Game Card</code>accanto <code>USB device</code>all'opzione e premere di nuovo START per chiudere la scheda impostazioni.
Ora collegare il tuo PS Vita al computer tramite USB e premere il pulsante SELECT.

<strong>Nota</strong> : il montaggio delle schede di gioco tramite USB non funziona su dispositivi PlayStation TV o PlayStation Vita TV.
<h2><a id="user-content-sharing-additional-content" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#sharing-additional-content" aria-hidden="true"></a>Condivisione di contenuti aggiuntivi</h2>
Si può condividere qualsiasi contenuto addizionale su più dispositivi da <code>ux0:addcont/TITLE_ID/DLC_FOLDER</code>o, a giochi di carte selezionati, dalla <code>grw0:addcont/TITLE_ID/DLC_FOLDER</code>
A tale scopo, copiare la licenza falso <code>ux0:nonpdrm/license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif</code>a <code>ux0:license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif</code>.
<h2><a id="user-content-sharing-game-updates" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#sharing-game-updates" aria-hidden="true"></a>Condivisione di aggiornamenti di giochi</h2>
Mentre si può semplicemente copiare il contenuto <code>ux0:patch/TITLE_ID</code>o <code>grw0:patch/TITLE_ID</code>(in caso di titoli di carte selezionati), gli aggiornamenti di gioco possono essere scaricati e installati direttamente dalla PlayStation Network (a meno che l'aggiornamento più recente non sia compatibile con 3.60).
<h2><a id="user-content-installing-shared-applications" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#installing-shared-applications" aria-hidden="true"></a>Installazione di applicazioni condivise</h2>
<ul>
 	<li>L'applicazione digitale e le carte di gioco devono essere memorizzate nel seguente luogo: <code>ux0:app/TITLE_ID</code></li>
 	<li>I contenuti aggiuntivi devono essere memorizzati nella posizione seguente: <code>ux0:addcont/TITLE_ID/DLC_FOLDER</code>le relative licenze devono essere copiate <code>ux0:license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif</code>.</li>
 	<li>Gli aggiornamenti di gioco devono essere conservati al seguente indirizzo: <code>ux0:patch/TITLE_ID</code>.</li>
</ul>
Aprire VitaShell (versione 1.6 o successiva) e premere △ nella <code>home</code>sezione di VitaShell e scegliere <code>Refresh livearea</code>.
Questo innescherà l'installazione se i file sono stati inseriti correttamente e le licenze all'interno dei <code>work.bin</code>file sono valide.
<h2><a id="user-content-overview" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#overview" aria-hidden="true"></a>Panoramica</h2>
Se si decide di memorizzare il contenuto del gioco sul computer, si consiglia di utilizzare la stessa struttura <code>ux0:</code>come illustrato di seguito:
<pre><code>├───addcont
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
</code></pre>
<h2><a id="user-content-source-code" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#source-code" aria-hidden="true"></a>Codice sorgente</h2>
Il codice sorgente si trova all'interno della <code>src</code>directory ed è sotto licenza <code>GPLv3</code>.
<h2><a id="user-content-troubleshooting" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#troubleshooting" aria-hidden="true"></a>Risoluzione dei problemi</h2>
<ul>
 	<li>"Ottengo un <code>C1-2758-2</code>errore quando si tenta di eseguire un gioco / applicazione" - Il tuo gioco non è stato copiato correttamente e almeno uno dei file è danneggiato, si prega di ripeterlo e riprovare.</li>
 	<li>" <code>C1-6703-6</code>Ottengo un errore quando si tenta di eseguire un gioco / applicazione" - Esegui NoNpDrm da un Devkit / Testkit (PDEL / PTEL) questi dispositivi non sono attualmente supportati.</li>
 	<li>"Ottengo un <code>C0-9250-6</code>errore quando si tenta di eseguire un gioco / applicazione" - Il <code>nonpdrm.skprx</code>modulo non viene caricato, assicurarsi che il percorso al modulo sia scritto <code>ur0:tai/config.txt</code>o <code>ux0:tai/config.txt</code>se esiste più avanti sul dispositivo.</li>
 	<li>"Ottengo un <code>NP-6182-7</code>errore quando si tenta di eseguire un gioco / applicazione" - Questo errore si è verificato solo una volta durante il nostro test durante il tentativo di eseguire un'applicazione temporanea di PlayStation Plus scaduta, tentando di eseguire il gioco ancora una volta risolto il problema, non siamo mai riusciti a riprodurre questo errore, se riesci a riprodurre in modo coerente questo problema, apri un problema su github.</li>
 	<li>"Il mio gioco / applicazione viene visualizzato come versione di prova nella livearea". Ciò accade perché hai copiato un gioco / un'applicazione con una modalità di prova senza o con un invalid / corrotto <code>work.bin</code>.</li>
 	<li>"In qualche modo ho messo l'installazione, come posso reinstallare un gioco?" - È possibile eliminare la licenza (falsa) <code>ux0:license/app/TITLE_ID</code>e utilizzare l'opzione di aggiornamento in VitaShell.</li>
</ul>
<h2><a id="user-content-donation" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#donation" aria-hidden="true"></a>Donazione</h2>
Tutto il mio lavoro è volontario e non profit, tuttavia puoi sostenere il mio lavoro facendo una piccola donazione - non importa quanto piccola, sarei molto grato! Basta prestare attenzione a quello che mi scrivi nel messaggio;)
<a href="https://www.paypal.me/PSVitaTheFloW">Donation Link</a>
<h2><a id="user-content-special-thanks" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#special-thanks" aria-hidden="true"></a>Ringraziamenti speciali</h2>
<ul>
 	<li>Grazie alla molecola di squadra per HENkaku e grazie a <a href="https://twitter.com/yifanlu">yifanlu</a> per taiHEN</li>
 	<li>Grazie a <a href="https://twitter.com/Mathieulh">Mathieulh</a> per il test beta e mi ha aiutato a scrivere questo readme</li>
</ul>

