---
title: Convalidare la replica delle impostazioni di configurazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cde1f3a96f249e98bc4e48c2e6d9c40adaad526
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a>Convalidare la replica delle impostazioni di configurazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

È possibile convalidare la replica delle informazioni di configurazione nel server perimetrale eseguendo il cmdlet **Get-CsManagementStoreReplicationStatus** di lync Server 2013 nel computer interno in cui si trova l'archivio di gestione centrale o un computer collegato a un dominio in cui sono installati i componenti principali di lync Server 2013.

I risultati iniziali possono indicare lo stato "false" invece di "true" per la replica. In questo caso, eseguire il cmdlet **Invoke-CsManagementStoreReplication** e consentire il completamento della replica prima di eseguire di nuovo il cmdlet **Get-CsManagementStoreReplicationStatus** .

</div>

<span> </span>

</div>

</div>

</div>

