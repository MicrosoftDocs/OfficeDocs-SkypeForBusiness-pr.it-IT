---
title: 'Lync Server 2013: Distribuzione del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a730057735f187dc5e5080d532515a4eb9db110
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Distribuzione del server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-03-31_

Lync Server 2013, il server di chat persistente fa parte dell'infrastruttura di Lync Server 2013.

La distribuzione di un server di chat persistente richiede:

  - USA generatore di topologia per definire o importare e successivamente pubblicare la topologia e i componenti che vuoi distribuire.

  - Preparare l'ambiente per la distribuzione dei componenti del server di chat persistente.

  - Installare e configurare i componenti del server di chat persistenti per la distribuzione.

Il server di chat persistente è disponibile con Lync Server 2013 Enterprise Edition come pool separato (non collocato con i server front-end Enterprise Edition). Il server di chat persistente richiede un server back-end di SQL Server nel pool di Enterprise Edition per archiviare il contenuto della chat room e altri metadati rilevanti. È consigliabile installare **PersistentChatStore** in un server back-end di SQL Server dedicato, anche se è supportata la collocazione di Lync Server 2013 back end server e **PersistentChatStore** nella stessa istanza di SQL Server.

Il server di chat persistente può essere distribuito anche con Lync Server 2013 Standard Edition. In questo caso, il server front-end **PersistentChatService** è collocato nel computer Standard Edition e il server back-end di **PersistentChatStore** può essere distribuito nell'istanza di SQL Server Express locale.

Per informazioni dettagliate sulle configurazioni di Colocation supportate, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md).

<div>


> [!IMPORTANT]  
> Non è supportata la disponibilità elevata per Persistent Chat&nbsp;Server Standard Edition. Le prestazioni e la scala saranno limitate. Inoltre, sosteniamo solo il nuovo server&nbsp;standard per la chat persistente. Non è supportato l'aggiornamento di Lync Server 2010, Group Chat Server a una versione standard&nbsp;di lync server&nbsp;2013 Persistent Chat Server.



</div>

Se l'organizzazione richiede il supporto della conformità, è possibile installare il servizio di conformità del server di chat persistente nel server front end del server di chat persistente. Per la conformità è necessario un database separato.

Ogni topologia richiede almeno un server con Lync Server 2013 installato e un server con il software di database di SQL Server installato.

Usare generatore di topologie per aggiungere il server di chat persistente alle distribuzioni di Lync Server 2013. È possibile scegliere di aggiungere uno o più pool di server di chat persistenti tramite Generatore di topologia. Seguire le stesse istruzioni di distribuzione per la distribuzione di più pool di server di chat persistenti come per qualsiasi pool. Per informazioni dettagliate, vedere [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate sulle topologie disponibili e sui requisiti tecnici e software per l'installazione del server di chat persistente, vedere [pianificazione del server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione, funzionamento del [server di chat persistente in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) nella documentazione di pianificazione, documentazione di distribuzione o documentazione operativa e [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa al supporto.

Per informazioni dettagliate sull'acquisizione di certificati, sulla creazione del database di SQL Server e sulla creazione di archivi di file, vedere [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.

Un singolo server front-end di server di chat persistente può supportare utenti attivi di 20.000. È possibile avere un pool di server di chat persistente con un massimo di 4 server front-end attivi che supportano un totale di 80.000 utenti simultanei.

Il server di chat persistente è supportato anche in un server virtuale. Il server virtuale può supportare fino a 20.000 utenti simultanei se corrisponde alle specifiche del server fisico.

<div>


> [!IMPORTANT]  
> Il server di chat persistente deve essere installato in un file system NTFS per facilitare l'applicazione della sicurezza del file System. FAT32 non è un file system supportato per il server di chat persistente.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Funzionamento del server di chat persistente in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Elenco di controllo di distribuzione per il server Chat persistente in Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Requisiti tecnici per il server di chat persistente in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Configurazione dei sistemi e dell'infrastruttura per il server Chat persistente in Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Aggiunta del server Chat persistente alla distribuzione in Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Installazione del server Chat persistente in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Aggiunta di un amministratore di Chat persistente in Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Configurazione del server Chat persistente in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Risoluzione dei problemi di configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Configurazione del server Chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Failover e failback del server Chat persistente in Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

