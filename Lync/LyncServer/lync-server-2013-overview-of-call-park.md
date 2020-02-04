---
title: 'Lync Server 2013: Panoramica di Call Park'
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
ms.openlocfilehash: c5deeff873b37c0056bf03c598c39e448cba4379
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Panoramica di Call Park in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

L'applicazione Call Park di Lync Server 2013 consente agli utenti di VoIP aziendale di eseguire una delle operazioni seguenti:

  - Inserire una chiamata in attesa e quindi recuperare la chiamata dallo stesso telefono o da un altro telefono.

  - Inserire una chiamata in attesa per trasferirla in un reparto o in un'area generale, ad esempio in un reparto vendite o in un magazzino in cui è presente un telefono con area comune.

  - Mettere una chiamata in attesa e mantenere il telefono di risposta originale gratuito per altre chiamate.

Quando un utente parcheggia una chiamata, Lync Server trasferisce la chiamata a un numero temporaneo, detto *orbita*, in cui la chiamata viene mantenuta fino a quando non viene recuperata o il timeout viene riattivato. Lync Server invia l'orbita all'utente che ha parcheggiato la chiamata. Per recuperare la chiamata parcheggiata, l'utente può selezionare il numero dell'orbita oppure fare clic sul collegamento orbita o sul pulsante nella finestra di conversazione.

L'utente che ha parcheggiato una chiamata può segnalare a qualcuno di recuperare la chiamata usando un meccanismo esterno, ad esempio messaggistica istantanea (IM) o un sistema di paging, per comunicare il numero dell'orbita a qualcun altro. L'utente che ha parcheggiato la chiamata può uscire dalla finestra di conversazione per ricevere una notifica quando viene recuperata la chiamata.

Poiché gli intervalli di Orbit sono univoci a livello globale, è possibile recuperare le chiamate da qualsiasi sito di Lync Server o telefono PBX se il routing è configurato in modo appropriato. Se non si recupera la chiamata entro un periodo di tempo configurabile, la chiamata torna alla persona che l'ha parcheggiata. Se la persona non risponde alla risponderia, la chiamata viene trasferita a una destinazione di fallback, ad esempio a un operatore, se configurata. È possibile configurare il numero di volte in cui la chiamata squilla prima di essere trasferita da uno a dieci volte. Se non si risponde a una chiamata trasferita, la chiamata viene disconnessa. L'orbita viene liberata quando la chiamata viene recuperata o disconnessa.

Quando si distribuisce Call Park, è necessario riservare intervalli di numeri di interno per le chiamate di parcheggio. Queste estensioni devono essere estensioni virtuali: estensioni che non hanno un utente o un telefono assegnato. Si configura quindi la tabella Orbit di Call Park con gli intervalli di numeri di interno e si specifica quale servizio applicazione ospita l'applicazione di parcheggio di chiamata che gestisce ogni intervallo. Ogni pool Front end include una tabella di parcheggio di chiamata nel server back-end corrispondente usato per gestire le chiamate parcheggiate nel pool. L'elenco di intervalli orbit è archiviato in Central Management store e viene usato per instradare le orbite al pool di destinazione. Ogni pool di Lync Server in cui è distribuita e configurata l'applicazione Parcheggio di chiamata può avere uno o più intervalli di orbita. Gli intervalli di Orbit devono essere univoci a livello globale in tutta la distribuzione di Lync Server.

Si configurano anche altre impostazioni di Call Park, ad esempio dove vengono reindirizzate le chiamate se si verificano il timeout e se la persona del telefono sente la musica durante il parcheggio. È anche possibile specificare il file musicale da riprodurre mentre la chiamata è in attesa.

<div>


> [!NOTE]  
> I file musicali personalizzati per il parcheggio delle chiamate non vengono sottoposto a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e andranno perduti se i file caricati nel pool sono danneggiati, danneggiati o eliminati. Mantieni sempre una copia di backup separata dei file personalizzati di musica in attesa caricati per Call Park.



</div>

L'applicazione Call Park è un componente di Enterprise Voice. Quando si distribuisce VoIP aziendale, l'applicazione Call Park viene installata e attivata automaticamente. Prima di poter usare Call Park, tuttavia, l'amministratore di VoIP aziendale deve configurarlo e abilitarlo per gli utenti tramite il criterio vocale.

</div>

<span> </span>

</div>

</div>

</div>

