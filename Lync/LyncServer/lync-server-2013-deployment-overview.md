---
title: 'Lync Server 2013: Panoramica della distribuzione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b21d6c6a977fbb94a54114753f32c022aa5e713
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Panoramica della distribuzione per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-12_

La differenza principale tra Lync Server 2013 Enterprise Edition e Lync Server 2013 Standard Edition è che Standard Edition non supporta le funzionalità di disponibilità elevata incluse in Enterprise Edition. Per la disponibilità elevata, è necessario distribuire più front end server in un pool e quindi è possibile eseguire il mirroring del server che esegue SQL Server. Con Enterprise Edition è possibile scegliere di collocare o definire un Mediation Server autonomo. Monitoring Server and Archiving Server può utilizzare un server autonomo che esegue SQL Server. In alternativa, possono disporre di istanze di SQL Server in esecuzione nel server di database per i pool Front end e i server.

I server che eseguono Lync Server 2013 Standard Edition sono progettati per organizzazioni di dimensioni ridotte e posizioni remote, che sono geograficamente rimosse dalla distribuzione principale dell'organizzazione. Due server Standard Edition in combinazione per il failover in caso di emergenza possono supportare fino a 5.000 utenti. Non è possibile raggruppare i server Standard Edition come i front end server in Enterprise Edition. Inoltre, il database di SQL Server utilizzato da Standard Edition è un server collocato che esegue SQL Server Express che è stato creato per gestire i carichi di lavoro del server Standard Edition. Questo non significa che tutti i ruoli devono risiedere in un server Standard Edition. È possibile disporre di Mediation Server autonomi e server perimetrali. Il database di SQL Server per l'archivio di gestione centrale e ai fini di Lync Server 2013 deve risiedere nel server Standard Edition collocato con il server che esegue SQL Server. Il server di monitoraggio e il server di archiviazione utilizzano un server autonomo con il database di SQL Server.

</div>

<span> </span>

</div>

</div>

</div>

