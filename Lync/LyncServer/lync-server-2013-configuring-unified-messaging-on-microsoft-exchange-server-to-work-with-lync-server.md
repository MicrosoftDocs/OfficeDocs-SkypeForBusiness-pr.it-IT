---
title: "Lync Server 2013: Configurazione della messaggistica unificata in Microsoft Exchange Server per l'interazione con Lync Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461d822862e837879f1feb2d3f980b816aae5280
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Configurazione della messaggistica unificata in Microsoft Exchange Server per l'interazione con Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-11_

<div>


> [!IMPORTANT]  
> Se si vuole usare la messaggistica unificata di Exchange (UM) per fornire risposte alle chiamate, Outlook Voice Access o servizi di operatore automatico per gli utenti di VoIP aziendale, leggere la <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">pianificazione per l'integrazione della messaggistica unificata di Exchange in Lync Server 2013</A> nella documentazione di pianificazione e quindi seguire le istruzioni in questa sezione.



</div>

Per configurare la messaggistica UNIFICAta di Exchange per l'utilizzo di Enterprise Voice, è necessario eseguire le attività seguenti:

  - Configurare i certificati nel server che gestisce i servizi di messaggistica UNIFICAta di Exchange
    
    <div>
    

    > [!NOTE]  
    > Aggiungere tutti i server di accesso client e cassette postali a tutti i dial plan URI SIP di messaggistica unificata. In caso contrario, il routing delle chiamate in uscita non funziona come previsto.

    
    </div>

  - Creare uno o più piani di dial URI SIP di messaggistica unificata, insieme ai numeri di telefono di accesso del Sottoscrittore, in base alle esigenze e quindi creare corrispondenti piani di chiamata di Lync Server.

  - USA lo script **exchucutil. ps1** per:
    
      - Creare gateway IP di messaggistica unificata.
    
      - Creare gruppi di risposta di messaggistica unificata.
    
      - Concedere l'autorizzazione Lync Server 2013 per la lettura degli oggetti servizi di dominio Active Directory di messaggistica unificata.

  - Creare un oggetto operatore automatico di messaggistica unificata.

  - Creare un oggetto di accesso del Sottoscrittore.

  - Crea un URI SIP per ogni utente e associa gli utenti a un dial plan di URI SIP di messaggistica unificata.

<div>

## <a name="requirements-and-recommendations"></a>Requisiti e suggerimenti

Prima di iniziare, la documentazione in questa sezione presuppone che siano stati distribuiti i ruoli di Exchange 2013 seguenti: accesso client e cassetta postale. In Microsoft Exchange Server 2013 la messaggistica unificata di Exchange viene eseguita come servizio in questi server.

Per informazioni dettagliate sulla distribuzione di Exchange 2013, vedere la raccolta di Exchange 2013 TechNet all'indirizzo[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

Tenere inoltre presente quanto segue:

  - Se la messaggistica unificata di Exchange è installata in più foreste, è necessario eseguire la procedura di integrazione di Exchange Server per ogni foresta di messaggistica unificata. Ogni foresta di messaggistica unificata deve inoltre essere configurata per considerare attendibile la foresta in cui è distribuito Lync Server 2013 e la foresta in cui è distribuito Lync Server 2013 deve essere configurata in modo da considerare attendibile ogni foresta di messaggistica unificata.

  - I passaggi di integrazione vengono eseguiti nei ruoli del server Exchange in cui sono in esecuzione i servizi di messaggistica unificata e nel server che esegue Lync Server 2013. È consigliabile eseguire i passaggi di integrazione della messaggistica unificata di Exchange Server prima di eseguire i passaggi di integrazione di Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Per scoprire quali passaggi di integrazione vengono eseguiti in quali server e per quali ruoli di amministratore, vedere <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo di distribuzione per l'integrazione di messaggistica unificata locale e Lync Server 2013</A>.

    
    </div>

Gli strumenti seguenti devono essere disponibili in ogni server che gestisce la messaggistica unificata di Exchange:

  - Exchange Management Shell

  - Lo script **exchucutil. ps1**, che esegue le attività seguenti:
    
      - Crea un gateway IP di messaggistica unificata per ogni Lync Server 2013.
    
      - Crea un gruppo di ricerca per ogni gateway. L'identificatore pilota di ogni gruppo di ricerca specifica il dial plan URI SIP di messaggistica unificata usato dal pool Front-end o dal server Standard Edition associato al gateway.
    
      - Concede l'autorizzazione Lync Server 2013 per la lettura degli oggetti della messaggistica unificata di Exchange in servizi di dominio Active Directory.

</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurare i certificati nel server in cui è in uso la messaggistica unificata di Microsoft Exchange Server](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

