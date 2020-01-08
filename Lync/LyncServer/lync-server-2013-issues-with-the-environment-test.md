---
title: "Lync Server 2013: problemi con il test dell'ambiente"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ed158c598b9dc5596df23cb845f0adac4c6fed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Problemi con il test dell'ambiente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Analizzatore procedure consigliate consente di verificare che l'ambiente Lync Server 2013 sia una configurazione supportata. Come parte del controllo Active Directory Domain Services, Best Practices Analyzer esegue le operazioni seguenti:

  - Verifica la preparazione dello schema e della foresta dei servizi di dominio Active Directory.

  - Identifica il numero di siti e domini di servizi di dominio Active Directory nella distribuzione.

  - Controlla i livelli di foresta e di dominio.

  - Controlla la versione del controller di dominio.

  - Identifica il contesto dei nomi di dominio, configurazione e schema.

  - Identifica il numero di utenti abilitati.

  - Controlla la posizione in cui sono archiviate le impostazioni dei servizi di dominio Active Directory globale.

  - Controlla i punti di connessione del servizio (convergenza) per Lync Server.

  - Identifica la versione del database.

<div>

## <a name="resolving-issues-with-the-environment"></a>Risoluzione dei problemi relativi all'ambiente

Se il test dell'ambiente ha riscontrato problemi con l'ambiente, questi problemi sono probabilmente causati da problemi relativi alla configurazione di Active Directory o al livello di software in uso in server specifici. Ad esempio, se Best Practices Analyzer identifica tutti i controller di dominio nell'ambiente in cui è in esecuzione Windows Server 2000, emetterà un avviso e sarà necessario aggiornare questi controller di dominio a una versione supportata di Windows Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

