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
ms.openlocfilehash: 3d237e0ba3f94f81ce3988e2ce8994d49f97087d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Panoramica della distribuzione per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-12_

La differenza principale tra Lync Server 2013 Enterprise Edition e Lync Server 2013 Standard Edition è che Standard Edition non supporta le caratteristiche di disponibilità elevata incluse in Enterprise Edition. Per una disponibilità elevata, è necessario distribuire più server front-end in un pool e quindi è possibile eseguire il mirroring del server in cui è in uso SQL Server. Con Enterprise Edition è possibile scegliere di collocare o definire un Mediation Server autonomo. Il server di monitoraggio e l'archiviazione possono usare un server autonomo con SQL Server. In alternativa, possono avere istanze di SQL Server in uso nel server di database per i pool e i server front-end.

I server che esegue Lync Server 2013 Standard Edition sono progettati per organizzazioni di piccole dimensioni e percorsi remoti, che vengono rimossi geograficamente dalla distribuzione principale dell'organizzazione. Due server standard in combinazione per il failover in caso di emergenza possono supportare fino a 5.000 utenti. Non è possibile raggruppare i server standard di edizione come i server front-end in Enterprise Edition. Inoltre, il database di SQL Server usato da Standard Edition è un server collocato con SQL Server Express progettato per gestire i carichi di lavoro del server Standard Edition. Questo non significa che tutti i ruoli debbano risiedere in un server Standard Edition. Puoi avere Mediation Server e Edge Server autonomi. Il database di SQL Server per l'archivio di gestione centralizzato e per gli scopi di Lync Server 2013 deve risiedere nel server Standard Edition con il server in cui è in uso SQL Server. Il server di monitoraggio e l'archiviazione usano un server autonomo con il database di SQL Server.

</div>

<span> </span>

</div>

</div>

</div>

