---
title: 'Lync Server 2013: requisiti tecnici per il server Chat persistente'
description: 'Lync Server 2013: requisiti tecnici per il server Chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 905563f31de36d41a48aea5fb8db3cfde9cb2434
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550332"
---
# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Requisiti tecnici per il server Chat persistente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-06_

Ogni computer che ospita il server Chat persistente deve disporre dell'accesso a una topologia esistente di Lync Server 2013 con i componenti seguenti:

  - **Lync server 2013, Front End Server.**   Il front end server è la base per il routing SIP (Session Initiation Protocol), che rende possibile la comunicazione tra i computer che eseguono il server Chat persistente e la funzionalità Persistent Chat. Prima di iniziare a distribuire il server Chat persistente, verificare la distribuzione di Lync Server 2013, Standard Edition o un pool Lync Server front end e qualsiasi altro computer interno che esegue Lync Server, in base alle esigenze dell'organizzazione.

Nelle sezioni seguenti vengono descritti i requisiti specifici per il server Chat persistente e il database in cui sono archiviati i dati della chat persistente.

<div>

## <a name="persistent-chat-server-requirements"></a>Requisiti del server Chat persistente

Per informazioni dettagliate sull'hardware consigliato per la distribuzione di Lync Server e la versione più recente del server Chat persistente, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.

Per informazioni dettagliate sul supporto del sistema operativo per server e strumenti per Lync Server e il server Chat persistente, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

Per informazioni dettagliate sul software aggiuntivo necessario per la distribuzione del server Chat persistente, vedere la tabella seguente.

### <a name="persistent-chat-server-software-prerequisites"></a>Prerequisiti software per il server Chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Software</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Accodamento messaggi</p></td>
<td><p>Utilizzato dal server Chat persistente e dal servizio di conformità di Persistent Chat, se distribuito.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>Requisiti del database del server Chat persistente

Il server Chat persistente utilizza il database di chat persistente per archiviare la cronologia delle chat, la configurazione e i dati di provisioning degli utenti. Facoltativamente, utilizza il database di conformità di Persistent Chat per archiviare i dati di conformità.

<div>


> [!IMPORTANT]  
> Il database di Persistent Chat (MGC) e il database di conformità (mgccomp) possono trovarsi nella stessa istanza di SQL Server o in SQL Server diversi.



</div>

Per preparare una piattaforma del server di database, accertarsi che ogni computer soddisfi i requisiti hardware e quindi installare il software prerequisito.

La piattaforma server per i server di database di chat persistente richiede lo stesso hardware del server database back-end di Lync Server. Per informazioni dettagliate, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.

Nel server di database, assicurarsi che sia installata una delle applicazioni software seguenti:

  - Microsoft SQL Server 2012. Per informazioni dettagliate sull'installazione di Microsoft SQL Server 2012, vedere "Install SQL Server 2012" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkID=248559](https://go.microsoft.com/fwlink/p/?linkid=248559) .

  - Microsoft SQL Server 2008 R2. Per informazioni dettagliate sull'installazione di Microsoft SQL Server 2008 R2, vedere la sezione relativa all'installazione di SQL Server (SQL Server 2008 R2) all'indirizzo [https://go.microsoft.com/fwlink/?LinkId=275702](https://go.microsoft.com/fwlink/?linkid=275702) .

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>Requisiti dei certificati del server Chat persistente

Per informazioni dettagliate sull'acquisizione dei certificati, la creazione del database di SQL Server e la creazione di archivi di file, vedere [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

