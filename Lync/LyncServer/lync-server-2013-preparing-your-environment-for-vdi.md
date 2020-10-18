---
title: "Lync Server 2013: preparazione dell'ambiente per VDI"
description: "Lync Server 2013: preparazione dell'ambiente per VDI."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e90b9e0f09d3082a28406f1a1dc715285ee4d7e3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579912"
---
# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a>Preparazione dell'ambiente Lync Server 2013 per VDI

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Per preparare l'ambiente per il plug-in VDI di Lync, è necessario che l'amministratore esegua i passaggi seguenti.

1.  In Lync Server 2013, assicurarsi che EnableMediaRedirection sia impostato su TRUE per tutti gli utenti di VDI. Per informazioni dettagliate, vedere gli argomenti della Guida per il cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e il cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

2.  Nel computer del Data Center installare il client Lync 2013 in tutte le macchine virtuali.

3.  Nei computer locali installare il plug-in VDI di Lync.

</div>

<span> </span>

</div>

</div>

</div>

