---
title: "Lync Server 2013: prerequisiti per l'abilitazione dell'autenticazione Kerberos"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dd399ef7a0ed2dd6609fe0455d9593e1e567b3b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Prerequisiti per l'abilitazione dell'autenticazione Kerberos in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Prima di abilitare l'autenticazione Kerberos, accertarsi di aver completato tutte le operazioni preliminari di configurazione e di preparazione dell'infrastruttura:

  - Lo schema di Active Directory è esteso per Lync Server 2013.

  - La preparazione della foresta di Active Directory è stata completata per Lync Server 2013.

  - La preparazione del dominio Active Directory è stata completata per Lync Server 2013.

  - L'archivio di gestione centrale è stato installato e disponibile correttamente.

  - La topologia è stata creata e pubblicata tramite Generatore di topologie.

  - I server e i ruoli che richiedono i servizi Web sono stati definiti e distribuiti, inclusi front end server, server Standard Edition e Director.

  - Internet Information Services (IIS) è configurato e distribuito con i servizi ruolo consigliati per il supporto dei servizi Web in Lync Server 2013.

Dopo aver soddisfatto i prerequisiti, è necessario essere pronti a creare uno o più account per i servizi Web da utilizzare per l'autenticazione Kerberos per la distribuzione. È necessario creare come minimo un account di autenticazione Kerberos per ogni distribuzione. È tuttavia possibile creare un account per ogni sito per fornire l'autenticazione Kerberos locale nel sito. È possibile specificare un solo account di autenticazione Kerberos per sito.

</div>

<span> </span>

</div>

</div>

</div>

