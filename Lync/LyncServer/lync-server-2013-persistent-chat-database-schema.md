---
title: 'Lync Server 2013: Schema del database di Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73f3b21fe8ea7f9fc71aa5432a601e9fa3ad2425
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Schema del database di Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-18_

Questo documento documenta lo schema del database di chat persistente nel software di comunicazione di Lync Server 2013.

Il database della chat persistente fa riferimento al database corrispondente ai ruoli di Lync Server 2013 back-end server **PersistentChatStore** (corrispondente al database mgc) e **PersistentChatComplianceStore** (corrispondente al database mgccomp). L'obiettivo della pubblicazione di questo schema è quello di consentire la creazione di query e acquisire alcune informazioni utili per la creazione di una segnalazione utile intorno all'utilizzo della chat, alle sale attive, ai poster principali e così via.

<div>


> [!IMPORTANT]  
> Ci riserviamo il diritto di evolvere questo schema. Microsoft non garantisce di mantenere la compatibilità completa con questo schema pubblicato.



</div>

Seguire queste procedure consigliate:

  - Nessun SELECT\* //è supportato perché l'elenco di colonne può aumentare.

  - Non sono supportate modifiche allo schema generate dall'utente.

  - Non sono supportate operazioni di scrittura.

  - Testare le query che si compilano su database di dimensioni rappresentative per verificare che le query possano essere eseguite a un livello per soddisfare le proprie esigenze.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Elenco delle tabelle del server Chat persistente in Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Elenco delle tabelle di conformità del server Chat persistente in Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Dettagli sulle tabelle del server Chat persistente in Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Query del database di Chat persistente di esempio per Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

