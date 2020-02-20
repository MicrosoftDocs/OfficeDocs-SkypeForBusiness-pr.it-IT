---
title: 'Lync Server 2013: pianificazione per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca0fd8edb6e2939b82711392c53b0e5bef3e7740
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a>Pianificazione per le conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-29_

Lync Server 2013 offre una vasta gamma di funzionalità di conferenza:

  - Web Conferencing, che include collaborazione su documenti, condivisione di applicazioni e condivisione del desktop. Lync Server 2013 utilizza Office Web Apps e il server Office Web Apps per gestire la condivisione e il rendering delle presentazioni di PowerPoint. Per informazioni dettagliate sull'installazione e sulla configurazione del server Office Web Apps, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - A/V Conferencing, che consente agli utenti di partecipare a conferenze audio o video in tempo reale senza dover utilizzare servizi esterni, come il servizio Microsoft Live Meeting o un ponte audio di terze parti

  - Conferenza telefonica con accesso esterno, che consente agli utenti di partecipare alla parte audio di una conferenza di Lync Server 2013 utilizzando un telefono PSTN senza dover utilizzare un provider di servizi di audioconferenza di terze parti.

  - IM Conferencing, per conferenza in cui più di due utenti comunicano in una singola sessione di messaggistica istantanea. Per informazioni dettagliate sulle conferenze di messaggistica istantanea, vedere [pianificazione di front end server, messaggistica istantanea e presenza in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).

Lync Server 2013 supporta sia le conferenze pianificate sia le conferenze estemporanee.

Quando si distribuisce Lync Server 2013, Front End Server, è possibile scegliere se distribuire anche le funzionalità di conferenza Web, A/V Conferencing e di conferenza telefonica con accesso esterno. Le funzionalità di conferenza di messaggistica istantanea vengono sempre distribuite automaticamente insieme alle funzionalità di conversazione di messaggistica istantanea nei server front end di Lync Server 2013.

<div>


> [!NOTE]  
> Se la distribuzione include riunioni organizzate utilizzando client Office Communicator 2007 R2 (inclusa la console di Live Meeting o il componente aggiuntivo per conferenze per Microsoft Office Outlook), le riunioni avranno le limitazioni seguenti dopo la migrazione a Lync Server 2013: 
> <UL>
> <LI>
> <P>Gli utenti della riunione non saranno in grado di utilizzare le funzionalità di collaborazione dati, tra cui la collaborazione dei documenti, la condivisione di applicazioni e la condivisione del desktop.</P>
> <LI>
> <P>Possono verificarsi problemi di stabilità poiché i client di Office Communicator 2007 R2 non sono supportati con Lync Server 2013.</P></LI></UL>Per evitare questi problemi, ripianificare le riunioni organizzate utilizzando client di Office Communicator 2007 R2 con Outlook 2010 o Outlook 2013 utilizzando il componente aggiuntivo per riunioni online per Lync 2010 o il componente aggiuntivo per riunioni online per Lync 2013.



</div>

Nelle sezioni che seguono vengono illustrati gli elementi necessari alla distribuzione dei vari tipi di funzionalità per conferenze, compresi il processo di pianificazione, i componenti, i requisiti hardware e software e il processo di distribuzione.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Panoramica delle conferenze in Lync Server 2013](lync-server-2013-overview-of-conferencing.md)

  - [Definizione dei requisiti per le conferenze in Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Componenti e topologie per le conferenze in Lync Server 2013](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Requisiti tecnici per le conferenze in Lync Server 2013](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Elenco di controllo di distribuzione per le conferenze in Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Supporto per riunioni di grandi dimensioni in Lync Server 2013](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

