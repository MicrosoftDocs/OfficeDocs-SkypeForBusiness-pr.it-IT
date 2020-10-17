---
title: Impedire le sessioni per i servizi
description: Impedisci sessioni per i servizi.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a452f8091716daa0a15967e2a278e82c5bc8c4f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563692"
---
# <a name="prevent-sessions-for-services"></a>Impedire le sessioni per i servizi

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

È possibile utilizzare il pannello di controllo di Microsoft Lync Server 2010 per impedire nuove sessioni per tutti i servizi di Lync Server 2010 in esecuzione in un computer specifico o per impedire nuove sessioni per un servizio specifico di Lync Server 2010.

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>Per impedire nuove sessioni di tutti i servizi di Lync Server in un computer

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire il Pannello di controllo di Lync Server.

3.  Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.

4.  Nella pagina **Stato** ordinare l'elenco oppure cercare nell'elenco il computer in cui sono in esecuzione i servizi per cui si desidera impedire nuove sessioni, quindi fare clic su di esso.

5.  Fare clic su **Azione**.

6.  Fare clic su **Impedisci nuove sessioni per tutti i servizi**.

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Per impedire nuove sessioni per uno specifico servizio

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire il Pannello di controllo di Lync Server.

3.  Nella barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.

4.  Nella pagina **Stato** ordinare o scorrere l'elenco per trovare il computer in cui è in esecuzione il servizio che si desidera avviare o arrestare e quindi fare clic su di esso.

5.  Fare clic su **Proprietà**.

6.  Ordinare l'elenco dei servizi, se necessario, quindi fare clic sul servizio per cui si desidera impedire nuove sessioni.

7.  Fare clic su **Azione**.

8.  Fare clic su **Impedisci nuove sessioni per il servizio**.

9.  Fare clic su **Chiudi**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

