---
title: "Lync Server 2013: pianificazione dell'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e418ee1db146afa1f766aa0fc56842222f7b510c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Pianificazione dell'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-19_

Nella maggior parte delle organizzazioni le comunicazioni coinvolgono servizi e utenti non compresi nella rete interna. Tali servizi e utenti includono dipendenti temporaneamente o permanentemente fuori sede, dipendenti di organizzazioni clienti e partner, persone che utilizzano i servizi di messaggistica istantanea pubblica e potenziali clienti, partner e utenti anonimi che vengono invitati a riunioni e presentazioni. In questa documentazione queste persone vengono indicate come *utenti esterni*.

Con Microsoft Lync Server 2013, gli utenti dell'organizzazione possono utilizzare la messaggistica istantanea e la presenza per comunicare con gli utenti esterni e possono partecipare a conferenze audio/video (A/V) e Web Conferencing con i dipendenti esterni e altri tipi di utente esterno. È inoltre possibile supportare l'accesso esterno da dispositivi mobili e tramite VoIP aziendale. Gli utenti esterni che non sono membri dell'organizzazione possono partecipare alle riunioni di Lync Server 2013, consentendo ai partecipanti anonimi.

Per supportare le comunicazioni tra il firewall dell'organizzazione, è necessario distribuire Lync Server 2013 Edge Server nella rete perimetrale (nota anche come DMZ, area demilitarizzata e subnet schermata). Il server perimetrale controlla il modo in cui gli utenti esterni al firewall possono connettersi alla distribuzione interna di Lync Server 2013. Controlla inoltre le comunicazioni con utenti esterni che hanno origine nel firewall.

A seconda di specifici requisiti, è possibile distribuire uno o più server perimetrali in una o più posizioni. In questa sezione vengono descritti gli scenari per l'accesso degli utenti esterni in Lync Server 2013 e viene illustrato come pianificare la topologia di proxy inverso e Edge.

<div>


> [!NOTE]  
> Anche se è necessario un server perimetrale per il supporto di VoIP aziendale e accesso utente esterno, questa sezione si concentra sul supporto per messaggistica istantanea, presenza, A/V Conferencing, Federazione, Web Conferencing e Lync mobile. Per informazioni dettagliate sul supporto di VoIP aziendale, vedere <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Modifiche apportate in Lync Server 2013 che influiscono sulla pianificazione del server perimetrale](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Requisiti di sistema per i componenti per l'accesso degli utenti esterni per Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Panoramica dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Informazioni su individuazione automatica in Lync Server 2013](lync-server-2013-understanding-autodiscover.md)

  - [Scelta di una topologia in Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Raccolta dati in Lync Server 2013](lync-server-2013-data-collection.md)

  - [Determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Pianificare i certificati dei server perimetrali in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

