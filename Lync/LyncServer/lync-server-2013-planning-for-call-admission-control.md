---
title: 'Lync Server 2013: pianificazione del controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa0d3173b3316d4e4dff704402da94c20aa2c9f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Pianificazione del controllo di ammissione di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Per le applicazioni per comunicazioni unificate basate sul protocollo IP, ad esempio la telefonia, le comunicazioni video e la condivisione di applicazioni, la larghezza di banda disponibile delle reti aziendali non è considerata generalmente un fattore di limitazione negli ambienti LAN. Nei collegamenti WAN tra i siti tuttavia la larghezza di banda della rete può essere limitata. Quando si verifica un eccesso di sottoscrizione di un collegamento WAN da parte del traffico di rete, per risolvere il problema di congestione vengono utilizzati i meccanismi correnti, ad esempio l'accodamento, il buffering e l'eliminazione dei pacchetti. Il traffico in eccesso in genere viene ritardato finché non si risolve la congestione di rete o, se necessario, finché non viene eliminato il traffico. Per il traffico di dati convenzionali, in questi casi è possibile ripristinare il client di ricezione. Per il traffico in tempo reale, ad esempio le comunicazioni unificate, non è possibile risolvere la congestione in questo modo, poiché questo tipo di traffico è sensibile sia alla latenza che alla perdita di pacchetti. La congestione nella WAN può determinare una qualità percepita dagli utenti (QoE) scadente. Per il traffico in tempo reale in condizioni di congestione, è meglio rifiutare le chiamate anziché consentire connessioni di qualità scadente.

Il Servizio Controllo di ammissione di chiamata determina se è disponibile una larghezza di banda di rete sufficiente per stabilire una sessione in tempo reale di qualità accettabile. In Lync Server 2013, CAC controlla il traffico in tempo reale solo per l'audio e il video, ma non influisce sul traffico dei dati. Se il percorso WAN predefinito non dispone della larghezza di banda necessaria, il servizio Controllo di ammissione di chiamata può tentare di instradare la chiamata tramite un percorso Internet o la rete PSTN (Public Switched Telephone Network). Il servizio di controllo di ammissione è disponibile solo in Lync Server.

In questa sezione viene descritta la funzionalità di Controllo di ammissione di chiamata e viene illustrata la relativa pianificazione.

<div>


> [!NOTE]  
> Lync Server dispone di tre funzionalità di VoIP aziendale avanzate: controllo di ammissione di chiamata (CAC), servizi di emergenza (E9-1-1) e bypass multimediale. Per una panoramica delle informazioni di pianificazione comuni a tutte e tre queste caratteristiche, vedere <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Panoramica del controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Esempio: raccolta dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Componenti e topologie per il servizio di controllo di ammissione in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Procedure consigliate per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Checklist di distribuzione per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

