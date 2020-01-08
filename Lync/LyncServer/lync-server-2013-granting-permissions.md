---
title: 'Lync Server 2013: Concessione di autorizzazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c8afde42a231124648824fbf8fbae07b0beedc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>Concessione di autorizzazioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-15_

Per la configurazione, è possibile concedere le autorizzazioni per il gruppo universale RTCUniversalServerAdmins per una specifica unità organizzativa di Active Directory, che consente ai membri del gruppo RTCUniversalServerAdmins in tale OU di installare Lync Server 2013 nel dominio specificato. Quando si assegnano le autorizzazioni per un'unità organizzativa, vengono concesse le autorizzazioni seguenti:

  - Leggere

  - Scrivere

  - ReadSPN

  - WriteSPN

Per l'amministrazione, è possibile aggiungere le autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi di RTC universali creati dalla preparazione della foresta possano accedere alle unità organizzative senza bisogno di essere membri del gruppo Domain Admins. Le autorizzazioni aggiunte all'unità organizzativa specificata sono le stesse che il cmdlet **Enable-CsAdDomain** aggiunge ai contenitori OU computer e utenti.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Concessione di autorizzazioni di installazione in Lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Concessioni di autorizzazioni per unità organizzative in Lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

