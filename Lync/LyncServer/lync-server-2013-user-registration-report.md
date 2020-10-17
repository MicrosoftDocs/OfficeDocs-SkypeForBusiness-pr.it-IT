---
title: "Lync Server 2013: rapporto di registrazione dell'utente"
description: 'Lync Server 2013: rapporto di registrazione degli utenti.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7adb8ef7e94a24f0fd088f12e009fc9d63f3be9d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569752"
---
# <a name="user-registration-report-in-lync-server-2013"></a>Rapporto di registrazione degli utenti in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-21_

Il rapporto registrazione utenti fornisce una panoramica delle attività di accesso degli utenti, in particolare informazioni sul numero di utenti che hanno effettuato l'accesso a Microsoft Lync Server 2013 nel corso di un periodo di tempo specificato (ogni ora, giornaliero, settimanale e mensile). Tenere presente che il report indica solo il numero di utenti connessi. Non indica *quali* utenti hanno effettuato l'accesso. I rapporti di monitoraggio non forniscono informazioni sugli utenti specifici che utilizzano Lync Server 2013 (e quali no). Tuttavia, è possibile ottenere una stima approssimativa delle informazioni degli utenti utilizzando il rapporto attività utente.

Quando si forniscono informazioni sugli accessi degli utenti, il rapporto di registrazione degli utenti disegna due distinzioni importanti. In primo luogo, interrompe gli accessi in due categorie principali: gli accessi interni e gli accessi esterni. Gli accessi interni rappresentano gli utenti che hanno effettuato l'accesso dall'interno del firewall dell'organizzazione, ovvero durante la connessione alla rete aziendale. Gli accessi esterni rappresentano gli utenti che si sono connessi dall'esterno del firewall tramite un server perimetrale (ad esempio, un utente che ha effettuato l'accesso da un Internet Café conta come un account esterno). Se è necessario sapere quanti utenti accedono dall'esterno del firewall, il rapporto registrazione utenti può fornire queste informazioni.

Inoltre, il rapporto registrazione utenti annota il numero di utenti *attivi* presenti nel corso di un determinato periodo. Un utente attivo è un utente che ha preso parte a una sessione di messaggistica istantanea, ha partecipato a una riunione di Lync, ha effettuato o ha ricevuto una chiamata telefonica oppure ha utilizzato Lync Server in altro modo durante tale periodo di tempo. Differisce da un utente che ha effettuato l'accesso, ma non si è mai avvalso effettivamente del sistema.

<div>

## <a name="accessing-the-user-registration-report"></a>Accesso al rapporto registrazione utenti

Il rapporto registrazione utenti è accessibile solo dalla home page Relazioni monitoraggio e non è collegato ad altri rapporti.

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>Utilizzo ottimale del rapporto registrazione utenti

Dopo aver distribuito Lync Server una domanda comune è la seguente: come è possibile sapere se gli utenti utilizzano effettivamente questa nuova tecnologia? Sebbene presenti qualche limitazione, il rapporto registrazione utenti può contribuire a fornire una risposta al riguardo. Per determinare se gli utenti utilizzano o meno Lync Server, è necessario eseguire due operazioni. Innanzitutto, occorre acquisire il valore metrico degli utenti con accesso univoco dal rapporto registrazione utenti. Questo valore indica il numero di utenti distinti connessi a Lync Server.

In base al confronto, la metrica totale degli accessi indica il numero totale di volte in cui tutti gli utenti hanno effettuato l'accesso a Lync Server. Si supponga, ad esempio, che Ken si sia connesso a Lync Server cinque volte diverse in un solo giorno. In tal caso, Ken remario conta come cinque sessioni di accesso separate per la metrica totale degli accessi, ma un solo utente di accesso per la metrica degli utenti di accesso univoco. Analogamente, non è raro che un utente acceda da più dispositivi o più posizioni. Ad esempio, un utente può accedere utilizzando il suo computer desktop, il suo computer portatile e può disporre di un telefono IP che accede automaticamente a Lync Server. In questo esempio, è presente un utente univoco con tre accessi.

Per spiegare ulteriormente la differenza tra accessi totali e accessi univoci, osservare gli accessi relativi a uno specifico periodo nella tabella seguente.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Utente</th>
<th>Ora accesso</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Davide Garghentini</p></td>
<td><p>07/07/2012 08.45</p></td>
</tr>
<tr class="even">
<td><p>Davide Garghentini</p></td>
<td><p>07/07/2012 08.46</p></td>
</tr>
<tr class="odd">
<td><p>Luisa Cazzaniga</p></td>
<td><p>07/07/2012 09.17</p></td>
</tr>
<tr class="even">
<td><p>Davide Garghentini</p></td>
<td><p>07/07/2012 09.22</p></td>
</tr>
<tr class="odd">
<td><p>Luisa Cazzaniga</p></td>
<td><p>07/07/2012 09.31</p></td>
</tr>
</tbody>
</table>


Sebbene complessivamente vengano indicati cinque accessi, vi sono in realtà solo due utenti con accesso univoco: Davide Garghentini, che si è connesso tre volte, e Luisa Cazzaniga, che ha effettuato l'accesso due volte. Questa è la differenza tra accessi e utenti con accesso univoco.

Oltre a conoscere il numero di accessi univoci, è necessario conoscere il numero totale di utenti che sono stati abilitati per Lync Server. Tale valore può essere recuperato aprendo Lync Server 2013 Management Shell ed eseguendo il comando di Windows PowerShell seguente:

    (Get-CsUser).Count

Se il comando precedente restituisce un valore pari a 1.236 e la metrica degli utenti di accesso univoco restituisce un valore medio di 667, che indica che un po' più della metà degli utenti abilitati per Lync si sta effettivamente accedendo al sistema ogni giorno, ovvero 667 diviso per 1.236, che è approssimativamente 54%.

<div>


> [!WARNING]  
> Tenere presente che le metriche di accesso registrano gli utenti effettivamente connessi durante il periodo di tempo specificato. Non tengono conto degli utenti già connessi al sistema. Ad esempio, se la metrica degli utenti di accesso univoco Visualizza 667 accessi e sono presenti 1.236 utenti, questo suggerisce che circa la metà degli utenti accedono al sistema. Tuttavia, si supponga che 300 utenti siano già connessi al sistema al momento in cui si è iniziato a controllare i dati di accesso. Questo significa che si è effettivamente avuto quasi 1.000 utenti connessi a Lync Server, il che significherebbe che più vicino al 80% degli utenti sono stati connessi.



</div>

È inoltre opportuno confrontare i valori delle metriche Utenti con accesso univoco e Utenti attivi univoci. La metrica Unique Active users indica il numero di utenti univoci che hanno effettivamente utilizzato Lync Server: hanno effettuato una chiamata telefonica, hanno partecipato a una riunione di Lync o sono stati presenti in una sessione di messaggistica istantanea. Si tratta di informazioni utili, perché Microsoft Lync 2013 può essere configurato per l'avvio automatico ogni volta che un utente avvia Windows. Per questo motivo, potrebbe essere presente un numero elevato di utenti che accedono automaticamente a Lync quando eseguono l'accesso a Windows ogni giorno, ma non utilizzano mai Lync Server in quel periodo di tempo.

La metrica degli utenti attivi univoci fornisce anche dati più significativi in un'organizzazione in cui gli utenti in genere non disattivano le finestre alla fine della giornata. Al contrario, bloccano semplicemente i propri computer e lasciano l'esecuzione di Windows e Lync. In una situazione simile, si potrebbe finire con pochissimi accessi al giorno perché gli utenti hanno effettuato l'accesso alcuni giorni fa e non sono mai disconnessi. Tuttavia, gli utenti attivi univoci indicano se gli utenti utilizzano attivamente Lync o un altro client di Lync Server.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Ad esempio, il rapporto di registrazione degli utenti consente di visualizzare i dati per tutti i pool di registrazione e i server perimetrali o per visualizzare i dati per un singolo pool. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In tal caso, le registrazioni vengono raggruppate in base all'ora, al giorno, alla settimana o al mese.

Nella tabella seguente sono riportati i filtri che è possibile utilizzare con il rapporto registrazione utenti.

### <a name="user-registration-report-filters"></a>Filtri per il rapporto registrazione utenti

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di fine come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervallo</strong></p></td>
<td><p>Selezionare uno dei seguenti:</p>
<ul>
<li><p>Orario (è possibile visualizzare un massimo di 25 ore)</p></li>
<li><p>Giornaliero (è possibile visualizzare un massimo di 31 giorni)</p></li>
<li><p>Settimanale (è possibile visualizzare un massimo di 12 settimane)</p></li>
<li><p>Mensile (è possibile visualizzare un massimo di 12 mesi)</p></li>
</ul>
<p>Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori, a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo Giornaliero con 07/07/2012 come data di inizio e 28/02/2012 come data di fine, verranno visualizzati i dati dalla mezzanotte del 7 agosto 2012 alla mezzanotte del 7 settembre 2012, ovvero i dati per un totale di 31 giorni.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure selezionare <strong>[Tutto]</strong> per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente vengono riportate le informazioni fornite nel rapporto registrazione utenti.

### <a name="user-registration-report-metrics"></a>Metrica del rapporto registrazione utenti

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Elemento utilizzabile per eseguire l'ordinamento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Orario</strong></p>
<p><strong>Giornaliero</strong></p>
<p><strong>Settimanale</strong></p>
<p><strong>Mensile</strong></p></td>
<td><p>No</p></td>
<td><p>Indica l'intervallo di tempo selezionato nella barra degli strumenti per i filtri. Quando applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate a esso relative. Ad esempio, se si utilizza l'intervallo Giornaliero e si fa clic su 07/07/2012, l'attività di registrazione degli utenti relativa a tale data verrà visualizzata suddivisa per ore.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale accessi</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni di accesso che hanno avuto esito positivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Accessi interni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di accessi nella rete interna.</p></td>
</tr>
<tr class="even">
<td><p><strong>Accessi esterni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di accessi dal di fuori della rete interna, utilizzando il server perimetrale.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Utenti con accesso univoco</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di utenti che hanno avuto almeno una sessione di accesso. Un utente che ha avuto più sessioni di accesso viene considerato come un unico utente, al pari di una persona che ha avuto una sola sessione di accesso.</p></td>
</tr>
<tr class="even">
<td><p><strong>Utenti attivi univoci</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di utenti che sono stati coinvolti in una sessione peer-to-peer o di conferenza. Un utente che ha avuto più sessioni viene considerato come un unico utente, al pari di una persona che ha avuto una sola sessione.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

