---
title: "Lync Server 2013: configurazione del supporto per l'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb83156d319db96a4c6ed79768193a24e5cc3e0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Configurazione del supporto per l'individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-21_

Il **servizio di individuazione automatica** servizi Web di Lync Server è stato pubblicato per la prima volta nell'aggiornamento cumulativo di lync Server 2010: novembre 2011. Questo aggiornamento è stato accompagnato dalla versione iniziale dei client di Lync mobile. Il servizio di individuazione automatica ha esposto i servizi di mobilità, noti come servizio MCX.

Il servizio di individuazione automatica funge da singola posizione per tutti i client per richiedere informazioni su quali servizi e funzionalità sono disponibili e su come contattare i Sevices tramite un nome di dominio completo o un riferimento per il localizzatore di risorse Web Uniform. L'individuazione automatica espone un certo numero di funzionalità e ogni client effettuerà richieste in base alle caratteristiche che il client può usare. Ad esempio, un client Lync 2013 Desktop utilizzerà autodiscvoer per determinare i servizi Web esterni, ma non userà i servizi di mobilità (MCX). Per definire e abilitare correttamente i client per l'uso delle funzionalità disponibili, gli scenari che consentono a un client di trovare e usare efficacemente le voci di individuazione automatica devono essere definiti. Per usare autodoscover, la distribuzione richiede che un proxy inverso pubblichi i servizi Web di Lync Server, che i record DNS siano configurati per risolvere le query DNS per il servizio di individuazione automatica di Lync Server e i servizi Web di Lync Server e che i servizi di certificazione sono configurati correttamente per lo scenario specifico.

<div>


> [!TIP]  
> Per informazioni tecniche sugli elementi di una richiesta/risposta di individuazione automatica, vedere informazioni sull' <A href="lync-server-2013-understanding-autodiscover.md">individuazione automatica in Lync Server 2013</A>.



</div>

Le informazioni e le tabelle seguenti definiscono, per scenario, le configurazioni (se presenti) che è necessario implementare per consentire l'uso completo ed efficace del servizio di individuazione automatica. Le informazioni contenute negli argomenti seguenti sono specifiche di Microsoft Lync Server 2013. Per informazioni su come pianificare la mobilità per Lync Server 2010, vedere [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113). Per distribuire la mobilità per Lync Server 2010, vedere[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurazione del DNS per l'individuazione automatica in Lync Server 2013](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Configurazione dei certificati per l'individuazione automatica in Lync Server 2013](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Configurazione di un proxy inverso per l'individuazione automatica in Lync Server 2013](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Configurazione dell'individuazione automatica in Lync Server 2013 per distribuzioni ibride](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

