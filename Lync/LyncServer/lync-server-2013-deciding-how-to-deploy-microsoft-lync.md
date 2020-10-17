---
title: 'Lync Server 2013: scelta della modalità di distribuzione di Microsoft Lync'
description: 'Lync Server 2013: scelta della modalità di distribuzione di Microsoft Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a800b51dfddc6f2c99e42c8f117056ed4091b6a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558102"
---
# <a name="deciding-how-to-deploy-lync-server-2013"></a>Decidere come distribuire Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Durante la pianificazione di Lync, la prima decisione importante è la distribuzione di Microsoft Lync: come Lync Server 2013 in locale oppure Lync Online con Microsoft 365 o Office 365 nel cloud.

  - **Lync Server 2013 locale** : questa opzione offre il set completo di funzionalità di Lync e fornisce la massima flessibilità per la configurazione, la personalizzazione e la gestione della distribuzione. Tutti i server sono installati localmente e mantenuti presso l'organizzazione. Una distribuzione locale fornisce l'intera gamma di funzionalità di Lync Server.

  - **Lync Online nel cloud** Lync Online è stato ideato per le organizzazioni che desiderano i vantaggi di costo e agilità dei servizi di messaggistica istantanea basati su cloud, presenza e riunioni senza sacrificare le funzionalità di Business-Class di Lync Server. Con Lync Online, Microsoft distribuisce e gestisce l'infrastruttura server necessaria e gestisce la manutenzione, le patch e gli aggiornamenti in esecuzione. Alcune funzionalità disponibili in una distribuzione locale non sono disponibili in Lync Online.

Il tipo di distribuzione più adatto per un'azienda dipende dal tipo di workload che si ha bisogno di distribuire, nonché dalla posizione geografica e dallo stato dell'attività dell'organizzazione.

<div>

## <a name="lync-server"></a>Lync Server

Una distribuzione locale di Lync Server rappresenta la soluzione ideale nei seguenti casi:

  - Funzionalità complete di **VoIP aziendale**     Se si prevede di distribuire una soluzione VoIP aziendale completa per la sostituzione del sistema PBX o che utilizza funzionalità di chiamata avanzate, è necessaria una distribuzione locale di Lync Server. La distribuzione locale supporta un tipo di connettività diretta con i sistemi e trunk PBX, e funzionalità telefoniche avanzate come gruppi di risposta e parcheggio di chiamata. Lync Online attualmente non supporta queste funzionalità.

  - Controlli di qualità **multimediale**     Se si desidera che l'intera gamma di funzionalità di controllo della qualità multimediale, ad esempio le caratteristiche di servizio di ammissione di chiamata (CAC) e Quality of Service (QoS), si desideri una distribuzione locale.

  - **Chat**     persistente Se è necessario distribuire la chat persistente per l'organizzazione, è necessario scegliere una distribuzione locale.

  - Applicazioni server di terze **parti**     Solo le distribuzioni locali possono lavorare con le applicazioni di terze parti attendibili che utilizzano Microsoft Unified Communications Managed API (UCMA).

  - **Società multi-nazionali/multiregionali che necessitano di supporto regionale**     Se si dispone di datacenter in più paesi o aree geografiche e devono essere distribuiti e gestiti su base regionale, è preferibile una distribuzione locale, in quanto fornisce questo tipo di funzionalità di gestione regionale.

  - **Controllo completo sui criteri, i report e gli aggiornamenti**     Con una distribuzione di Lync Server locale, è possibile accedere al set completo di criteri server e client, al monitoraggio e ad altri report e alla tempistica degli aggiornamenti. Lync Online fornisce un sottoinsieme di impostazioni e report di criteri e fornisce una finestra limitata, anche se significativa, per l'accettazione degli aggiornamenti.

</div>

<div>

## <a name="lync-online"></a>Lync Online

Se nessuno dei precedenti rappresenta un fattore di importanza critica per la propria organizzazione, è possibile scegliere Lync Online, che offre una distribuzione e una gestibilità semplificate. Lync Online offre un robusto set di funzionalità di messaggistica istantanea, presenza e conferenza e consente inoltre di abilitare le chiamate vocali e video su IP tra gli utenti dell'organizzazione.

</div>

</div>

<span> </span>

</div>

</div>

</div>
