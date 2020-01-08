---
title: "Lync Server 2013: pianificare l'aspetto delle linee condivise"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 938bc723d9803acc955899a2b625f983d860b421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Pianificare l'aspetto della linea condivisa in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-03-21_

Leggere questo argomento per informazioni su come pianificare l'aspetto della linea condivisa (SLA) in Lync Server 2013, aggiornamento cumulativo aprile 2016.

L'aspetto delle linee condivise è una funzionalità di Lync Server 2013, aggiornamento cumulativo aprile 2016 per la gestione di più chiamate su un numero specifico denominato numero condiviso. SLA può configurare un utente di Lync abilitato per VoIP aziendale come numero condiviso con più linee per rispondere a più chiamate. Le chiamate non vengono effettivamente ricevute sul numero condiviso, ma vengono inoltrate agli utenti che agiscono come delegati per il numero condiviso. Uno qualsiasi dei delegati può prendere la chiamata mentre il resto dei delegati riceve una notifica al telefono su chi ha ricevuto la chiamata e quale linea si è occupata di conseguenza. Sia il numero di righe che i delegati sono configurabili per un numero condiviso in SLA. Inoltre, le opzioni avanzate, ad esempio BusyOption (cosa succede in una situazione in cui tutte le linee sono occupate) e MissedCallOption (il caso in cui nessuno dei delegati prende una chiamata), possono essere configurate anche per un numero condiviso.

SLA è supportato solo nei dispositivi telefonici seguenti (non è supportato per i client Lync su computer, telefoni cellulari o altri dispositivi):

  - Polycom VVX300 con aggiornamento firmware 5.4.1

  - Polycom VVX400 con aggiornamento firmware 5.4.1

  - Polycom VVX500 con aggiornamento firmware 5.4.1

  - Polycom VVX600 con aggiornamento firmware 5.4.1

SLA è una nuova funzionalità di Lync Server 2013, aggiornamento cumulativo aprile 2016.

Per informazioni sulla distribuzione di SLA, vedere [distribuire l'aspetto delle linee condivise in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).

<div>

## <a name="feature-list"></a>Elenco delle caratteristiche

La configurazione di un gruppo di SLA consente la seguente procedura:

  - Tutti i delegati del gruppo possono rispondere alle chiamate in ingresso allo stesso numero condiviso. Le chiamate possono essere basate su PSTN o SIP.

  - I delegati possono tenere e ritirare le chiamate.

  - I delegati possono trasferire le chiamate a un numero esterno al gruppo SLA.

  - I delegati possono vedere quante chiamate sono attualmente sul numero condiviso e visualizzare lo stato di ognuna di queste chiamate.

  - Puoi configurare un numero massimo di chiamate simultanee per il numero condiviso. È anche possibile impostare la modalità di gestione delle chiamate aggiuntive dopo il raggiungimento del massimo. Le chiamate in eccesso possono essere rifiutate con un segnale di occupato, inoltrato a un numero alternativo oppure inoltrato alla segreteria telefonica.

  - È possibile configurare la modalità di gestione delle chiamate perse (le chiamate non vengono raccolte dopo un determinato periodo di tempo). Se si Abilita la segreteria telefonica per l'identità del gruppo, le chiamate perse vengono automaticamente inoltrate alla segreteria telefonica. Se non si dispone della segreteria telefonica abilitata per l'identità del gruppo (numero condiviso), è possibile scegliere di rifiutare le chiamate perse con un segnale di occupato, inoltrato a un numero alternativo o disconnesso.

</div>

</div>

<span> </span>

</div>

</div>

</div>

