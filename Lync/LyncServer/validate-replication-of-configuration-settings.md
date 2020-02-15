---
title: Convalidare la replica delle impostazioni di configurazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65620e07227581f35e5760e8665e615c6976bde2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a>Convalidare la replica delle impostazioni di configurazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet **Get-CsManagementStoreReplicationStatus** di lync Server 2013 nel computer interno in cui si trova l'archivio di gestione centrale o qualsiasi computer aggiunto a un dominio in cui è installato lync Server 2013 Core Components.

I risultati iniziali possono indicare lo stato "False" anziché "True" per la replica. In questo caso, eseguire il cmdlet **Invoke-CsManagementStoreReplication** e attendere il completamento della replica prima di eseguire di nuovo **Get-CsManagementStoreReplicationStatus**.

</div>

<span> </span>

</div>

</div>

</div>

