---
title: 'Lync Server 2013: Determinazione della modalità di distribuzione di Microsoft Lync'
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
ms.openlocfilehash: aef6ac76b6c0e8a6fb3c0444ab219acf78119ecd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a>Determinazione della modalità di distribuzione di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

Durante la pianificazione di Lync, la prima decisione importante è la distribuzione di Microsoft Lync: come Lync Server 2013 in locale o Lync Online con Microsoft Office 365 nel cloud.

  - **Lync Server 2013 locale** : questa opzione offre il set completo di funzionalità Lync e offre la massima flessibilità nella configurazione, personalizzazione e gestione della distribuzione. Tutti i server sono installati in loco e gestiti dall'organizzazione. Una distribuzione locale offre l'intera gamma di funzionalità di Lync Server.

  - **Lync Online nel cloud** Lync Online è progettato per le organizzazioni che desiderano vantaggi per i costi e la flessibilità dei servizi di messaggistica istantanea, presenza e riunioni basati sul cloud, senza sacrificare le funzionalità di classe aziendale di Lync Server. Con Lync Online, Microsoft distribuisce e gestisce l'infrastruttura server necessaria e gestisce la manutenzione, le patch e gli aggiornamenti in corso. Alcune funzionalità disponibili in una distribuzione locale non sono disponibili in Lync Online.

Il tipo di distribuzione più adatto dipende dai carichi di lavoro che si vogliono distribuire e dallo stato geografico e aziendale dell'organizzazione.

<div>

## <a name="lync-server"></a>Lync Server

Una distribuzione locale di Lync Server è la soluzione migliore per gli scenari seguenti:

  - **Funzionalità di VoIP aziendale completa**   se si prevede di distribuire una soluzione VoIP aziendale completa per sostituire il PBX o che usa funzionalità avanzate per le chiamate, è necessaria una distribuzione locale di Lync Server. Locale supporta la connettività diretta con sistemi PBX e trunk e funzionalità avanzate per il telefono, ad esempio Response Group e Call Park. Lync Online attualmente non supporta queste funzionalità.

  - **Controlli di qualità multimediale**   se si vuole che l'intera gamma di caratteristiche di garanzia della qualità dei contenuti multimediali, ad esempio le funzionalità di controllo di ammissione alle chiamate (CAC) e qualità del servizio (QoS), si voglia eseguire una distribuzione locale.

  - **Chat persistente**   se è necessario distribuire la chat persistente per l'organizzazione, è necessario scegliere una distribuzione locale.

  - **applicazioni server di**   terze parti solo le distribuzioni locali possono lavorare con le applicazioni di terze parti attendibili che usano Microsoft Unified Communications Managed API (UCMA).

  - **Società multinazionali/multiregionali che necessitano**   di un supporto regionale se si hanno datacenter in più paesi o aree geografiche e i server devono essere distribuiti e gestiti su base regionale, è consigliabile una distribuzione locale, in quanto offre questo tipo di funzionalità di gestione regionale.

  - **Controllo completo sui criteri, i report e gli aggiornamenti**   con una distribuzione locale di Lync Server, è possibile accedere al set completo di criteri per server e client, per il monitoraggio e altri report e per la tempistica degli aggiornamenti. Lync Online offre un sottoinsieme di impostazioni e report dei criteri e offre una finestra limitata, ma significativa, per l'accettazione degli aggiornamenti.

</div>

<div>

## <a name="lync-online"></a>Lync Online

Se nessuno dei fattori nell'elenco precedente è fondamentale per l'utente, è consigliabile scegliere Lync Online per semplificare la distribuzione e la gestibilità. Lync Online offre un set di caratteristiche di messaggistica istantanea, presenza e conferenze affidabili e consente inoltre di effettuare chiamate vocali e video tramite IP tra gli utenti dell'organizzazione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

