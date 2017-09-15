<h1>TRADUZIONE IN ITALIANO</h1>
----------------------------------------------------------------------

<h1>Plugin NoNpDrm di TheFloW</h1>
<h2><a id="user-content-features" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#features" aria-hidden="true"></a>Caratteristiche</h2>
<ul>
 	<li>Esporta le chiavi di licenza dei contenuti PS Vita come licenze false.</li>
 	<li>Bypasserà la scadenza del PlayStation Plus e di altre licenze temporanee.</li>
 	<li>Consente di eseguire versioni di prova come versioni complete.</li>
 	<li>Consente la condivisione di contenuti crittografati PFS (giochi non decodificati non modificati) su più account e dispositivi PS Vita utilizzando file di licenza generati.</li>
 	<li>I giochi importati si comportano come giochi acquistati e consentono l'utilizzo di aggiornamenti di gioco senza alcun problema scaricati dalla Sony Interactive Entertainment Network (PlayStation Network) a condizione che questi aggiornamenti siano eseguiti su firmware 3.60 e inferiore.</li>
 	<li>I giochi possono anche essere spogliati della loro crittografia PFS utilizzando strumenti come vitamin, proprio come qualsiasi altro gioco acquistato.</li>
 	<li>Utilizzo di applicazioni acquistate su dispositivi disattivati.</li>
</ul>
In poche parole, questo plugin ti permette di ignorare la protezione DRM su qualsiasi contenuto PS Vita.
<h3><a id="user-content-this-software-will-not" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#this-software-will-not" aria-hidden="true"></a>Questo software NON</h3>
<ul>
 	<li>Consente modifiche ai tuoi giochi / applicazioni.</li>
 	<li>Funziona con i contenuti decodificati PFS (come i giochi scaricati utilizzando applicazioni come Vitamin o MaiDumpTool).</li>
 	<li>Consente l'esecuzione di applicazioni / utilizzo di contenuti senza una licenza valida o un file di licenza falsa.</li>
 	<li>Funziona con i titoli PlayStation Portable o PlayStation 1 (se volete giocare a tali titoli, potresti guardare il <a href="https://github.com/TheOfficialFloW/Adrenaline/releases">software Adrenaline</a> ).</li>
 	<li>Funziona con applicazioni che eseguono solo il firmware 3.61 o successivo.</li>
</ul>
<h2><a id="user-content-legal-disclaimer" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#legal-disclaimer" aria-hidden="true"></a>Disclaimer legale</h2>
<ul>
 	<li>La rimozione e la distribuzione di contenuti DRM e / o l'elusione di meccanismi di protezione della copia per qualsiasi altro scopo che l'archiviazione / la conservazione dei giochi che possiedono licenze è illegale.</li>
 	<li>Questo software è destinato ad essere strettamente riservato per il tuo uso personale <strong>PERSONAL</strong> .</li>
 	<li>L'autore non si assume alcuna responsabilità per le tue azioni utilizzando questo software.</li>
</ul>
<h2><a id="user-content-software-requirements" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#software-requirements" aria-hidden="true"></a>Requisiti software</h2>
Questo software funzionerà solo su PlayStation Vita, PlayStation Vita TV, dispositivi PlayStation TV in esecuzione su firmware 3.60, il framework taiHEN e HENkaku devono essere in esecuzione sul tuo dispositivo, per ulteriori informazioni si prega di collegarsi a <a href="https://henkaku.xyz/">https://henkaku.xyz/</a>
Per tutti le possibilità descritte di seguito, è necessario utilizzare <a href="https://github.com/TheOfficialFloW/VitaShell/releases">VitaShell v1.6</a> o superiore per trasferimenti più veloci.
VitaShell ti permette di montare la scheda di memoria o la scheda di gioco di PS Vita sul tuo PC tramite USB.
Su un dispositivo PSTV, è possibile montare un'unità flash USB e copiare i file su <code>uma0:</code>.
<h2><a id="user-content-installation" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#installation" aria-hidden="true"></a>Installazione</h2>
Scaricare l'ultima <a href="https://github.com/TheOfficialFloW/NoNpDrm/releases">nonpdrm.skprx</a> , copiarla <code>ux0:tai</code>e modificare il <code>ux0:tai/config.txt</code>file per aggiungere il percorso al modulo <code>*KERNEL</code>come segue
<pre><code>*KERNEL
ux0:tai/nonpdrm.skprx
</code></pre>
Se sai cosa stai facendo, puoi cambiare questo percorso in una posizione arbitraria finché corrisponda alla posizione esatta del modulo. Puoi anche modificare l' <code>ur0:tai/config.txt</code>opzione supponendo di non avere un file config.txt all'interno della cartella <code>ux0:tai/</code>
<h2><a id="user-content-creating-the-fake-license" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#creating-the-fake-license" aria-hidden="true"></a>Creazione della licenza falsa</h2>
Per generare un file di licenza falsa contenente la chiave rif. E' necessario innanzitutto avviare l'applicazione con il plug-in NoNpDrm abilitato.
Le licenze false per le applicazioni saranno quindi memorizzate in
<ul>
 	<li><code>ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif</code></li>
 	<li><code>ux0:nonpdrm/license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif</code> (per ulteriori contenuti)</li>
</ul>
<h2><a id="user-content-sharing-digital-applications" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#sharing-digital-applications" aria-hidden="true"></a>Condivisione di applicazioni digitali</h2>
<ul>
 	<li>Se si desidera utilizzare l'applicazione sullo stesso dispositivo, ma su un altro account, è sufficiente copiare la licenza falsa <code>6488b73b912a753a492e2714e9b38bc7.rif</code>a <code>ux0:license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif</code>.</li>
 	<li>Se si desidera utilizzare l'applicazione su un dispositivo diverso, trasferire il contenuto <code>ux0:app/TITLE_ID</code>sul PC e copiare il <code>ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif</code>file di licenza falso in quanto <code>TITLE_ID/sce_sys/package/work.bin</code> <strong>è necessario sovrascrivere l'originale work.bin</strong></li>
</ul>
<strong>Nota</strong> : sui giochi ottenuti tramite PlayStation Store, <code>work.bin</code>è legato all'account Sony Interactive Entertainment (noto anche come PlayStation Network) e contiene il tuo ID account. La licenza falsa tuttavia <strong>NON</strong> contiene informazioni personali.
<h2><a id="user-content-sharing-game-cards" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#sharing-game-cards" aria-hidden="true"></a>Condivisione delle cartucce di gioco</h2>
Trasferire la cartella <code>gro0:app/TITLE_ID</code> e il suo contenuto su <code>ux0:app/TITLE_ID</code>o sul computer e salvare la licenza falsa<code>ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif</code>come <code>TITLE_ID/sce_sys/package/work.bin</code>.

Per trasferimenti più veloci è possibile montare la Game Card su USB. A tale scopo, aprire VitaShell (vedere la sezione Requisiti software di questa documentazione), premere il pulsante START della PS Vita nel <code>Main settings</code>menu, selezionare <code>Game Card</code>opzione <code>USB device</code> e premere di nuovo il tasto START per chiudere la scheda impostazioni.
Ora collegare la tua PS Vita al computer tramite USB e premere il pulsante SELECT.

<strong>Nota</strong> : il montaggio delle schede di gioco tramite USB non funziona su dispositivi PlayStation TV o PlayStation Vita TV.
<h2><a id="user-content-sharing-additional-content" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#sharing-additional-content" aria-hidden="true"></a>Condivisione di contenuti aggiuntivi</h2>
Si può condividere qualsiasi contenuto addizionale su più dispositivi da <code>ux0:addcont/TITLE_ID/DLC_FOLDER</code>o, a cartucce di gioco selezionati, dalla cartella <code>grw0:addcont/TITLE_ID/DLC_FOLDER</code>
A tale scopo, copiare la licenza falsa <code>ux0:nonpdrm/license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif</code>a <code>ux0:license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif</code>.
<h2><a id="user-content-sharing-game-updates" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#sharing-game-updates" aria-hidden="true"></a>Condivisione di aggiornamenti di giochi</h2>
Mentre si può semplicemente copiare il contenuto <code>ux0:patch/TITLE_ID</code>o <code>grw0:patch/TITLE_ID</code>(in caso di titoli di carte selezionati), gli aggiornamenti di gioco possono essere scaricati e installati direttamente da PlayStation Network (a meno che l'aggiornamento più recente non sia compatibile con 3.60).
<h2><a id="user-content-installing-shared-applications" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#installing-shared-applications" aria-hidden="true"></a>Installazione di applicazioni condivise</h2>
<ul>
 	<li>L'applicazione digitale e le cartucce di gioco devono essere memorizzate nel seguente percorso: <code>ux0:app/TITLE_ID</code></li>
 	<li>I contenuti aggiuntivi devono essere memorizzati nella posizione seguente: <code>ux0:addcont/TITLE_ID/DLC_FOLDER</code>le relative licenze devono essere copiate <code>ux0:license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif</code>.</li>
 	<li>Gli aggiornamenti di gioco devono essere conservati al seguente indirizzo: <code>ux0:patch/TITLE_ID</code>.</li>
</ul>
Aprire VitaShell (versione 1.6 o successiva) e premere △ nella <code>home</code>sezione di VitaShell e scegliere <code>Refresh livearea</code>.
Questo innescherà l'installazione se i file sono stati inseriti correttamente e le licenze all'interno dei file <code>work.bin</code> valide.
<h2><a id="user-content-overview" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#overview" aria-hidden="true"></a>Panoramica</h2>
Se si decide di memorizzare il contenuto del gioco sul computer, si consiglia di utilizzare la stessa struttura <code>ux0:</code>come illustrato di seguito:
<pre><code>├───addcont
│   └───TITLE_ID
│   │   └───DLC_FOLDER
├───app
│   └───TITLE_ID
│   │   └───sce_sys
│   │       └───package
│   │           └───work.bin (copiare o sovrascrivere da ux0:nonpdrm/license/app/TITLE_ID/6488b73b912a753a492e2714e9b38bc7.rif)
├───license
│   └───addcont
│   │   └───TITLE_ID
│   │       └───DLC_FOLDER
│   │           └───6488b73b912a753a492e2714e9b38bc7.rif (copiato da ux0:nonpdrm/license/addcont/TITLE_ID/DLC_FOLDER/6488b73b912a753a492e2714e9b38bc7.rif)
├───patch
│   └───TITLE_ID
</code></pre>
<h2><a id="user-content-source-code" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#source-code" aria-hidden="true"></a>Codice sorgente</h2>
Il codice sorgente si trova all'interno della directory <code>src</code> ed è sotto licenza <code>GPLv3</code>.
<h2><a id="user-content-troubleshooting" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#troubleshooting" aria-hidden="true"></a>Risoluzione dei problemi</h2>
<ul>
 	<li>"Ottengo un errore <code>C1-2758-2</code> quando si tenta di eseguire un gioco / applicazione" - Il tuo gioco non è stato copiato correttamente e almeno uno dei file è danneggiato, si prega di ripeterlo e riprovare.</li>
 	<li>" <code>C1-6703-6</code>Ottengo un errore quando si tenta di eseguire un gioco / applicazione" - Esegui NoNpDrm da un Devkit / Testkit (PDEL / PTEL) questi dispositivi non sono attualmente supportati.</li>
 	<li>"Ottengo un errore <code>C0-9250-6</code>quando si tenta di eseguire un gioco / applicazione" - Il modulo <code>nonpdrm.skprx</code> non viene caricato, assicurarsi che il percorso al modulo sia scritto <code>ur0:tai/config.txt</code>o <code>ux0:tai/config.txt</code>se esiste più avanti sul dispositivo.</li>
 	<li>"Ottengo un errore <code>NP-6182-7</code> quando si tenta di eseguire un gioco / applicazione" - Questo errore si è verificato solo una volta durante il nostro test durante il tentativo di eseguire un'applicazione temporanea di PlayStation Plus scaduta, tentando di eseguire il gioco ancora una volta risolto il problema, non siamo mai riusciti a riprodurre questo errore, se riesci a riprodurre in modo coerente questo problema, apri un problema su github.</li>
 	<li>"Il mio gioco / applicazione viene visualizzato come versione di prova nel livearea". Ciò accade perché hai copiato un gioco / un'applicazione con una modalità di prova senza o con un invalid / corrotto <code>work.bin</code>.</li>
 	<li>"In qualche modo ho fermato l'installazione, come posso reinstallare un gioco?" - È possibile eliminare la licenza (falsa) <code>ux0:license/app/TITLE_ID</code>e utilizzare l'opzione di aggiornamento in VitaShell.</li>
</ul>
<h2><a id="user-content-donation" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#donation" aria-hidden="true"></a>Donazione</h2>
Tutto il mio lavoro è volontario e non profit, tuttavia puoi sostenere il mio lavoro facendo una piccola donazione - non importa quanto piccola, sarei molto grato! Basta prestare attenzione a quello che mi scrivi nel messaggio;)
<a href="https://www.paypal.me/PSVitaTheFloW">Donation Link</a>
<h2><a id="user-content-special-thanks" class="anchor" href="https://github.com/theheroGAC/NoNpDrm/blob/patch-1/readme.md#special-thanks" aria-hidden="true"></a>Ringraziamenti speciali</h2>
<ul>
 	<li>Grazie al Team Molecule per HENkaku e grazie a <a href="https://twitter.com/yifanlu">yifanlu</a> per taiHEN</li>
 	<li>Grazie a <a href="https://twitter.com/Mathieulh">Mathieulh</a> per il beta test e per aver aiutato me a scrivere questo readme</li>
  <li>Traduzione in italiano by theheroGAC</li>
</ul>
