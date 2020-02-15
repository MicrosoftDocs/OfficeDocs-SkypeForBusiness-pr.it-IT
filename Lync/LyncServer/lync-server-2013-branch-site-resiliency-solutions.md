---
title: 'Lync Server 2013: soluzioni di resilienza dei siti di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 019da9259cae95d019f954f275ed36a5f79174e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Soluzioni di resilienza dei siti di succursale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-12-10_

Esistono vantaggi evidenti per fornire la resilienza dei siti di succursale all'organizzazione. In particolare, se si perde la connessione al sito centrale, gli utenti del sito di succursale continueranno ad avere il servizio VoIP aziendale e la segreteria telefonica (se si configurano le impostazioni di reinstradamento della segreteria telefonica, vedere i [requisiti di resilienza dei siti di succursale per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)). Tuttavia, per i siti con meno di 25 utenti, una soluzione di resilienza potrebbe non fornire un rendimento sufficiente sull'investimento.

Se si decide di garantire la resilienza dei siti di succursale, sono disponibili tre opzioni. Per scegliere l'opzione più adatta all'organizzazione, utilizzare come riferimento la tabella riportata di seguito.

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Se...</th>
<th>È consigliabile utilizzare un…</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nel sito di succursale vengono ospitati dai 25 ai 1000 utenti e l'utile sugli investimenti non consente una distribuzione completa oppure non è disponibile supporto amministrativo locale</p></td>
<td><p>Survivable Branch Appliance</p>
<p>Survivable Branch Appliance è un server blade standard del settore con un servizio di registrazione di Lync Server e Mediation Server in esecuzione su Windows Server 2008 R2. Survivable Branch Appliance contiene anche un gateway PSTN (Public Switched Telephone Network). I dispositivi di terze parti qualificati, sviluppati da partner Microsoft nell'ambito del programma di qualifica e certificazione degli SBA (Survivable Branch Appliance), forniscono una connessione PSTN continua in caso di problemi della rete WAN, ma non garantiscono un servizio di presenza o conferenza resiliente perché tali funzionalità dipendono dai Front End Server nel sito centrale.</p>
<p>Per informazioni dettagliate sugli apparecchi Survivable Branch, &quot;vedere Survivable Branch Appliance Details,&quot; più avanti in questo argomento.</p>
<p><strong>Nota:</strong> Se si decide di utilizzare anche un trunk SIP con il Survivable Branch Appliance, contattare il fornitore di Survivable Branch Appliance per informazioni su quale provider di servizi è più adatto per l'organizzazione.</p></td>
</tr>
<tr class="even">
<td><p>Host compreso tra 1000 e 2000 utenti nel sito di succursale, manca una connessione WAN resiliente e sono disponibili amministratori di Lync Server addestrati</p></td>
<td><p>Survivable Branch Server o due Survivable Branch Appliance.</p>
<p>Survivable Branch Server è una riunione di Windows Server requisiti hardware specificati in cui è installato Lync Server registrar e software Mediation Server. Deve connettersi a un gateway PSTN o a un trunk SIP verso un provider di servizi telefonici.</p>
<p>Per informazioni dettagliate sui Survivable Branch Server, &quot;vedere Survivable Branch Server Details,&quot; più avanti in questo argomento.</p></td>
</tr>
<tr class="odd">
<td><p>Se sono necessarie funzionalità di conferenza e presenza oltre alle funzionalità vocali per un massimo di 5000 utenti e sono disponibili amministratori di Lync Server addestrati</p></td>
<td><p>Eseguire la distribuzione come sito centrale con un server Standard Edition anziché come sito di succursale.</p>
<p>Una distribuzione su vasta scala di Lync Server fornisce una connessione PSTN continua e una presenza resiliente e le conferenze in caso di errore WAN.</p>
<p>Per informazioni dettagliate sulla preparazione per questa soluzione, vedere <a href="lync-server-2013-planning-for-your-organization.md">Organization Planning for Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">determinare i requisiti di sistema per Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">determinare i requisiti dell'infrastruttura per Lync Server 2013</a>e altre sezioni rilevanti della documentazione relativa alla pianificazione.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>Topologie di resilienza

Nella figura seguente vengono illustrate le topologie consigliate per la resilienza dei siti di succursale.

**Opzioni di resilienza per i siti di succursale**

![Opzioni di resilienza del ramo vocale](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Opzioni di resilienza del ramo vocale")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Dettagli relativi al Survivable Branch Appliance

Il Survivable Branch Appliance di Lync Server include i componenti seguenti:

  - Una funzione di registrazione per l'autenticazione degli utenti, la registrazione e il routing delle chiamate

  - Un Mediation Server per la gestione dei segnali tra la funzione di registrazione e un gateway PSTN

  - Un gateway PSTN per il routing delle chiamate alla rete PSTN come trasporto di fallback in caso di problemi della rete WAN

  - SQL Server Express per l'archiviazione dei dati degli utenti in locale

Survivable Branch Appliance include anche trunk PSTN, porte analogiche e una scheda Ethernet.

Se la connessione WAN del sito di succursale a un sito centrale non è disponibile, gli utenti di Branch interni continuano a essere registrati con Survivable Branch Appliance registrar e a ottenere il servizio vocale ininterrotto tramite la connessione Survivable Branch Appliance alla rete PSTN. Gli utenti del sito di succursale che si connettono da casa o da altre postazioni remote saranno in grado di registrarsi in un server di registrazione presso un sito centrale in caso di non disponibilità del collegamento WAN al sito di succursale. Tali utenti disporranno della funzionalità di comunicazione unificata completa, con l'unica eccezione che le chiamate in ingresso nel sito di succursale verranno indirizzate alla segreteria telefonica. Quando la connessione WAN torna disponibile, per gli utenti del sito di succursale viene ripristinata la funzionalità completa. Né il failover per il Survivable Branch Appliance né il ripristino del servizio richiedono la presenza di un amministratore IT.

Lync Server supporta fino a due Survivable Branch Appliance in un sito di succursale.

<div>


> [!NOTE]  
> Gli utenti ospitati in un Survivable Branch Appliance di Lync Server non sono in grado di creare nuove chat room o di visualizzare la scheda sala per le sale esistenti.



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Panoramica della distribuzione del Survivable Branch Appliance

Il Survivable Branch Appliance è prodotto dai produttori di apparecchiature originali in partnership con Microsoft e distribuito per conto di rivenditori a valore aggiunto. Questa distribuzione deve essere eseguita solo dopo la distribuzione di Lync Server nel sito centrale, una connessione WAN al sito di succursale e gli utenti dei siti di succursale sono abilitati per VoIP aziendale.

Per informazioni dettagliate su queste fasi, vedere [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) nella documentazione relativa alla distribuzione.


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
<td><p>Configurare servizi di dominio Active Directory per il Survivable Branch Appliance</p></td>
<td><p><strong>Nel sito centrale:</strong></p>
<ol>
<li><p>Creare un account utente di dominio (o identità aziendale) per il tecnico che installerà e attiverà il Survivable Branch Appliance nel sito di succursale.</p></li>
<li><p>Creare un account computer (con il nome di dominio completo (FQDN) applicabile) per Survivable Branch Appliance in servizi di dominio Active Directory.</p></li>
<li><p>In Generatore di topologie creare e pubblicare il Survivable Branch Appliance.</p></li>
</ol></td>
<td><p>L'account utente del tecnico deve essere membro del gruppo RTCUniversalSBATechnicians. Il Survivable Branch Appliance deve appartenere al gruppo RTCSBAUniversalServices, che si verifica automaticamente quando si utilizza il generatore di topologie.</p></td>
</tr>
<tr class="even">
<td><p>Installare e attivare il Survivable Branch Appliance.</p></td>
<td><p><strong>Nel sito di succursale:</strong></p>
<ol>
<li><p>Connettere il Survivable Branch Appliance a una porta Ethernet e a una porta PSTN.</p></li>
<li><p>Avviare Survivable Branch Appliance.</p></li>
<li><p>Aggiungere il Survivable Branch Appliance al dominio, utilizzando l'account utente di dominio creato per il Survivable Branch Appliance nel sito centrale. Impostare l'FQDN e l'indirizzo IP in modo che corrispondano all'FQDN creato nell'account computer.</p></li>
<li><p>Configurare il Survivable Branch Appliance utilizzando l'interfaccia utente OEM.</p></li>
<li><p>Verificare la connettività PSTN.</p></li>
</ol></td>
<td><p>L'account utente del tecnico deve essere membro del gruppo RTCUniversalSBATechnicians.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Dettagli relativi al Survivable Branch Server

In Generatore di topologie creare il sito di succursale, aggiungere il Survivable Branch Server a quel sito, quindi eseguire la distribuzione guidata di Lync Server nel computer in cui si desidera installare il ruolo.

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

