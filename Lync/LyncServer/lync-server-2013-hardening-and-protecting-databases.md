---
title: 'Lync Server 2013: Protezione avanzata e sicurezza dei database'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e02a5fd0f90367f23e7b0fb314f037f7b31e45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>Protezione avanzata e sicurezza dei database di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-12-05_

Microsoft Lync Server 2013 dipende anche da database di SQL Server per l'archiviazione di informazioni utente, stato conferenza, dati di archiviazione e record dettagli chiamata (CDRs). È possibile massimizzare la disponibilità dei dati di Lync Server 2013 nei database back-end di Lync Server, partizionando i dati dell'applicazione in modo da migliorare la tolleranza degli errori e semplificando la risoluzione dei problemi. Per raggiungere questi obiettivi, partizionare i dati dell'applicazione in base a:

  - **Uso delle procedure**   consigliate per il partizionamento dei server separare il sistema operativo, l'applicazione e i file di programma dai file di dati.

  - **Archiviazione dei file di log delle transazioni e dei file**   di database archiviare separatamente questi file per aumentare la tolleranza di errore e ottimizzare il ripristino e archiviarli in un disco o un volume crittografato.

  - **Uso**del cluster clustering dei server back-end per ottimizzare la disponibilità di sistema di Lync Server 2013.   

  - **Assicurarsi che tutti i backup dei dati siano crittografati e gestiti**   correttamente, i file multimediali persi, eliminati o smarriti possano rappresentare una minaccia significativa per la sicurezza dei dati per le distribuzioni di Lync Server 2013

In qualsiasi server Lync Server 2013 eccetto il server Standard Edition, l'istanza di SQL Server Express (istanza di RTCLOCAL) non è accessibile in remoto e non vengono create eccezioni del firewall locale, ad eccezione di SQL Server Express in un server Standard Edition. In un server Standard Edition, sia il database back-end che il Central Management store (CMS) sono configurati per l'accessibilità remota. Per indurire i database di SQL Server, è possibile eseguire le operazioni seguenti:

  - Personalizzare il firewall di SQL Server Express nei server Standard Edition, limitando l'ambito dei server che possono accedere in remoto al database. Per impostazione predefinita, qualsiasi indirizzo IP può accedere in remoto al database.

  - Usare Gestione configurazione SQL Server per specificare i protocolli, gli indirizzi IP e le porte per l'accesso remoto a SQL Server:
    
      - Lync Server 2013 usa il protocollo TCP/IP. Supporta IP versione 4 (IPv4), ma non IP versione 6 (IPv6).
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013 può funzionare in una rete con lo stack Dual IP abilitato.

        
        </div>
    
      - Lync Server 2013 supporta più indirizzi IP (schede di indirizzi di rete multihomed). È possibile specificare che SQL Server ascolti solo indirizzi IP specifici (indirizzo individuale o subnet) e usi solo protocolli specifici.
    
      - Lync Server 2013 supporta le porte SQL Server statiche e dinamiche.

  - Eseguire SQL Server in una porta statica (non predefinita) e non eseguire SQL Server browser (in modo che non possa segnalare la porta di attesa al client). Questo richiede una configurazione personalizzata in ogni client di SQL Server, inclusi i server front-end, il server di monitoraggio, il server di archiviazione e le console di amministrazione (in cui è in corso Lync Server Management Shell, pannello di controllo di Lync Server o generatore di topologie) e tutti gli altri Server che gestiscono database Lync Server).

<div>


> [!NOTE]  
> L'accesso ai database deve essere limitato agli amministratori di database attendibili. Un amministratore di database malintenzionato può inserire o modificare i dati nei database per acquisire privilegi sui server di Lync Server 2013 o ottenere informazioni riservate dai servizi, anche se non è stato concesso l'accesso diretto o l'amministratore del database controllo dei server di Lync Server 2013.



</div>

Per informazioni dettagliate sulle configurazioni personalizzate e l'indurimento dei database di SQL Server, vedere l'articolo di Blog di NextHop "utilizzo di Lync Server 2010 con una configurazione [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)di rete SQL Server personalizzata".

<div>


> [!NOTE]  
> È anche possibile indurire i sistemi operativi e i server delle applicazioni ed è possibile usare criteri di gruppo per implementare il blocco della sicurezza nella distribuzione di Lync Server. Per informazioni dettagliate, vedere <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">indurimento e protezione di server e applicazioni per Lync server 2013</A>.



</div>

</div>

<span> </span>

</div>

</div>

</div>

