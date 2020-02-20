---
title: 'Lync Server 2013: bypass multimediale e Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a33ed2c9b3494e9c67e8ac4a658b6aee75ff7649
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Bypass multimediale e Mediation Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Il bypass multimediale è una funzionalità di Lync Server che consente a un amministratore di configurare il routing delle chiamate per il flusso direttamente tra l'endpoint utente e il gateway PSTN (Public Switched Telephone Network) senza attraversare il Mediation Server. Il bypass multimediale consente di migliorare la qualità delle chiamate riducendo la latenza, la traduzione non necessaria, la possibilità di perdita di pacchetti e il numero di potenziali punti di errore. Se un sito remoto privo di Mediation Server è connesso a un sito centrale da uno o più collegamenti WAN con larghezza di banda vincolata, il bypass multimediale abbassa il requisito di larghezza di banda consentendo agli elementi multimediali provenienti da un client in un sito remoto di fluire direttamente sul gateway locale senza prima di tutto è necessario scorrere il collegamento WAN a un Mediation Server nel sito centrale e viceversa. Questa riduzione dell'elaborazione multimediale integra inoltre la capacità del Mediation Server di controllare più gateway.

Le funzionalità di bypass multimediale e controllo di ammissione di chiamata (CAC) si escludono a vicenda. Se per una chiamata viene utilizzato il bypass multimediale, il controllo di ammissione di chiamate per tale chiamata non viene eseguito. Il presupposto è che nella chiamata non siano coinvolti link con larghezza di banda limitata.

<div>

## <a name="see-also"></a>Vedere anche


[Controllo di ammissione di chiamata e Mediation Server in Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)  


[Pianificazione del bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

