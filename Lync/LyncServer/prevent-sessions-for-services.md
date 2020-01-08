---
title: Impedire le sessioni per i servizi
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19f3ed7c788db120782966541bfea9813328d90c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a>Impedire le sessioni per i servizi

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

È possibile usare il pannello di controllo di Microsoft Lync Server 2010 per impedire l'utilizzo di nuove sessioni per tutti i servizi Lync Server 2010 in uso in un computer specifico o per impedire nuove sessioni per un servizio specifico di Lync Server 2010.

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>Per evitare nuove sessioni per tutti i servizi Lync Server in un computer

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire il pannello di controllo di Lync Server.

3.  Nella barra di spostamento sinistra fare clic su **topologia** e quindi su **stato**.

4.  Nella pagina **stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui sono in esecuzione i servizi per cui si vogliono impedire le nuove sessioni e quindi fare clic su di esso.

5.  Fare clic su **azione**.

6.  Fare clic su **Impedisci nuove sessioni per tutti i servizi**.

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Per impedire nuove sessioni per un servizio specifico

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire il pannello di controllo di Lync Server.

3.  Nella barra di spostamento sinistra fare clic su **topologia** e quindi su **stato**.

4.  Nella pagina **stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui è in esecuzione il servizio che si vuole avviare o arrestare e quindi fare clic su di esso.

5.  Fare clic su **Proprietà**.

6.  Ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio per cui si vogliono impedire le nuove sessioni.

7.  Fare clic su **azione**.

8.  Fare clic su **Impedisci nuove sessioni per il servizio**.

9.  Fare clic su **Chiudi**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

