---
title: 'Lync Server 2013: supporto per più trunk'
description: 'Lync Server 2013: supporto per più trunk.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbabb90405b3fdae47a59ba8a0798743943216d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552422"
---
# <a name="multiple-trunk-support-in-lync-server-2013"></a>Supporto per più trunk in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

La funzionalità di Lync Server 2013 supporta più associazioni tra gateway e Mediation Server. Queste associazioni vengono eseguite definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX. Utilizzare il generatore di topologie per associare i gateway a Mediation Server (ovvero Trunks).

  - Per assegnare o rimuovere un trunk in Lync Server 2013, è innanzitutto necessario definire un trunk in Generatore di topologie. Un trunk è costituito dai seguenti elementi: Mediation Server Fully Qualified Domain Name (FQDN), la porta di attesa Mediation Server, il nome di dominio completo del gateway e la porta di attesa del gateway.

  - Per configurare più trunk, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server. Questo fornisce ulteriore resilienza all'infrastruttura VoIP aziendale, che è particolarmente utile in scenari di interoperabilità PBX (Private Branch Exchange).

Dopo essere stato definito, il trunk deve essere associato a una route. Per associare un trunk a una route, è possibile definire un nome semplice per il trunk in Generatore di topologie. Questo nome semplice viene utilizzato come nome del trunk nel pannello di controllo di Lync Server, dove Trunks può essere associato a route. Il nome del trunk semplice viene utilizzato come nome del gateway da Lync Server Management Shell.

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server. Dal generatore di topologie fare clic con il pulsante destro del mouse sul Mediation Server associato e quindi scegliere **Proprietà**. Specificare il gateway predefinito per il Mediation Server.

Nel diagramma seguente vengono illustrati i trunk multipli definiti per ogni Mediation Server e gateway.

**Routing con trunk M-N**

![Più assegnazioni di trunk.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Più assegnazioni di trunk.")

</div>

<span> </span>

</div>

</div>

</div>

