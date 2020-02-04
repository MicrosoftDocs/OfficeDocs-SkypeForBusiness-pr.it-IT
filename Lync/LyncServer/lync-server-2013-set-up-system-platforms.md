---
title: 'Lync Server 2013: Configurare le piattaforme del sistema'
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
ms.openlocfilehash: 6bb714cf9da27e968a4e02e8d822ab8e597f654d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>Configurare le piattaforme del sistema in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Prima di avviare la distribuzione del server di chat persistente, è necessario installare il sistema operativo necessario su hardware che soddisfi i requisiti di sistema per i server:

Per informazioni dettagliate sull'hardware supportato per i server che utilizzano Lync Server 2013, i server di database e i file server, vedere [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità. Per informazioni dettagliate su sistemi operativi e software di database supportati, vedere [supporto di software e infrastrutture server in Lync server 2013](lync-server-2013-server-software-and-infrastructure-support.md) nella documentazione relativa alla supportabilità. Per informazioni dettagliate sui requisiti di Windows Update, vedere [supporto e requisiti aggiuntivi del server in Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md) nella documentazione relativa alla supportabilità.

Il server front-end del server di chat persistente, **PersistentChatService**, può essere distribuito in uno o più computer autonomi in un pool di Lync Server 2013 Enterprise Edition. Non possono essere collocati nei server front-end di Lync Server Enterprise Edition. Il server di chat persistente può essere distribuito dal programma di avvio automatico, proprio come gli altri ruoli di Lync Server. I **servizi Web di chat persistenti per il caricamento e il download di file**e i **servizi Web di chat persistenti per la gestione delle chat room** sono componenti Web distribuiti nei server front-End di Lync Server 2013.

Un singolo server front-end di server di chat persistente può supportare utenti attivi di 20.000. È possibile avere un pool di server di chat persistente con un massimo di 4 front-end attivi che supportano un totale di 80.000 utenti simultanei. Il server di back-end della chat persistente, **PersistentChatStore**, archivia le chat room e le categorie. È consigliabile installare **PersistentChatStore** in un server back-end di SQL Server dedicato nel pool di Enterprise Edition. anche se supportiamo la collocazione di Lync Server 2013 back-end server e **PersistentChatStore** nella stessa istanza di SQL Server.

Se l'organizzazione richiede il supporto della conformità, è possibile installarla usando generatore di topologie. Il servizio di conformità del server di chat persistente viene installato nello stesso computer del server front-end di Persistent Chat. Per la conformità è necessario un database separato. Per informazioni dettagliate sui requisiti di conformità per il server di chat persistente, vedere [pianificazione del server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione.

Ogni topologia richiede almeno un server con Lync Server 2013 installato e un server con il software di database di SQL Server installato. Generatore di topologia supporta più pool di server di chat persistenti. Seguire le stesse istruzioni di distribuzione per la distribuzione di più pool di server di chat persistenti come per qualsiasi pool dalla [distribuzione di Lync server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.

È anche possibile distribuire il server di chat persistente con Lync Server 2013 Standard Edition. In questo caso, il server front-end **PersistentChatService** è collocato nel server Standard Edition ed è possibile distribuire il server back-end di **PersistentChatStore** nell'istanza di SQL Server Express locale.

<div>


> [!IMPORTANT]  
> Non è supportata la versione standard di&nbsp;Persistent Chat Server per l'elevata disponibilità. Le prestazioni e la scala saranno limitate. Inoltre, sosteniamo solo le nuove distribuzioni&nbsp;del server standard per la chat persistente. Non è supportato un aggiornamento di Lync Server 2010, Group Chat Server in una versione standard di Lync&nbsp;Server 2013 Persistent Chat Server&nbsp;.



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

