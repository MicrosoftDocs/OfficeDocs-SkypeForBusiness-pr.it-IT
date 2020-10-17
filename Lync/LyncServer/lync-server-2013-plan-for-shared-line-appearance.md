---
title: "Lync Server 2013: pianificare l'aspetto delle linee condivise"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a79c053098d1fbd3ba364a12b18fb335a0687e46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519833"
---
# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Pianificare l'aspetto delle linee condivise in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-03-21_

Leggere questo argomento per informazioni su come effettuare la pianificazione di SLA (Shared Line Appearance) in Lync Server 2013, aggiornamento cumulativo aprile 2016.

L'aspetto delle linee condivise è una funzionalità di Lync Server 2013, aggiornamento cumulativo di aprile 2016 per la gestione di più chiamate su un numero specifico denominato numero condiviso. SLA è in grado di configurare qualsiasi utente Lync abilitato per VoIP aziendale come numero condiviso con più righe per rispondere a più chiamate. Le chiamate non vengono effettivamente ricevute sul numero condiviso, ma vengono inoltrate agli utenti che agiscono come delegati per il numero condiviso. Uno qualsiasi dei delegati può prendere la chiamata mentre il resto dei delegati riceve una notifica sul telefono di chi ha ricevuto la chiamata e quale linea si è occupata di conseguenza. Sia il numero di righe che i delegati sono configurabili per un numero condiviso in SLA. Inoltre, le opzioni avanzate, come BusyOption (cosa succede in una situazione in cui tutte le linee sono occupate) e MissedCallOption (il caso in cui nessuno dei delegati prelevare una chiamata), possono essere configurate anche per un numero condiviso.

SLA è supportato solo sui seguenti dispositivi telefonici (non è supportato per i client Lync su computer, telefoni cellulari o altri dispositivi):

  - Polycom VVX300 with Firmware Update 5.4.1

  - Polycom VVX400 with Firmware Update 5.4.1

  - Polycom VVX500 with Firmware Update 5.4.1

  - Polycom VVX600 with Firmware Update 5.4.1

SLA è una nuova funzionalità di Lync Server 2013, aggiornamento cumulativo aprile 2016.

Per informazioni sulla distribuzione di SLA, vedere [deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).

<div>

## <a name="feature-list"></a>Elenco funzionalità

La configurazione di un gruppo di SLA consente di abilitare le seguenti operazioni:

  - Tutti i delegati del gruppo possono rispondere alle chiamate in ingresso allo stesso numero condiviso. Le chiamate possono essere basate su PSTN o SIP.

  - I delegati possono conservare e raccogliere le chiamate.

  - I delegati possono trasferire le chiamate a un numero esterno al gruppo di SLA.

  - I delegati possono vedere quante chiamate sono attualmente sul numero condiviso e visualizzare lo stato di ognuna di queste chiamate.

  - È possibile configurare un numero massimo di chiamate simultanee per il numero condiviso. È inoltre possibile impostare il modo in cui si desidera che vengano gestite altre chiamate dopo che è stato raggiunto il limite massimo. Le chiamate in eccesso possono essere rifiutate con un segnale di occupato, inoltrate a un numero alternativo o inoltrate alla segreteria telefonica.

  - È possibile configurare la modalità di gestione delle chiamate senza risposta (chiamate non ritirate dopo un determinato periodo di tempo). Se si Abilita la segreteria telefonica per l'identità del gruppo, le chiamate perse passano automaticamente alla segreteria telefonica. Se non si dispone della segreteria telefonica abilitata per l'identità del gruppo (numero condiviso), è possibile scegliere se le chiamate perse devono essere rifiutate con un segnale di occupato, inoltrato a un numero alternativo o disconnesso.

</div>

</div>

<span> </span>

</div>

</div>

</div>

