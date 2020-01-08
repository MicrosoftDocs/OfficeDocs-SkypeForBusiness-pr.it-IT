---
title: "Lync Server 2013: Pianificazione dell'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76d4853e7e748128214fc93b721a59e979af03e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Pianificazione dell'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-19_

Le comunicazioni nella maggior parte delle organizzazioni coinvolgono i servizi e gli utenti che non si trovano all'interno della rete interna. Questi servizi e utenti includono i dipendenti temporaneamente o definitivamente fuori sede, i dipendenti delle organizzazioni di clienti o partner, le persone che usano servizi di messaggistica istantanea pubblica e i potenziali clienti, partner e utenti anonimi che si invitano alle riunioni e alle presentazioni. In questa documentazione, queste persone sono chiamate collettivamente *utenti esterni*.

Con Microsoft Lync Server 2013, gli utenti dell'organizzazione possono usare la messaggistica istantanea e la presenza per comunicare con gli utenti esterni e possono partecipare a conferenze audio/video (A/V) e conferenze Web con i dipendenti esterni e altri tipi di utente esterno. Puoi anche supportare l'accesso esterno da dispositivi mobili e da VoIP aziendale. Gli utenti esterni che non sono membri dell'organizzazione possono partecipare alle riunioni di Lync Server 2013, consentendo i partecipanti anonimi.

Per supportare le comunicazioni attraverso il firewall dell'organizzazione, distribuire Lync Server 2013 Edge Server nella rete perimetrale (nota anche come DMZ, zona demilitarizzata e subnet schermata). Il server perimetrale controlla il modo in cui gli utenti esterni al firewall possono connettersi alla distribuzione interna di Lync Server 2013. Controlla inoltre le comunicazioni con utenti esterni che hanno origine all'interno del firewall.

A seconda dei requisiti, è possibile distribuire uno o più Edge Server in una o più posizioni. Questa sezione descrive scenari per l'accesso degli utenti esterni in Lync Server 2013 e spiega come pianificare la topologia del proxy inverso e del bordo.

<div>


> [!NOTE]  
> Anche se è necessario un server perimetrale per supportare l'accesso a VoIP aziendale e utenti esterni, questa sezione si incentra sul supporto di messaggistica istantanea, presenza, servizi di conferenza A/V, Federazione, Web Conferencing e Lync mobile. Per informazioni dettagliate sul supporto per VoIP aziendale, vedere <A href="lync-server-2013-planning-for-enterprise-voice.md">pianificazione di VoIP aziendale in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Modifiche introdotte in Lync Server 2013 che incidono sulla pianificazione dei server perimetrali](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Requisiti di sistema per i componenti per l'accesso degli utenti esterni per Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Panoramica dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Informazioni sull'individuazione automatica in Lync Server 2013](lync-server-2013-understanding-autodiscover.md)

  - [Scelta di una topologia in Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Raccolta dati in Lync Server 2013](lync-server-2013-data-collection.md)

  - [Determinare i requisiti di DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Pianificare i certificati dei server perimetrali in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

