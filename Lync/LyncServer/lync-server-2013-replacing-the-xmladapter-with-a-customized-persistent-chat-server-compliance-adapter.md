---
title: "Lync Server 2013: sostituire l'XMLAdapter con un adattatore di conformità del server di chat persistente personalizzato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d26e470438dc8a79dbaa3944c05ad4158cafe44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Sostituzione di XMLAdapter con un adattatore di conformità del server di chat persistente personalizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

È possibile scrivere una scheda personalizzata invece di usare l'XmlAdapter installato con il server di chat persistente. A questo scopo, devi specificare un assembly .NET Framework che contiene una classe pubblica che implementa l'interfaccia **IComplianceAdapter** . È necessario inserire questo assembly nella cartella di installazione del server di chat persistente di ogni server nel pool del server di chat persistente. Uno dei server di conformità può specificare i dati di conformità alla scheda, ma i server di conformità non forniranno i dati di conformità duplicati a più istanze della scheda.

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>Implementazione dell'interfaccia IComplianceAdapter

L'interfaccia è definita nell'assembly Compliance. dll nello spazio dei `Microsoft.Rtc.Internal.Chat.Server.Compliance`nomi. L'interfaccia definisce due metodi che devono essere implementati dall'adapter personalizzato.

    void SetConfig(AdapterConfig config)

Il server di conformità della chat persistente chiamerà questo metodo quando l'adapter viene caricato per primo. `AdapterConfig` Contiene la configurazione della conformità della chat persistente pertinente per la scheda conformità.

    void Translate(ConversationCollection conversations)

Il server di conformità della chat persistente chiama questo metodo a intervalli periodici, purché siano presenti nuovi dati da tradurre. Questo intervallo di tempo è uguale a `RunInterval` quello impostato nella configurazione della conformità della chat persistente.

`ConversationCollection` Contiene le informazioni sulla conversazione raccolte dall'ultima volta che è stato chiamato questo metodo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

