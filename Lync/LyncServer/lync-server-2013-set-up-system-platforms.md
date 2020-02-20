---
title: 'Lync Server 2013: configurare le piattaforme di sistema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec8b2e923b4c0815449ce7fd7beb2624fe728623
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>Configurare le piattaforme di sistema in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Prima di avviare la distribuzione del server Chat persistente, è necessario installare il sistema operativo necessario sull'hardware che soddisfi i requisiti di sistema nei server:

Per informazioni dettagliate sull'hardware supportato per i server che eseguono Lync Server 2013, i server di database e i file server, vedere [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità. Per informazioni dettagliate sui sistemi operativi e il software di database supportati, vedere [Server software and Infrastructure Support in Lync server 2013](lync-server-2013-server-software-and-infrastructure-support.md) nella documentazione relativa alla supportabilità. Per informazioni dettagliate sui requisiti di Windows Update, vedere [additional server support and requirements in Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) nella documentazione relativa alla supportabilità.

Il server front-end di Persistent Chat Server, **PersistentChatService**, può essere distribuito su uno o più computer autonomi in un pool Lync Server 2013 Enterprise Edition. Non possono essere collocati nei server front end di Lync Server Enterprise Edition. Il server Chat persistente può essere distribuito dal programma di avvio automatico, proprio come gli altri ruoli di Lync Server. I **servizi Web di chat persistente per il caricamento o il download di file**e i **servizi Web di chat persistente per la gestione delle chat room** sono componenti Web distribuiti nei server front End di Lync Server 2013.

Un singolo server front end del server di chat persistente può supportare 20.000 utenti attivi. È possibile disporre di un pool di server Chat persistente con un massimo di 4 front-end attivi che supportano un totale di 80.000 utenti simultanei. Il server back-end della chat persistente, **PersistentChatStore**, archivia le chat room e le categorie. È consigliabile installare **PersistentChatStore** in un server back-end SQL Server dedicato nel pool Enterprise Edition. anche se è supportata la collocazione del server back-end Lync Server 2013 e **PersistentChatStore** nella stessa istanza di SQL Server.

Se nell'organizzazione è necessario il supporto della conformità, è possibile installarlo tramite Generatore di topologie. Il servizio di conformità del server Chat persistente è installato nello stesso computer del server front end server di chat persistente. Per motivi di conformità è richiesto un database separato. Per informazioni dettagliate sui requisiti di conformità per il server Chat persistente, vedere [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione.

Ogni topologia richiede almeno un server con Lync Server 2013 installato e un server con il software di database di SQL Server installato. Generatore di topologie supporta più pool di server Chat persistente. Seguire le stesse istruzioni per la distribuzione per la distribuzione di più pool di server Chat persistente come si farebbe per qualsiasi pool dalla [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.

È inoltre possibile distribuire il server Chat persistente con Lync Server 2013 Standard Edition. In questo caso, il server front end di **PersistentChatService** è collocato nel server Standard Edition ed è possibile distribuire il server back-end di **PersistentChatStore** nell'istanza locale di SQL Server Express.

<div>


> [!IMPORTANT]  
> Non è supportato il server&nbsp;di chat persistente Standard Edition per la disponibilità elevata. Le prestazioni e la scala saranno limitate. Inoltre, vengono supportate solo le nuove distribuzioni&nbsp;del server Standard Edition di Persistent Chat Server. Non è supportato un aggiornamento di Lync Server 2010, Group Chat Server a un server&nbsp;&nbsp;Standard Edition di Lync Server 2013 Persistent Chat.



</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti e supporto per i server aggiuntivi in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)  


[Hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md)  
[Supporto dell'infrastruttura e del software server in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md)  
[Pianificazione del server Chat persistente in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
[Distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

