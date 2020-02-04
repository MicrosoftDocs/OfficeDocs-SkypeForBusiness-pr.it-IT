---
title: "Lync Server 2013: Definizione dei requisiti dell'organizzazione per VoIP aziendale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8987905d2b117eb889486882b7d74ce4e52659a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Definizione dei requisiti dell'organizzazione per VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-08-07_

Questo argomento offre una panoramica delle considerazioni che è necessario apportare in merito alle aree geografiche, ai siti e ai collegamenti tra i siti della topologia e in che modo sono importanti quando si distribuisce VoIP aziendale. Per informazioni dettagliate su come prendere queste decisioni, vedere [impostazioni di rete per le funzionalità vocali avanzate di Enterprise in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="sites-and-regions"></a>Siti e aree geografiche

Prima di tutto, identificare i siti della topologia in cui distribuire VoIP aziendale e le aree di rete a cui appartengono tali siti. In particolare, valutare come si fornirà la connettività PSTN (Public Switched Telephone Network) a ogni sito. Per motivi di gestibilità e logistica, le aree geografiche a cui appartengono questi siti possono essere un fattore decisivo. Decidere dove verranno distribuiti i gateway localmente, dove saranno distribuiti gli appliance Survivable Branch (SBAs) e dove è possibile configurare trunk SIP (localmente o nel sito centrale) in un provider di servizi di telefonia Internet (ITSP).

</div>

<div>

## <a name="network-links-between-sites"></a>Collegamenti di rete tra siti

È inoltre necessario prendere in considerazione l'utilizzo della larghezza di banda previsto nei collegamenti di rete tra il sito centrale e i siti di succursale. Se si ha o si prevede di distribuire i collegamenti WAN resilienti tra i siti, è consigliabile distribuire un gateway in ogni sito di succursale per specificare la terminazione per gli utenti di tali siti. Se si hanno collegamenti WAN resilienti, ma è probabile che la larghezza di banda di un collegamento WAN sia vincolata, configurare il controllo di ammissione delle chiamate per il collegamento. Se non si dispone di collegamenti WAN resilienti, è necessario ospitare meno di 1000 utenti nel sito di succursale e non sono disponibili amministratori di Lync Server addestrati localmente, è consigliabile distribuire un Survivable Branch Appliance nel sito della filiale. Se si ospitano tra gli utenti di 1000 e 5000 nel sito di succursale, non è disponibile una connessione WAN resiliente e sono stati addestrati gli amministratori di Lync Server, è consigliabile distribuire un Survivable Branch Server con un piccolo gateway nel sito della filiale. Se si ha un peer del gateway che supporta il bypass multimediale, è consigliabile anche abilitare il bypass multimediale sui collegamenti vincolati.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Impostazioni di rete per le funzionalità vocali avanzate di Enterprise in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

