---
title: "Lync Server 2013: configurazione della messaggistica unificata in Microsoft Exchange Server per l'utilizzo con Lync Server"
description: "Lync Server 2013: configurazione della messaggistica unificata in Microsoft Exchange Server per l'utilizzo con Lync Server."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53c303f0ae659536aafcbdfcd829ed236e35a0ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548242"
---
# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Configurazione della messaggistica unificata in Microsoft Exchange Server per l'utilizzo con Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-11_

<div>


> [!IMPORTANT]  
> Se si desidera utilizzare la messaggistica unificata di Exchange per fornire i servizi di risponditore automatico, Outlook Voice Access o operatori automatici per gli utenti di VoIP aziendale, leggere <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">pianificazione per l'integrazione della messaggistica unificata di Exchange in Lync Server 2013</A> nella documentazione relativa alla pianificazione e quindi seguire le istruzioni riportate in questa sezione.



</div>

Per configurare la messaggistica unificata di Exchange in modo che funzioni con VoIP aziendale, è necessario eseguire le attività seguenti:

  - Configurare i certificati nel server che esegue i servizi di messaggistica unificata di Exchange
    
    <div>
    

    > [!NOTE]  
    > Aggiungere tutti i server Accesso client e cassette postali a tutti i dial plan URI SIP di messaggistica unificata. In caso contrario, il routing delle chiamate in uscita non funzionerà come previsto.

    
    </div>

  - Creare uno o più dial plan URI SIP di messaggistica unificata, insieme ai numeri di telefono di accesso del Sottoscrittore, in base alle esigenze e quindi creare i dial plan di Lync Server corrispondenti.

  - Utilizzare lo script **exchucutil.ps1** per:
    
      - Creare gateway IP di messaggistica unificata.
    
      - Creare gruppi di risposta di messaggistica unificata.
    
      - Concedere l'autorizzazione Lync Server 2013 per leggere gli oggetti di servizi di dominio Active Directory di messaggistica unificata.

  - Creare un oggetto operatore automatico di messaggistica unificata.

  - Creare un oggetto di accesso sottoscrittore.

  - Creare un URI SIP per ogni utente e associare gli utenti a un dial plan URI SIP di messaggistica unificata.

<div>

## <a name="requirements-and-recommendations"></a>Requisiti e raccomandazioni

Prima di iniziare, la documentazione in questa sezione presuppone che siano stati distribuiti i ruoli di Exchange 2013 seguenti: accesso client e cassetta postale. In Microsoft Exchange Server 2013, la messaggistica unificata di Exchange viene eseguita come servizio su questi server.

Per informazioni dettagliate sulla distribuzione di Exchange 2013, vedere la libreria TechNet di Exchange 2013 all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)

Tenere inoltre presente quanto segue:

  - Se la messaggistica unificata di Exchange è installata in più foreste, è necessario eseguire i passaggi di integrazione di Exchange Server per ogni foresta di messaggistica unificata. Ogni foresta di messaggistica unificata, inoltre, deve essere configurata per considerare attendibile la foresta in cui è distribuito Lync Server 2013 e la foresta in cui è distribuito Lync Server 2013 deve essere configurata in modo da considerare attendibile ogni foresta di messaggistica unificata.

  - I passaggi di integrazione vengono eseguiti sui ruoli del server Exchange in cui sono in esecuzione i servizi di messaggistica unificata e sul server che esegue Lync Server 2013. È consigliabile eseguire i passaggi di integrazione della messaggistica unificata di Exchange Server prima di eseguire i passaggi di integrazione di Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Per sapere quali passaggi di integrazione vengono eseguiti nei server e in base ai quali i ruoli di amministratore, vedere <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo di distribuzione per l'integrazione della messaggistica unificata locale e Lync Server 2013</A>.

    
    </div>

Gli strumenti seguenti devono essere disponibili in ogni server che esegue la messaggistica unificata di Exchange:

  - Exchange Management Shell

  - Script **exchucutil.ps1**, che consente di eseguire le attività seguenti:
    
      - Crea un gateway IP di messaggistica unificata per ogni Lync Server 2013.
    
      - Creazione di un gruppo di risposta per ogni gateway. L'identificatore pilota di ogni gruppo di risposta specifica il dial plan URI SIP di messaggistica unificata utilizzato dal pool Front end o dal server Standard Edition associato al gateway.
    
      - Concede all'autorizzazione Lync Server 2013 la lettura degli oggetti di messaggistica unificata di Exchange in servizi di dominio Active Directory.

</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Configurare i certificati nel server che esegue la messaggistica unificata di Microsoft Exchange Server](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

