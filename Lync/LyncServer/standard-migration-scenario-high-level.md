---
title: Scenario di migrazione standard - informazioni generali
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68ff7110cc7e14ccc76ab7d0c0125e723477934a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>Scenario di migrazione standard - informazioni generali

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-30_

Usare gli elementi seguenti come punto di partenza quando si esegue la migrazione di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat a Lync Server 2013, Persistent Chat Server. Il percorso di migrazione standard di Lync Server 2013 è il seguente:

  - L'organizzazione ha distribuito in precedenza Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat e si vuole distribuire Lync Server 2013, Persistent Chat Server.

  - Distribuire Lync Server 2013 e quindi distribuire i pool del server di chat persistente.

  - Preparare e pianificare la migrazione delle chat room persistenti e determinare il momento appropriato per arrestare il sistema per la migrazione.

  - Eseguire i cmdlet di Windows PowerShell per la migrazione (**Export-CsPersistentChatData** e **Import-CsPersistentChatData**) per trasferire il contenuto nel server di chat persistente.

  - Verificare che la migrazione sia riuscita.

  - Rimuovere la Commissione dalla distribuzione legacy.

  - Configurare il server di chat persistente in modo che i client legacy possano connettersi a Lync Server 2013, server di chat persistente. Questa operazione è necessaria perché richiede tempo per distribuire nuovi client e si vuole consentire agli utenti esistenti con client legacy di accedere alle chat room il più presto possibile.

  - Distribuire nuovi client, pur continuando a garantire che i dipendenti con la chat di gruppo legacy (client) possano arrivare alle loro chat room.

</div>

<span> </span>

</div>

</div>

</div>

