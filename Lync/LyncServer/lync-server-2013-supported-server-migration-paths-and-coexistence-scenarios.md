---
title: 'Lync Server 2013: percorsi di migrazione del server supportati e scenari di coesistenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ed7689931cf917c77527266918832ead8bd0a27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523973"
---
# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Percorsi di migrazione del server supportati e scenari di coesistenza in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-16_

Lync Server 2013 supporta la migrazione da una delle seguenti operazioni:

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

La migrazione da un ambiente che esegue entrambe le versioni precedenti non è supportata. La migrazione da versioni precedenti, ad esempio Microsoft Office Communications Server 2007 o Live Communications Server 2005, non è supportata. Se la distribuzione precedente includeva Group Chat, è necessario eseguirne la migrazione separatamente.

<div>

## <a name="migration-methods"></a>Metodi di migrazione

È supportata la migrazione di tutte le topologie di Lync Server e i ruoli del server. È possibile eseguire la migrazione da una topologia a un'altra, incluso da un server Standard Edition a un server Enterprise Edition.

Lync Server 2013 supporta solo il metodo di migrazione seguente:

  - <span></span>  
    **Migrazione side-by-side** Nella migrazione affiancata, Lync Server 2013 viene distribuito insieme a una distribuzione di Microsoft Lync Server 2010 o Office Communications Server 2007 R2 esistente e quindi si trasferiscono le operazioni nei nuovi server e si spostano gli utenti in Lync Server 2013. Questo metodo richiede l'uso di ulteriori piattaforme server, inclusi hardware e software, durante la migrazione e i nomi dei sistemi e dei pool sono diversi nella nuova configurazione. Se è necessario ripristinare la versione precedente, è possibile spostare di nuovo le operazioni nei server precedenti.

La migrazione tra foreste di servizi di dominio Active Directory non è supportata.

Il metodo di migrazione consigliato è di tipo incrementale. Per informazioni dettagliate sulla migrazione da una versione precedente, inclusa la tempistica appropriata per la distribuzione dei componenti, vedere gli argomenti seguenti nella documentazione relativa alla migrazione:

  - [Migrazione da Lync Server 2010 a Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migrazione da Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migrazione da Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat al server chat persistente di Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>Scenari di coesistenza

Lync Server 2013 può coesistere con i componenti di una distribuzione di Lync Server 2010 o di una distribuzione di Office Communications Server 2007 R2. La distribuzione simultanea di Lync Server 2013 con Lync Server 2010 e Office Communications Server 2007 R2 (distribuzione simultanea di tutte e tre le versioni) non è supportata.

Durante una migrazione in fasi in cui una distribuzione di Lync Server 2010 o Office Communications Server 2007 R2 precedente coesiste temporaneamente con la nuova distribuzione di Lync Server 2013, il supporto per il routing di versioni miste è limitato. Per informazioni dettagliate, vedere la documentazione relativa alla migrazione.

È necessario utilizzare computer separati e distinti che eseguono Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 per le istanze di database di Lync Server 2013. Non è possibile utilizzare la stessa istanza di SQL Server per un pool Front End di Lync Server 2013 utilizzato per un pool Front End di Lync Server 2010 o Office Communications Server 2007 R2. Se si definisce e si configura Lync Server 2013 in Generatore di topologie per una distribuzione che dispone già di Lync Server 2010 o Office Communications Server 2007 R2 distribuito, generatore di topologie non consentirà di definire un'istanza di Lync Server 2013 già in uso nella topologia.

Il generatore di topologie visualizzerà il seguente messaggio per informare l'utente del problema: "l' \[ FQDN di SQL Server del server \] contiene già un ruolo di hosting dell'istanza di SQL ' archivio utenti '".

<div>


> [!NOTE]  
> Se si intende distribuire i ruoli del server nuovi per la distribuzione di Lync Server 2013, è consigliabile prima aggiornare la distribuzione esistente come descritto nella documentazione relativa alla migrazione e la documentazione relativa alla distribuzione e quindi distribuire i nuovi ruoli del server come descritto nella documentazione relativa alla pianificazione e alla distribuzione. Se si esegue la migrazione di una versione precedente di Group Chat, eseguirne la migrazione per ultima, dopo aver completato il processo di migrazione di tutti gli altri componenti da Lync Server 2010 o Office Communications Server 2007 R2.



</div>

Per i requisiti specifici di coesistenza e altri dettagli sulla coesistenza e la migrazione dei componenti di Lync Server 2010 o Office Communications Server 2007 R2 e Lync Server 2013, vedere [Migration from Lync server 2010 to Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) nella documentazione relativa alla migrazione. Per informazioni dettagliate sul supporto di versioni miste per i client, vedere [client supportati dalle distribuzioni precedenti in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

