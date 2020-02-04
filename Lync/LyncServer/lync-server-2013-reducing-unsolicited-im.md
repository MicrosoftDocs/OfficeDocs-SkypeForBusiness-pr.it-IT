---
title: 'Lync Server 2013: Riduzione della messaggistica istantanea indesiderata'
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
ms.openlocfilehash: d0f8326d6fa9f85b202e0ea2dcbe3fed63a723aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Riduzione della messaggistica istantanea indesiderata per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-12-05_

L'applicazione di filtro di messaggistica istantanea intelligente consente di proteggere la distribuzione di Microsoft Lync Server 2013 con i virus più comuni con una degradazione minima dell'esperienza utente. Il filtro ISTANTANEo intelligente offre gli elementi seguenti:

  - Filtro URL avanzato

  - Filtro di trasferimento file avanzato

Usare il filtro istantaneo intelligente per configurare i filtri per bloccare i messaggi istantanei non richiesti o potenzialmente nocivi da endpoint sconosciuti esterni al firewall aziendale. I filtri vengono configurati specificando i criteri da usare per determinare gli elementi da bloccare, ad esempio i messaggi istantanei contenenti collegamenti ipertestuali e file con estensioni specifiche.

Prima di distribuire l'applicazione di filtro messaggi ISTANTANEi intelligente, è necessario capire in che modo vengono applicate le opzioni di filtro quando i messaggi vengono instradati da un server di Lync Server 2013 a un altro. Il modo in cui queste opzioni di filtro vengono applicate è coerente, indipendentemente dal fatto che i server si trovino in un'unica organizzazione o in tutti i confini aziendali. Questa coerenza si applica al modo in cui l'avviso personalizzato e i testi di avviso vengono inseriti nei messaggi e inviati attraverso i server.

L'opzione di filtro consigliata consiste nel consentire messaggi istantanei con collegamenti ipertestuali, ma richiede il filtro istantaneo intelligente per disabilitare il collegamento inserendo un carattere di sottolineatura. Se si sceglie questa opzione, è disponibile l'opzione aggiuntiva per comporre un avviso per gli utenti che vengono visualizzati all'inizio di ogni messaggio istantaneo che contiene un collegamento ipertestuale.

Una seconda opzione di filtro consiste nel consentire i messaggi istantanei con collegamenti ipertestuali non modificati. Se si sceglie questa opzione, è presente l'opzione aggiuntiva (scelta consigliata) per comporre un avviso per gli utenti inseriti in ogni messaggio.

Una terza opzione consiste nel bloccare tutti i messaggi istantanei che contengono collegamenti ipertestuali. Se si sceglie questa opzione, il server invia un avviso all'utente. È necessario scrivere questo avviso.

</div>

<span> </span>

</div>

</div>

</div>

