---
title: "Lync Server 2013: problemi con il test dell'ambiente"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c96bae1a917efa52dfc25639d7e46fc1b7e2142e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Problemi relativi al test dell'ambiente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Best Practices Analyzer consente di verificare che l'ambiente Lync Server 2013 sia una configurazione supportata. Best Practices Analyzer fa parte dei controlli di Servizi di dominio Active Directory ed esegue le operazioni seguenti:

  - Verifica la preparazione della foresta e dello schema di Servizi di dominio Active Directory.

  - Identifica il numero di siti e domini di Servizi di dominio Active Directory nella distribuzione.

  - Controlla i livelli di foresta e dominio.

  - Controlla la versione del controller di dominio.

  - Identifica il dominio, la configurazione e il contesto di denominazione dello schema.

  - Identifica il numero degli utenti abilitati.

  - Controlla dove sono archiviate le impostazioni globali di Servizi di dominio Active Directory.

  - Verifica la disposizione dei punti di connessione del servizio (SCP) per Lync Server.

  - Identifica la versione del database.

<div>

## <a name="resolving-issues-with-the-environment"></a>Risoluzione dei problemi con l'ambiente

Se il test dell'ambiente rileva problemi con l'ambiente, questi potrebbero essere causati da problemi relativi alla configurazione di Active Directory o al livello di software in esecuzione in server specifici. Ad esempio, se Best Practices Analyzer identifica nell'ambiente dei controller di dominio in cui è in esecuzione Windows Server 2000, verrà visualizzato un avviso e sarà necessario aggiornare i controller di dominio alla versione supportata di Windows Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

