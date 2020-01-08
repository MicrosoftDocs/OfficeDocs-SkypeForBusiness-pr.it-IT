---
title: 'Lync Server 2013: Pianificazione dei servizi di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2aff3eef21ca150f4ad6fc9bb2358c2ac81680fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a>Pianificazione dei servizi di conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-29_

Lync Server 2013 offre una vasta gamma di funzionalità di conferenza:

  - Web Conferencing, che include la collaborazione tra documenti, condivisione applicazioni e condivisione desktop. Lync Server 2013 usa Office Web Apps e il server Office Web Apps per gestire la condivisione e il rendering delle presentazioni di PowerPoint. Per informazioni dettagliate sull'installazione e la configurazione del server Office Web Apps, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - Servizi di conferenza audio/video (A/V), che consente agli utenti di avere conferenze audio o video in tempo reale senza la necessità di un servizio esterno, ad esempio Microsoft Live Meeting Service o un bridge audio di terze parti.

  - Servizi di conferenza telefonica con accesso esterno, che consente agli utenti di partecipare alla parte audio di una conferenza di Lync Server 2013 utilizzando un telefono PSTN (Public Switched Telephone Network) senza richiedere un provider di audioconferenza di terze parti.

  - Servizi di conferenza di messaggistica istantanea, in cui più di due parti comunicano in una singola sessione di messaggistica istantanea. Per informazioni dettagliate sui servizi di conferenza di messaggistica istantanea, vedere [pianificazione dei server front-end, della messaggistica immediata e della presenza in Lync server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).

Lync Server 2013 supporta sia le conferenze pianificate che le conferenze estemporanee.

Quando si distribuisce Lync Server 2013, Front End Server, è possibile scegliere se distribuire anche le funzionalità di conferenza Web, conferenze A/V e servizi di conferenza telefonica con accesso esterno. Le funzionalità di conferenza di messaggistica istantanea vengono sempre distribuite automaticamente insieme alle funzionalità di conversazione di messaggistica istantanea nei server front end di Lync Server 2013.

<div>


> [!NOTE]  
> Se la distribuzione include riunioni organizzate con client di Office Communicator 2007 R2 (inclusa la console Live Meeting o il componente aggiuntivo conferenza per Microsoft Office Outlook), le riunioni avranno le seguenti limitazioni dopo la migrazione a Lync Server 2013: 
> <UL>
> <LI>
> <P>Gli utenti della riunione non saranno in grado di usare le caratteristiche di collaborazione dei dati, tra cui la collaborazione tra documenti, la condivisione delle applicazioni e la condivisione del desktop.</P>
> <LI>
> <P>I problemi di stabilità possono verificarsi perché i client di Office Communicator 2007 R2 non sono supportati con Lync Server 2013.</P></LI></UL>Per evitare questi problemi, ripianificare le riunioni organizzate con i client Office Communicator 2007 R2 con Outlook 2010 o Outlook 2013 usando il componente aggiuntivo riunione online per Lync 2010 o il componente aggiuntivo riunione online per Lync 2013.



</div>

Le sezioni seguenti descrivono le informazioni necessarie per distribuire i vari tipi di funzionalità di conferenza, inclusi il processo di pianificazione, i componenti, i requisiti hardware e software e il processo di distribuzione.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Panoramica delle conferenze in Lync Server 2013](lync-server-2013-overview-of-conferencing.md)

  - [Definizione dei requisiti per le conferenze in Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Componenti e topologie per le conferenze in Lync Server 2013](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Requisiti tecnici per le conferenze in Lync Server 2013](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Elenco di controllo di distribuzione per le conferenze in Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Supporto per le riunioni di grandi dimensioni in Lync Server 2013](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

