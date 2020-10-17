---
title: 'Lync Server 2013: sostituzione di XMLAdapter con una scheda di conformità del server Chat persistente personalizzata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c90452edc96a424111fcaa8c99dcf60e55e0109
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536353"
---
# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Sostituzione di XMLAdapter con una scheda di conformità del server Chat persistente personalizzata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

È possibile scrivere un adattatore personalizzato anziché utilizzare XmlAdapter installato con il server Chat persistente. A tale scopo, è necessario fornire un assembly .NET Framework che contenga una classe pubblica che implementi l'interfaccia **IComplianceAdapter** . È necessario inserire questo assembly nella cartella di installazione del server Chat persistente di ogni server nel pool di server Chat persistente. Uno qualsiasi dei server di conformità è in grado di fornire i dati di conformità alla scheda, ma i server di conformità non forniranno i dati di conformità duplicati a più istanze della scheda.

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>Implementazione dell'interfaccia IComplianceAdapter

L'interfaccia è definita nell'assembly Compliance.dll nello spazio dei nomi `Microsoft.Rtc.Internal.Chat.Server.Compliance` . L'interfaccia definisce due metodi che devono essere implementati dall'adattatore personalizzato.

    void SetConfig(AdapterConfig config)

Il server di conformità di Persistent Chat chiamerà questo metodo al primo caricamento dell'adapter. `AdapterConfig`Contiene la configurazione di conformità di Persistent Chat pertinente per la scheda di conformità.

    void Translate(ConversationCollection conversations)

Il server di conformità di Persistent Chat chiama questo metodo a intervalli periodici finché sono presenti nuovi dati da tradurre. Questo intervallo di tempo è uguale a quello `RunInterval` impostato nella configurazione di conformità di Persistent Chat.

`ConversationCollection`Contiene le informazioni di conversazione raccolte dall'ultima volta che è stato chiamato il metodo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

