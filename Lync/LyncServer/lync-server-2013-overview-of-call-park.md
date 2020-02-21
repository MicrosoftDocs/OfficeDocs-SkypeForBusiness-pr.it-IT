---
title: 'Lync Server 2013: Panoramica del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1624042b07bc024d837e55ffac402cb2f158922f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Panoramica del parcheggio di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

L'applicazione di parcheggio di chiamata Lync Server 2013 consente agli utenti di VoIP aziendale di eseguire una delle operazioni seguenti:

  - Mettere una chiamata in attesa e quindi recuperare la chiamata dallo stesso telefono o da uno diverso.

  - Mettere una chiamata in attesa per trasferirla a un altro reparto o a un'altra area generale, ad esempio a un reparto vendite o un magazzino in cui è presente un telefono di area comune.

  - Mettere una chiamata in attesa e mantenere libero per altre chiamate il telefono originale da cui si è risposto alla chiamata.

Quando un utente effettua una chiamata, Lync Server trasferisce la chiamata a un numero temporaneo, denominato *orbita*, in cui la chiamata viene mantenuta fino a quando non viene recuperata o non viene rilasciata. Lync Server invia l'orbita all'utente che ha parcheggiato la chiamata. Per recuperare la chiamata parcheggiata, l'utente può comporre il codice orbit o fare clic sul collegamento o il pulsante del codice orbit nella finestra Conversazione.

L'utente che ha eseguito il parcheggio di una chiamata può indicare a qualcun altro di recuperare la chiamata utilizzando un meccanismo esterno, ad esempio un sistema di messaggistica istantanea o di paging, per comunicare il codice orbit a un altro utente. L'utente che ha eseguito il parcheggio della chiamata può lasciare aperta la finestra Conversazione per ricevere una notifica quando la chiamata viene recuperata.

Poiché gli intervalli di Orbit sono univoci a livello globale, è possibile recuperare le chiamate da qualsiasi sito Lync Server o telefono PBX se il routing è configurato in modo appropriato. Se nessuno recupera la chiamata entro una quantità di tempo configurabile, la chiamata viene nuovamente indirizzata alla persona che ne ha eseguito il parcheggio. Se tale persona non risponde alla richiamata, la chiamata viene trasferita a una destinazione di fallback, ad esempio a un operatore, se questa impostazione è configurata. È possibile configurare da uno a dieci il numero di volte per cui consentire una richiamata prima che la chiamata venga trasferita. Se nessuno risponde a una chiamata trasferita, questa viene disconnessa. Il codice orbit viene liberato quando la chiamata viene recuperata o disconnessa.

Quando si distribuisce il parcheggio di chiamata, è necessario riservare intervalli di numeri di interno (codici orbit) per il parcheggio delle chiamate. Tali numeri devono essere interni virtuali, ovvero numeri a cui non sono assegnati utenti o telefoni. È quindi necessario configurare la tabella dei codici orbit del parcheggio di chiamata con gli intervalli di interni e specificare il servizio applicazione che ospita l'applicazione Parcheggio di chiamata che gestisce ogni intervallo. Ogni pool Front End include una tabella di parcheggio di chiamata nel server di back-end corrispondente utilizzato per gestire le chiamate parcheggiate nel pool. L'elenco degli intervalli di Orbit è memorizzato nell'archivio di gestione centrale e viene utilizzato per instradare le orbite al pool di destinazione. Ogni pool di Lync Server in cui viene distribuita e configurata l'applicazione Parcheggio di chiamata può disporre di uno o più intervalli di Orbit. Gli intervalli di Orbit devono essere univoci a livello globale nella distribuzione di Lync Server.

È anche possibile configurare altre impostazioni di parcheggio chiamata, ad esempio la destinazione di reindirizzamento delle chiamate in caso di timeout e se usare la musica di attesa durante il parcheggio. È anche possibile specificare il file musicale da riprodurre mentre la chiamata è in attesa.

<div>


> [!NOTE]  
> I file musicali personalizzati per il parcheggio di chiamata non vengono sottoposti a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e andranno persi se i file caricati nel pool sono danneggiati, danneggiati o eliminati. Mantenere sempre una copia di backup distinta dei file di musica di attesa personalizzati caricati per il parcheggio chiamate.



</div>

L'applicazione Parcheggio di chiamata è un componente di VoIP aziendale. Quando si distribuisce VoIP aziendale, l'applicazione Parcheggio di chiamata viene installata e attivata automaticamente. Prima di poter utilizzare l'applicazione Parcheggio di chiamata, tuttavia, l'amministratore di VoIP aziendale deve configurarla e abilitarla per gli utenti tramite criteri vocali.

</div>

<span> </span>

</div>

</div>

</div>

