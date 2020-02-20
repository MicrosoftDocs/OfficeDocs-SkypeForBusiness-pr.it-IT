---
title: 'Lync Server 2013: concessione di autorizzazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc725122005793790344544575fa4456d742c88d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>Concessione di autorizzazioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-15_

Per il programma di installazione, è possibile concedere le autorizzazioni per il gruppo universale RTCUniversalServerAdmins per un'unità organizzativa di Active Directory specifica, consentendo ai membri del gruppo RTCUniversalServerAdmins nell'unità organizzativa di installare Lync Server 2013 nel dominio specificato. Quando si assegnano le autorizzazioni per un'unità organizzativa, vengono concesse le autorizzazioni seguenti:

  - Lettura

  - Scrittura

  - ReadSPN

  - WriteSPN

Per l'amministrazione, è possibile aggiungere le autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza dover essere membri del gruppo Domain Admins. Le autorizzazioni aggiunte all'unità organizzativa specificata sono le stesse autorizzazioni che il cmdlet **Enable-CsAdDomain** aggiunge ai contenitori dell'unità organizzativa computer e utenti.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Concessione di autorizzazioni di installazione in Lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Concessione di autorizzazioni per le unità organizzative in Lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

