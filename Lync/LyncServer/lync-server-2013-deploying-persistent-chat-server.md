---
title: 'Lync Server 2013: distribuzione del server Chat persistente'
description: 'Lync Server 2013: distribuzione del server Chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b85c0070ab4bcd60d80d57738c25daac1de4faf1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566092"
---
# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Distribuzione del server Chat persistente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-03-31_

Lync Server 2013, il server Chat persistente fa parte dell'infrastruttura di Lync Server 2013.

La distribuzione del server Chat persistente richiede:

  - Utilizzare Generatore di topologie per definire o importare e successivamente pubblicare la topologia e i componenti che si desidera distribuire.

  - Preparare l'ambiente per la distribuzione dei componenti del server Chat persistente.

  - Installare e configurare i componenti del server Chat persistente per la distribuzione.

Il server Chat persistente è disponibile con Lync Server 2013 Enterprise Edition come pool separato (non incluso nei server Enterprise Edition front end). Il server di chat persistente richiede un server back-end SQL Server nel pool Enterprise Edition per archiviare il contenuto della chat room e altri metadati rilevanti. È consigliabile installare **PersistentChatStore** in un server back-end SQL Server dedicato, anche se è supportato il server back-end di Lync Server 2013 e **PersistentChatStore** nella stessa istanza di SQL Server.

Il server Chat persistente può anche essere distribuito con Lync Server 2013 Standard Edition. In questo caso, il server front end di **PersistentChatService** è collocato nel computer Standard Edition e il server back-end di **PersistentChatStore** può essere distribuito nell'istanza locale di SQL Server Express.

Per informazioni dettagliate sulle configurazioni di Colocation supportate, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md).

<div>


> [!IMPORTANT]  
> La disponibilità elevata non è supportata per il server Standard Edition di Persistent Chat &nbsp; . Le prestazioni e la scala saranno limitate. Inoltre, è supportato solo il nuovo server Standard Edition di Persistent Chat Server &nbsp; . Non è supportato l'aggiornamento di Lync Server 2010, Group Chat Server a un server Standard Edition di Lync Server 2013 &nbsp; Persistent Chat &nbsp; .



</div>

Se nell'organizzazione è necessario il supporto della conformità, è possibile installare il servizio di conformità del server Chat persistente sul server front end server Chat persistente. Per motivi di conformità è richiesto un database separato.

Ogni topologia richiede almeno un server con Lync Server 2013 installato e un server con il software di database di SQL Server installato.

Utilizzare Generatore di topologie per aggiungere il server Chat persistente alle distribuzioni di Lync Server 2013. È possibile scegliere di aggiungere uno o più pool di server Chat persistente utilizzando Generatore di topologie. Seguire le stesse istruzioni per la distribuzione per la distribuzione di più pool di server Chat persistente come si farebbe per qualsiasi pool. Per informazioni dettagliate, vedere [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate sulle topologie disponibili e sui requisiti tecnici e software per l'installazione del server Chat persistente, vedere [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione, [come funziona il server Chat persistente in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni e all' [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità.

Per informazioni dettagliate sull'acquisizione dei certificati, la creazione del database di SQL Server e la creazione di archivi di file, vedere [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.

Un singolo server front end del server di chat persistente può supportare 20.000 utenti attivi. È possibile disporre di un pool di server Chat persistente con fino a 4 server front end attivi che supportano un totale di 80.000 utenti simultanei.

Il server Chat persistente è supportato anche in un server virtuale. Quest'ultimo può supportare fino a 20.000 utenti se ha le stesse specifiche del server fisico.

<div>


> [!IMPORTANT]  
> Il server Chat persistente deve essere installato in un file system NTFS per consentire di applicare la sicurezza del file System. FAT32 non è un file system supportato per il server Chat persistente.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Funzionamento del server Chat persistente in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Elenco di controllo di distribuzione per il server Chat persistente in Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Requisiti tecnici per il server Chat persistente in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Configurazione dei sistemi e dell'infrastruttura per il server Chat persistente in Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Aggiunta del server Chat persistente alla distribuzione in Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Installazione del server Chat persistente in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Aggiunta di un amministratore di chat persistente in Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Configurazione del server Chat persistente in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Risoluzione dei problemi relativi alla configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Configurazione del server Chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Failover e failover del server Chat persistente in Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

