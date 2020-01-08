---
title: "Lync Server 2013: Prerequisiti per abilitare l'autenticazione Kerberos"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f405daa37007bffba1e02bd10d20d4de907e820e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Prerequisiti per abilitare l'autenticazione Kerberos in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Prima di abilitare l'autenticazione Kerberos, verificare di aver completato tutti i prerequisiti di configurazione e infrastruttura:

  - Lo schema di Active Directory è esteso per Lync Server 2013.

  - La preparazione della foresta di Active Directory viene completata per Lync Server 2013.

  - La preparazione del dominio Active Directory viene completata per Lync Server 2013.

  - Central Management store è stato installato e disponibile correttamente.

  - La topologia è stata creata e pubblicata tramite Generatore di topologie.

  - I server e i ruoli che richiedono servizi Web sono stati definiti e distribuiti, inclusi i server front-end, i server Standard Edition e i direttori.

  - Internet Information Services (IIS) è configurato e distribuito con i servizi ruolo consigliati per supportare i servizi Web in Lync Server 2013.

Dopo aver soddisfatto i prerequisiti, è necessario essere pronti per creare uno o più account per i servizi Web da usare per l'autenticazione Kerberos per la distribuzione. Devi almeno creare un account di autenticazione Kerberos per ogni distribuzione. Puoi tuttavia creare un account per ogni sito per consentire l'autenticazione Kerberos locale nel sito. È possibile specificare un solo account di autenticazione Kerberos per sito.

</div>

<span> </span>

</div>

</div>

</div>

