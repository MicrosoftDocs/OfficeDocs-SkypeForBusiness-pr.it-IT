---
title: 'Lync Server 2013: requisiti tecnici per il server di chat persistente'
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
ms.openlocfilehash: 0437f56c5eb5564eb4f85809aefd181c2cbd2eaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Requisiti tecnici per il server di chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-06_

Ogni computer che ospita il server di chat persistente deve avere accesso a una topologia di Lync Server 2013 esistente con i componenti seguenti:

  - **Lync Server 2013, server front-end.**  Il server front-end è la base per il routing SIP (Session Initiation Protocol), che rende possibile la comunicazione tra i computer che eseguono il server di chat persistente e la funzionalità di chat persistente. Prima di iniziare a distribuire il server di chat persistente, verificare la distribuzione di Lync Server 2013, Standard Edition o un pool di front-end di Lync Server e tutti gli altri computer interni che eseguono Lync Server, in base alle esigenze dell'organizzazione.

Nelle sezioni seguenti vengono descritti i requisiti specifici per il server di chat persistente e il database in cui sono archiviati i dati della chat persistente.

<div>

## <a name="persistent-chat-server-requirements"></a>Requisiti del server di chat persistente

Per informazioni dettagliate sull'hardware consigliato per la distribuzione di Lync Server e la versione più recente del server di chat persistente, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.

Per informazioni dettagliate sul supporto del sistema operativo server e strumenti per Lync Server e il server di chat persistente, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.

Per informazioni dettagliate sul software aggiuntivo necessario per la distribuzione del server di chat persistente, vedere la tabella seguente.

### <a name="persistent-chat-server-software-prerequisites"></a>Prerequisiti software per la chat persistente

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
<td><p>Usato dal server di chat persistente e dal servizio di conformità della chat persistente, se distribuito.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>Requisiti del database del server Chat persistente

Persistent Chat Server usa il database di chat persistente per archiviare la cronologia delle chat, la configurazione e i dati di provisioning degli utenti. Facoltativamente, usa il database di conformità della chat persistente per archiviare i dati di conformità.

<div>


> [!IMPORTANT]  
> Il database di chat persistente (MGC) e il database di conformità (mgccomp) possono trovarsi nella stessa istanza di SQL Server o in server SQL diversi.



</div>

Per preparare una piattaforma del server di database, assicurarsi che ogni computer soddisfi i requisiti hardware e quindi installare il software prerequisito.

La piattaforma server per i server di database della chat persistente richiede lo stesso hardware del server di database back-end di Lync Server. Per informazioni dettagliate, vedere [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.

Nel server database verificare che sia installata una delle applicazioni software seguenti:

  - Microsoft SQL Server 2012. Per informazioni dettagliate su come installare Microsoft SQL Server 2012, vedere "installare SQL Server 2012" [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).

  - Microsoft SQL Server 2008 R2. Per informazioni dettagliate su come installare Microsoft SQL Server 2008 R2, vedere la pagina relativa all' [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)installazione di SQL Server (sql Server 2008 R2).

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>Requisiti del certificato del server di chat persistente

Per informazioni dettagliate sull'acquisizione di certificati, sulla creazione del database di SQL Server e sulla creazione di archivi di file, vedere [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

