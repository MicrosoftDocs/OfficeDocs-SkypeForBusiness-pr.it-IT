---
title: 'Lync Server 2013: server Edge audio/video (A/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9738dbb11ce731ac832a5529d2013f3f9b2907
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a>Audio/video (A/V) Edge Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Il servizio A/V Edge consente agli utenti interni (utenti che hanno effettuato l'accesso alla rete organizzativa) di condividere audio e video con utenti esterni (utenti che non hanno eseguito l'accesso alla rete organizzativa). Oltre all'audio e al video, l'A/V Edge service offre anche il supporto per la condivisione desktop e il trasferimento di file.

Il servizio A/V Edge viene gestito principalmente tramite la configurazione A/V Edge; Queste impostazioni consentono di gestire la quantità massima di larghezza di banda da allocare per ogni porta e per utente e di specificare il periodo di tempo in cui può essere usato un token di autenticazione prima che il token debba essere rinnovato. Le impostazioni di configurazione di Edge a/V possono essere applicate ai siti o ai singoli server a/V Edge. Per determinare quale raccolta di impostazioni avrà la priorità, usare la guida seguente:

  - Le impostazioni configurate nell'ambito del servizio, ovvero su un singolo server, hanno la priorità su tutto.

  - Le impostazioni configurate nell'ambito del sito hanno la priorità sulle impostazioni configurate nell'ambito globale. Tuttavia, le impostazioni dell'ambito del servizio sostituiranno anche le impostazioni dell'ambito del sito.

  - Le impostazioni dell'ambito globale verranno usate solo se non sono state configurate impostazioni di servizio nel singolo server e se non sono presenti impostazioni del sito per il sito in cui si trova il server.

Il servizio A/V Edge può essere gestito solo tramite Lync Server PowerShell e i cmdlet CsAVEdgeConfiguration.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Restituire le informazioni di configurazione A/V Edge Server in Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [Creare o modificare una raccolta di impostazioni di configurazione di un/V Edge Server in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [Eliminare una raccolta esistente di impostazioni di configurazione di un/V Edge Server in Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

