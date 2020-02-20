---
title: 'Lync Server 2013: definizione dei requisiti per VoIP aziendale'
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
ms.openlocfilehash: 0406286f4f9d8251743fe6ff3a4807dff277fe92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>Definizione dei requisiti per VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-08-07_

In questo argomento viene fornita una panoramica delle considerazioni che è necessario apportare in merito alle aree geografiche, ai siti e ai collegamenti tra i siti nella topologia e su come questi sono importanti quando si distribuisce VoIP aziendale. Per informazioni dettagliate su come prendere queste decisioni, vedere [impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="sites-and-regions"></a>Siti e aree

In primo luogo, identificare i siti nella topologia in cui verranno distribuiti Enterprise Voice e le aree di rete a cui appartengono tali siti. Valutare in particolare il modo in cui verrà fornita la connettività PSTN (Public Switched Telephone Network) a ogni sito. Per motivi logistici e di gestione, le aree a cui appartengono questi siti possono rappresentare un fattore decisivo. Decidere dove verranno distribuiti i gateway localmente, in cui verrà distribuito Survivable Branch Appliance (SBA) e dove è possibile configurare trunk SIP (localmente o nel sito centrale) a un provider di servizi di telefonia Internet (ITSP).

</div>

<div>

## <a name="network-links-between-sites"></a>Collegamenti di rete tra siti

È inoltre necessario prendere in considerazione l'utilizzo della larghezza di banda previsto nei collegamenti di rete tra il sito centrale e i siti di succursale. Se si dispone o si pianifica la distribuzione dei collegamenti WAN resilienti tra i siti, è consigliabile distribuire un gateway in ogni sito di succursale per fornire la terminazione DID (Direct inwards) locale per gli utenti di tali siti. Se si dispone di collegamenti WAN resilienti, ma è probabile che la larghezza di banda di un collegamento WAN sia vincolata, configurare il servizio Controllo di ammissione di chiamata per il collegamento. Se non si dispone di collegamenti WAN resilienti, ospitare meno di 1000 utenti nel sito di succursale e non sono disponibili amministratori di Lync Server addestrati localmente, è consigliabile distribuire un Survivable Branch Appliance nel sito di succursale. Se si ospitano tra 1000 e 5000 utenti nel sito di succursale, manca una connessione WAN resiliente e sono disponibili amministratori di Lync Server addestrati, è consigliabile distribuire un Survivable Branch Server con un gateway di piccole dimensioni nel sito di succursale. Prendere inoltre in considerazione l'eventualità di abilitare il bypass multimediale nei collegamenti vincolati se si dispone di un peer gateway che supporta il bypass multimediale.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

