---
title: 'Lync Server 2013: riduzione della messaggistica istantanea indesiderata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5574930d6474a75ca4a35219df7cd2e3e2431b15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Riduzione della messaggistica istantanea indesiderata per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-12-05_

L'applicazione del filtro di messaggistica istantanea intelligente consente di proteggere la distribuzione di Microsoft Lync Server 2013 rispetto ai virus più comuni con riduzione minima dell'esperienza utente. Il filtro di protezione per messaggi istantanei offre le caratteristiche seguenti:

  - Filtro URL avanzato

  - Filtro trasferimento file avanzato

Utilizzare il filtro di protezione per messaggi istantanei per configurare filtri in modo da bloccare messaggi istantanei indesiderati o potenzialmente dannosi provenienti da endpoint sconosciuti esterni al firewall aziendale. Per configurare i filtri, è necessario definire i criteri da utilizzare per determinare gli elementi da bloccare, ad esempio i messaggi istantanei contenenti collegamenti ipertestuali e file con estensioni specifiche.

Prima di distribuire l'applicazione filtro messaggi di messaggistica istantanea intelligente, è necessario comprendere il modo in cui vengono applicate le opzioni di filtro quando i messaggi vengono instradati da un server Lync Server 2013 a un altro. Tali modalità sono coerenti e non dipendono dalla posizione in cui si trovano i server, ovvero se in una singola organizzazione o attraverso i confini di più organizzazioni. Questa coerenza si applica al modo in cui la nota personalizzata e il testo degli avvisi vengono inseriti nei messaggi e inviati tra server.

L'opzione di filtro consigliata consiste nel consentire i messaggi istantanei con collegamenti ipertestuali, ma nel richiedere al filtro di disabilitare il collegamento anteponendovi un carattere di sottolineatura. Se si sceglie questa opzione, è anche possibile scegliere di comporre una nota per gli utenti, visualizzata all'inizio di ogni messaggio istantaneo che contiene un collegamento ipertestuale.

Una seconda opzione di filtro consiste nel consentire i messaggi istantanei con collegamenti ipertestuali non modificati. Se si sceglie questa opzione, è anche possibile scegliere di comporre un avviso per gli utenti (scelta consigliata) da inserire in ogni messaggio.

Una terza opzione consiste nel bloccare tutti i messaggi istantanei contenenti collegamenti ipertestuali. Se si sceglie questa opzione, il server invia un avviso all'utente. È necessario scrivere questo avviso.

</div>

<span> </span>

</div>

</div>

</div>

