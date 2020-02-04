---
title: 'Lync Server 2013: Pianificazione del servizio Controllo di ammissione di chiamata'
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
ms.openlocfilehash: de1f39b32503be758e10f3fbf712acdc07bd956b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Pianificazione del servizio Controllo di ammissione di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Per le applicazioni UC (Unified Communications) basate su IP, come la telefonia, il video e la condivisione di applicazioni, la larghezza di banda disponibile delle reti aziendali non viene in genere considerata un fattore limitante all'interno degli ambienti LAN. Tuttavia, nei collegamenti WAN che interconnettono i siti, la larghezza di banda della rete può essere limitata. Quando un afflusso di traffico di rete esegue l'oversubscription di un collegamento WAN, vengono usati meccanismi correnti come l'accodamento, il buffer e l'eliminazione dei pacchetti per risolvere la congestione. Il traffico aggiuntivo viene in genere ritardato finché la congestione della rete non si semplifica o, se necessario, il traffico viene eliminato. Per il traffico dati convenzionale in tali situazioni, il client ricevente può recuperare. Per il traffico in tempo reale, ad esempio le comunicazioni unificate, la congestione della rete non può essere risolta in questo modo, perché il traffico delle comunicazioni unificate è sensibile sia alla latenza che alla perdita di pacchetti. La congestione della rete WAN può causare una scarsa qualità dell'esperienza (QoE) per gli utenti. Per il traffico in tempo reale in condizioni congestionate, è preferibile negare le chiamate piuttosto che ottenere connessioni con qualità scadente.

Il controllo di ammissione di chiamata (CAC) determina se la larghezza di banda della rete è sufficiente per stabilire una sessione in tempo reale di qualità accettabile. In Lync Server 2013, CAC controlla il traffico in tempo reale solo per l'audio e il video, ma non influisce sul traffico dei dati. Se il percorso WAN predefinito non ha la larghezza di banda necessaria, il CAC può provare a instradare la chiamata tramite un percorso Internet o la rete PSTN (Public Switched Telephone Network). CAC è disponibile solo in Lync Server.

Questa sezione descrive la funzionalità controllo ammissione chiamata e spiega come pianificare il comando CAC.

<div>


> [!NOTE]  
> Lync Server include tre funzionalità vocali avanzate per l'organizzazione: controllo di ammissione delle chiamate (CAC), servizi di emergenza (E9-1-1) e bypass multimediale. Per una panoramica delle informazioni sulla pianificazione comuni a tutte e tre queste caratteristiche, vedere <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">impostazioni di rete per le funzionalità vocali avanzate di Enterprise in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Panoramica del controllo di ammissione alle chiamate in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Definizione dei requisiti dell'organizzazione per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Componenti e topologie per il servizio Controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Procedure consigliate per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Elenco di controllo di distribuzione per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

