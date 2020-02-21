---
title: "Lync Server 2013: configurazione del supporto per l'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bbb9007562dfecdc4f38b6cf8ac3f1579094ed6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Configurazione del supporto per l'individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-21_

Il **servizio di individuazione automatica** dei servizi Web di Lync Server è stato introdotto per la prima volta nell'aggiornamento cumulativo di lync Server 2010: novembre 2011. Questo aggiornamento è stato accompagnato dalla versione iniziale dei client di Lync mobile. Il servizio di individuazione automatica ha esposto i servizi per dispositivi mobili, noto come servizio di MCX.

Il servizio di individuazione automatica funge da singola posizione per tutti i client per richiedere informazioni su quali servizi e funzionalità sono disponibili e su come contattare i sevizi, in base a un nome di dominio completo o a un riferimento a un Uniform Resource Locator del Web. L'individuazione automatica espone numerose funzionalità e ogni client eseguirà le richieste in base alle caratteristiche che il client può utilizzare. Ad esempio, un client Lync 2013 Desktop utilizzerà autodiscvoer per determinare i servizi Web esterni, ma non utilizzerà i servizi per dispositivi mobili (MCX). Per definire correttamente e consentire ai client di utilizzare le funzionalità disponibili, è necessario definire gli scenari che consentono a un client di trovare e utilizzare in modo efficace le voci di individuazione automatica. Per utilizzare autodoscover, la distribuzione richiede che un proxy inverso pubblichi i servizi Web di Lync Server, che i record DNS siano configurati per la risoluzione delle query DNS per il servizio di individuazione automatica di Lync Server e per i servizi Web di Lync Server e che i servizi certificati sono configurati correttamente per lo scenario specifico.

<div>


> [!TIP]  
> Per informazioni tecniche su cosa fare gli elementi all'interno della richiesta/risposta di individuazione automatica, vedere <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.



</div>

Le seguenti informazioni e tabelle definiscono, per ogni scenario, quali configurazioni (se presenti) è necessario implementare per fornire l'utilizzo completo ed efficace del servizio di individuazione automatica. Le informazioni contenute negli argomenti seguenti sono specifiche di Microsoft Lync Server 2013. Se si cercano indicazioni su come pianificare la mobilità per Lync Server 2010, vedere [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113). Per distribuire la mobilità per Lync Server 2010, vedere[https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Configurazione del DNS per l'individuazione automatica in Lync Server 2013](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Configurazione dei certificati per l'individuazione automatica in Lync Server 2013](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Configurazione di un proxy inverso per l'individuazione automatica in Lync Server 2013](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Configurazione dell'individuazione automatica in Lync Server 2013 per le distribuzioni ibride](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

