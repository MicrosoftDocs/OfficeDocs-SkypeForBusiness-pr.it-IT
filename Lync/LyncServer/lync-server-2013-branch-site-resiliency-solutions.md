---
title: 'Lync Server 2013: Soluzioni di resilienza dei siti di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce14328aed7ae4769d2f2aff18edb9c6135fe025
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Soluzioni di resilienza dei siti di succursale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-12-10_

Sono evidenti i vantaggi per fornire alla propria organizzazione la resilienza del sito di succursale. In particolare, se si perde la connessione al sito centrale, gli utenti del sito di succursale continueranno ad avere il servizio VoIP aziendale e la segreteria telefonica (se si configurano le impostazioni di reinstradamento della segreteria telefonica; per informazioni dettagliate, vedere [requisiti di resilienza dei siti secondari per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)). Tuttavia, per i siti con meno di 25 utenti, una soluzione di resilienza potrebbe non fornire un rendimento sufficiente per gli investimenti.

Se si decide di specificare la resilienza del sito filiale, sono disponibili tre opzioni. La tabella seguente può aiutare a determinare l'opzione migliore per l'organizzazione.

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Se si...</th>
<th>Ti consigliamo di usare un...</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ospita tra gli utenti di 25 e 1000 nel sito di succursale e se il ritorno sugli investimenti non supporta una distribuzione completa o il supporto amministrativo locale non è disponibile</p></td>
<td><p>Survivable Branch Appliance</p>
<p>Survivable Branch Appliance è un server blade standard del settore con un registrar di Lync Server e Mediation Server in uso in Windows Server 2008 R2. Il Survivable Branch Appliance contiene anche un gateway PSTN (Public Switched Telephone Network). I dispositivi di terze parti qualificati (sviluppati da Microsoft Partners nel programma di qualifica/certificazione di Survivable Branch Appliance (SBA)) garantiscono una connessione PSTN continua in caso di errore WAN, ma questo approccio non offre una presenza resiliente e servizi di conferenza, perché queste funzionalità dipendono dai server front-end del sito centrale.</p>
<p>Per informazioni dettagliate sugli elettrodomestici Survivable Branch &quot;, vedere dettagli di Survivable&quot; Branch Appliance, più avanti in questo argomento.</p>
<p><strong>Nota:</strong> Se si decide di usare anche un trunk SIP con l'appliance Survivable Branch, contattare il fornitore Survivable Branch Appliance per conoscere il provider di servizi migliore per l'organizzazione.</p></td>
</tr>
<tr class="even">
<td><p>Host tra gli utenti di 1000 e 2000 nel sito di succursale, non ha una connessione WAN resiliente e ha addestrato gli amministratori di Lync Server disponibili</p></td>
<td><p>Survivable Branch Server o due Survivable Branch Appliance.</p>
<p>Survivable Branch Server è una riunione di Windows Server requisiti hardware specificati in cui è installato Lync Server registrar e il software Mediation Server. Deve essere collegato a un gateway PSTN o a un trunk SIP a un provider di servizi telefonici.</p>
<p>Per informazioni dettagliate sui Survivable Branch Server, &quot;vedere dettagli di Survivable Branch&quot; server, più avanti in questo argomento.</p></td>
</tr>
<tr class="odd">
<td><p>Se sono necessarie funzionalità di presenza e conferenze oltre alle funzionalità vocali per un massimo di 5000 utenti e sono stati addestrati gli amministratori di Lync Server disponibili</p></td>
<td><p>Distribuire come sito centrale con un server Standard Edition anziché come sito di succursale.</p>
<p>Una distribuzione su vasta scala di Lync Server offre una connessione PSTN continua e una presenza resiliente e conferenze in caso di errore WAN.</p>
<p>Per informazioni dettagliate sulla preparazione di questa soluzione, vedere <a href="lync-server-2013-planning-for-your-organization.md">pianificazione dell'organizzazione per Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">determinare i requisiti di sistema per Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">determinare i requisiti di infrastruttura per Lync Server 2013</a>e altre sezioni pertinenti della documentazione relativa alla pianificazione.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>Topologie di resilienza

La figura seguente mostra le topologie consigliate per la resilienza del sito di succursale.

**Opzioni di resilienza del sito filiale**

![](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Opzioni di") resilienza del ramo vocale

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Dettagli Survivable Branch Appliance

Il Survivable Branch Appliance di Lync Server include i componenti seguenti:

  - Registrar per l'autenticazione utente, la registrazione e il routing delle chiamate

  - Un Mediation Server per la gestione della segnalazione tra il registrar e un gateway PSTN

  - Gateway PSTN per il routing delle chiamate alla rete PSTN come trasporto di fallback in caso di interruzioni WAN

  - SQL Server Express per l'archiviazione dei dati dell'utente locale

Il Survivable Branch Appliance include anche trunk PSTN, porte analogiche e una scheda Ethernet.

Se la connessione WAN del sito della filiale a un sito centrale diventa non disponibile, gli utenti di Branch interni continuano a essere registrati presso il registrar Survivable Branch Appliance e a ottenere il servizio vocale ininterrotto usando la connessione Survivable Branch Appliance alla rete PSTN. Gli utenti del sito della filiale che si connettono da una sede o da altre posizioni remote potranno eseguire la registrazione presso un server di registrazione in un sito centrale se il collegamento WAN al sito della filiale non è disponibile. Questi utenti avranno la funzionalità di comunicazioni unificate completa, con l'unica eccezione che le chiamate in ingresso al sito della filiale andranno alla segreteria telefonica. Quando la connessione WAN diventa disponibile, la funzionalità completa deve essere ripristinata agli utenti del sito succursale. Né il failover per il Survivable Branch Appliance né il ripristino del servizio richiedono la presenza di un amministratore IT.

Lync Server supporta fino a due Survivable Branch Appliance in un sito di succursale.

<div>


> [!NOTE]  
> Gli utenti ospitati in un dispositivo Survivable Branch di Lync Server non riescono a creare nuove chat room o a visualizzare la scheda della sala per le camere esistenti.



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Panoramica della distribuzione Survivable Branch Appliance

Il Survivable Branch Appliance è prodotto da produttori di apparecchiature originali in collaborazione con Microsoft e distribuito per loro conto da rivenditori a valore aggiunto. Questa distribuzione deve essere eseguita solo dopo la distribuzione di Lync Server presso il sito centrale, una connessione WAN al sito di succursale e gli utenti del sito di succursale sono abilitati per VoIP aziendale.

Per informazioni dettagliate su queste fasi, vedere [distribuzione di un Survivable Branch Appliance o server con Lync server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) nella documentazione relativa alla distribuzione.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Passaggi</th>
<th>Diritti utente</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurare servizi di dominio Active Directory per Survivable Branch Appliance</p></td>
<td><p><strong>Nel sito centrale:</strong></p>
<ol>
<li><p>Creare un account utente di dominio (o un'identità aziendale) per il tecnico che installerà e attiverà il Survivable Branch Appliance presso il sito della filiale.</p></li>
<li><p>Creare un account del computer (con il nome di dominio completo applicabile) per Survivable Branch Appliance in servizi di dominio Active Directory.</p></li>
<li><p>In Generatore di topologie creare e pubblicare l'appliance Survivable Branch.</p></li>
</ol></td>
<td><p>L'account utente tecnico deve essere un membro di RTCUniversalSBATechnicians. Il Survivable Branch Appliance deve appartenere al gruppo RTCSBAUniversalServices, che si verifica automaticamente quando si usa generatore di topologie.</p></td>
</tr>
<tr class="even">
<td><p>Installare e attivare Survivable Branch Appliance.</p></td>
<td><p><strong>Nel sito della filiale:</strong></p>
<ol>
<li><p>Connettere il Survivable Branch Appliance a una porta Ethernet e a una porta PSTN.</p></li>
<li><p>Avviare Survivable Branch Appliance.</p></li>
<li><p>Aggiungere il Survivable Branch Appliance al dominio usando l'account utente di dominio creato per Survivable Branch Appliance nel sito centrale. Impostare il nome di dominio completo e l'indirizzo IP in base al nome di dominio completo creato nell'account del computer.</p></li>
<li><p>Configurare l'appliance Survivable Branch utilizzando l'interfaccia utente OEM.</p></li>
<li><p>Testare la connettività PSTN.</p></li>
</ol></td>
<td><p>L'account utente tecnico deve essere un membro di RTCUniversalSBATechnicians.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Dettagli Survivable Branch Server

In Generatore di topologia creare il sito della filiale, aggiungere il Survivable Branch Server a tale sito e quindi eseguire la distribuzione guidata di Lync Server nel computer in cui si vuole installare il ruolo.

</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

