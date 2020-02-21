---
title: 'Lync Server 2013: schema del database di chat persistente'
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
ms.openlocfilehash: a18cd17686133219ccc60d5e85fd149df190665a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Schema del database di chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-18_

In questo documento viene documentato lo schema del database di chat persistente in Lync Server 2013 Communications software.

Il database di Persistent Chat si riferisce al database corrispondente ai ruoli del server back-end di Lync Server 2013 **PersistentChatStore** (corrispondente al database di MGC) e **PersistentChatComplianceStore** (corrispondente al database di mgccomp). L'obiettivo della pubblicazione di questo schema è di consentire la creazione di query per comprendere meglio come generare rapporti efficaci relativi all'uso della chat, alle chat attive, agli autori di post più attivi e così via.

<div>


> [!IMPORTANT]  
> Ci riserviamo il diritto di modificare questo schema. Microsoft non garantisce di poter mantenere la completa compatibilità di questo schema pubblicato con le versioni precedenti.



</div>

Tenere presenti queste procedure consigliate:

  - Nessuna selezione\* //è supportata perché l'elenco di colonne può aumentare.

  - Non sono supportate modifiche allo schema generate dall'utente.

  - Non sono supportate operazioni di scrittura

  - Testare le query create con database di dimensioni rappresentative, per assicurarsi che le prestazioni soddisfino le esigenze.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Elenco delle tabelle del server Chat persistente in Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Elenco delle tabelle di conformità del server Chat persistente in Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Dettagli della tabella del server Chat persistente in Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Query del database di chat persistente di esempio per Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

