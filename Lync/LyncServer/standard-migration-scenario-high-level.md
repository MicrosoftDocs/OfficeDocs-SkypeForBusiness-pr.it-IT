---
title: Scenario di migrazione standard-alto livello
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62a557d8b5a0f2a3e1e0f248b01795e75c02b3a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529803"
---
# <a name="standard-migration-scenario---high-level"></a>Scenario di migrazione standard-alto livello

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-30_

Utilizzare gli elementi seguenti come punto di partenza per la migrazione di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat a Lync Server 2013, server Chat persistente. Il percorso di migrazione standard di Lync Server 2013 è il seguente:

  - L'organizzazione ha distribuito in precedenza Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat e si desidera distribuire Lync Server 2013, il server Chat persistente.

  - Distribuire Lync Server 2013 e quindi distribuire i pool di server Chat persistente.

  - Preparare e pianificare la migrazione delle chat room permanenti e determinare il tempo appropriato per arrestare il sistema per la migrazione.

  - Eseguire i cmdlet di Windows PowerShell per la migrazione (**Export-CsPersistentChatData** e **Import-CsPersistentChatData**) per spostare il contenuto nel server Chat persistente.

  - Verificare la corretta esecuzione della migrazione.

  - Rimuovere la distribuzione legacy,

  - Configurare il server Chat persistente in modo che i client legacy possano connettersi a Lync Server 2013, server Chat persistente. Ciò è necessario perché la distribuzione dei nuovi client richiede tempo e si desidera consentire agli utenti esistenti con client legacy di poter accedere alle loro chat room il prima possibile.

  - Distribuire nuovi client, continuando a garantire che i lavoratori con i client di gruppo legacy possano accedere alle chat room.

</div>

<span> </span>

</div>

</div>

</div>

