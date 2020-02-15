---
title: 'Lync Server 2013: indurimento e protezione dei database'
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
ms.openlocfilehash: 6e1ef045253f6733ea3356baa6254a6c90926762
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>Indurimento e protezione dei database di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-12-05_

Microsoft Lync Server 2013 dipende anche da database di SQL Server per l'archiviazione delle informazioni utente, dello stato delle conferenze, dei dati di archiviazione e delle registrazioni dettagli chiamata (CDRs). Per massimizzare la disponibilità dei dati di Lync Server 2013 nei database back-end di Lync Server, è possibile suddividere i dati dell'applicazione in modo da migliorare la tolleranza di errore e semplificare la risoluzione dei problemi. Per raggiungere questi obiettivi, suddividere i dati dell'applicazione per:

  - **Utilizzo delle procedure**   consigliate per il partizionamento dei server separare i file del sistema operativo, dell'applicazione e del programma dai file di dati.

  - **Archiviazione dei file di registro delle transazioni e dei file**   di database archiviare questi file separatamente per aumentare la tolleranza di errore e ottimizzare il ripristino e archiviarli su un disco o un volume crittografato.

  - **Utilizzo**   del cluster di clustering dei server back-end per ottimizzare la disponibilità del sistema di Lync Server 2013.

  - **Assicurarsi che tutti i backup dei dati siano crittografati e gestiti**   adeguatamente persi, ignorati o che i supporti di backup non posizionati siano in grado di rappresentare una minaccia significativa per la sicurezza dei dati per le distribuzioni di Lync Server 2013

In qualsiasi server Lync Server 2013 eccetto il server Standard Edition, l'istanza di SQL Server Express (istanza di RTCLOCAL) non è accessibile in remoto e non viene creata alcuna eccezione del firewall locale, ad eccezione di SQL Server Express su un server Standard Edition. In un server Standard Edition, sia il database back-end che l'archivio di gestione centrale (CMS) sono configurati per essere accessibili in remoto. Per indurire i database di SQL Server, è possibile eseguire le operazioni seguenti:

  - Personalizzare il firewall di SQL Server Express nei server Standard Edition, limitando l'ambito dei server che possono accedere in remoto al database. Per impostazione predefinita, qualsiasi indirizzo IP può accedere in remoto al database.

  - Utilizzare Gestione configurazione SQL Server per specificare i protocolli, gli indirizzi IP e le porte per l'accesso remoto a SQL Server:
    
      - Lync Server 2013 utilizza il protocollo TCP/IP. Supporta IP versione 4 (IPv4), ma non IP versione 6 (IPv6).
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013 può funzionare in una rete con doppio stack IP abilitato.

        
        </div>
    
      - Lync Server 2013 supporta più indirizzi IP (schede indirizzi di rete multihomed). È possibile specificare che SQL Server ascolti solo indirizzi IP specifici (indirizzo individuale o subnet) e utilizzi solo protocolli specifici.
    
      - Lync Server 2013 supporta le porte SQL Server statiche e dinamiche.

  - Eseguire SQL Server in una porta statica (non predefinita) e non eseguire SQL Server browser (pertanto non è possibile segnalare la porta di attesa al client). Questo richiede una configurazione personalizzata su ogni client SQL Server, compresi front end server, Monitoring Server, server di archiviazione e console amministrative (esecuzione di Lync Server Management Shell, pannello di controllo di Lync Server o generatore di topologie) e tutte le altre Server che eseguono database di Lync Server).

<div>


> [!NOTE]  
> L'accesso ai database deve essere limitato agli amministratori di database attendibili. Un amministratore di database dannoso potrebbe inserire o modificare i dati nei database per acquisire i privilegi sui server Lync Server 2013 o ottenere informazioni riservate dai servizi, anche se all'amministratore del database non è stato concesso l'accesso diretto o controllo dei server Lync Server 2013.



</div>

Per informazioni dettagliate sulle configurazioni personalizzate e sull'indurimento dei database di SQL Server, vedere l'articolo del Blog di NextHop "utilizzo di Lync Server 2010 con una configurazione [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)di rete di SQL Server personalizzata" all'indirizzo.

<div>


> [!NOTE]  
> È inoltre possibile indurire i sistemi operativi e i server applicazioni ed è possibile utilizzare criteri di gruppo per implementare blocchi di sicurezza nella distribuzione di Lync Server. Per informazioni dettagliate, vedere <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">hardening and protecting Servers and Applications for Lync Server 2013</A>.



</div>

</div>

<span> </span>

</div>

</div>

</div>

