---
title: 'Lync Server 2013: Percorsi di migrazione dei server supportati e scenari di coesistenza'
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
ms.openlocfilehash: 1b16b0c92954c004aa04b9cc665786badb9bf632
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Percorsi di migrazione dei server supportati e scenari di coesistenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-16_

Lync Server 2013 supporta la migrazione da una delle opzioni seguenti:

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

La migrazione da un ambiente in cui sono in uso entrambe le versioni precedenti non è supportata. La migrazione dalle versioni precedenti, ad esempio Microsoft Office Communications Server 2007 o Live Communications Server 2005, non è supportata. Se la distribuzione precedente includeva la chat di gruppo, è necessario eseguirne la migrazione separatamente.

<div>

## <a name="migration-methods"></a>Metodi di migrazione

È supportata la migrazione di tutte le topologie e i ruoli del server di Lync Server. È possibile eseguire la migrazione da una topologia a una topologia diversa, ad esempio dal server Standard Edition al server Enterprise Edition.

Lync Server 2013 supporta solo il metodo di migrazione seguente:

  - <span></span>  
    **Migrazione affiancata.** Nella migrazione affiancata Lync Server 2013 viene distribuito insieme a una distribuzione di Microsoft Lync Server 2010 o Office Communications Server 2007 R2 esistente e quindi si trasferiscono le operazioni nei nuovi server e si spostano gli utenti in Lync Server 2013. Questo metodo richiede piattaforme server aggiuntive, inclusi hardware e software, durante la migrazione e i nomi di sistema e i nomi di pool sono diversi nella nuova configurazione. Se è necessario eseguire il rollback alla versione precedente, è possibile spostare di nuovo le operazioni nei server precedenti.

La migrazione tra foreste di servizi di dominio Active Directory non è supportata.

Il percorso di migrazione consigliato è un approccio graduale. Per informazioni dettagliate sulla migrazione da una versione precedente, inclusa l'appropriata fase di distribuzione dei componenti, vedere gli argomenti seguenti nella documentazione relativa alla migrazione:

  - [Migrazione da Lync Server 2010 a Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migrazione da Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migrazione da Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat al server chat persistente di Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>Scenari di coesistenza

Lync Server 2013 può coesistere con i componenti di una distribuzione di Lync Server 2010 o di una distribuzione di Office Communications Server 2007 R2. La distribuzione simultanea di Lync Server 2013 con Lync Server 2010 e Office Communications Server 2007 R2 (distribuzione simultanea di tutte e tre le versioni) non è supportata.

Durante una migrazione a fasi in cui una distribuzione di Lync Server 2010 o Office Communications Server 2007 R2 precedente coesiste temporaneamente con la nuova distribuzione di Lync Server 2013, il supporto per il routing di versioni miste è limitato. Per informazioni dettagliate, vedere la documentazione relativa alla migrazione.

È necessario usare computer separati e distinti con Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 per le istanze di database di Lync Server 2013. Non è possibile usare la stessa istanza di SQL Server per un pool di front end di Lync Server 2013 che si usa per un pool di front end di Lync Server 2010 o Office Communications Server 2007 R2. Se si definisce e si configura Lync Server 2013 in Generatore di topologia per una distribuzione che ha già implementato Lync Server 2010 o Office Communications Server 2007 R2, generatore di topologie non consentirà di definire un'istanza di un server Lync 2013 già in uso in la topologia.

Generatore di topologia visualizzerà il messaggio seguente per segnalare il problema: "il nome di \[dominio completo di SQL\] server del server contiene già un ruolo di hosting dell'istanza SQL" archivio utenti ".

<div>


> [!NOTE]  
> Se si intende distribuire ruoli del server nuovi alla distribuzione di Lync Server 2013, è consigliabile prima di tutto aggiornare la distribuzione esistente, come descritto nella documentazione relativa alla migrazione e nella documentazione di distribuzione, quindi distribuire i nuovi ruoli del server come descritto in documentazione sulla pianificazione e la documentazione sulla distribuzione. Se si esegue la migrazione di una versione precedente di Group Chat, eseguire la migrazione per ultima, dopo aver completato il processo di migrazione di tutti gli altri componenti da Lync Server 2010 o Office Communications Server 2007 R2.



</div>

Per specifici requisiti di coesistenza e altri dettagli sulla coesistenza e la migrazione dei componenti di Lync Server 2010 o Office Communications Server 2007 R2 e Lync Server 2013, vedere [migrazione da Lync server 2010 a Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) e [migrazione da Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) nella documentazione di migrazione. Per informazioni dettagliate sul supporto della versione mista per i client, vedere [client supportati da distribuzioni precedenti in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

