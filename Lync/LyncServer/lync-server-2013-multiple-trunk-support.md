---
title: 'Lync Server 2013: supporto per più trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156db04ceb26809c7043f30e9e01ea0071e0a31d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a>Supporto per più trunk in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

La funzionalità Lync Server 2013 supporta più associazioni tra gateway e Mediation Server. Queste associazioni vengono effettuate definendo un trunk, che è un'associazione logica tra un pool di Mediation Server e un gateway PSTN (Public Switched Telephone Network), Session Border Controller (SBC) o IP-PBX. Usare il generatore di topologie per associare i gateway ai server di mediazione (ovvero Trunks).

  - Per assegnare o rimuovere un trunk in Lync Server 2013, è prima di tutto necessario definire un trunk in Generatore di topologie. Un trunk è costituito dall'associazione seguente: Mediation Server Fully Qualified Domain Name (FQDN), la porta di ascolto di Mediation Server, il nome di dominio completo del gateway e la porta di ascolto del gateway.

  - Per configurare più Trunks, è possibile creare più associazioni tra lo stesso gateway e il Mediation Server. In questo modo è disponibile un'ulteriore resilienza dell'infrastruttura VoIP aziendale, che risulta particolarmente utile negli scenari di interoperabilità del PBX (Private Branch Exchange).

Quando viene definito un trunk, deve essere associato a una route. Per associare un trunk a una route, è possibile definire un nome semplice per il trunk in Generatore di topologia. Questo nome semplice viene usato come nome del trunk nel pannello di controllo di Lync Server, dove Trunks può essere associato alle route. Il nome trunk semplice viene usato come nome del gateway da Lync Server Management Shell.

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

L'amministratore deve selezionare un trunk predefinito associato a un Mediation Server. In Generatore di topologie fare clic con il pulsante destro del mouse sul server di mediazione associato e quindi scegliere **Proprietà**. Specificare il gateway predefinito per il Mediation Server.

Il diagramma seguente illustra i trunk più definiti per ogni Mediation Server e gateway.

**Routing Trunk M-N**

![Più assegnazioni trunk.] (images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Più assegnazioni trunk.")

</div>

<span> </span>

</div>

</div>

</div>

