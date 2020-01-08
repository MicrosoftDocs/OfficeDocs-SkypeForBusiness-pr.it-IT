---
title: 'Lync Server 2013: Modalità di bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a08ec3ae6d985c18e20964a857a74ad40bc7668d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a>Modalità di bypass multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

È necessario configurare il bypass multimediale sia a livello globale che per ogni singolo trunk PSTN. Quando si Abilita il bypass multimediale a livello globale, sono disponibili due opzioni: **Ignora sempre** e **Usa le informazioni sul sito e le aree**geografiche.

Come suggerisce il nome, il **bypass indica sempre** che il bypass verrà tentato per tutte le chiamate PSTN. Il bypass viene usato **sempre** per le distribuzioni in cui non è necessario abilitare il controllo di ammissione alle chiamate e non è necessario specificare informazioni dettagliate sulla configurazione per il tentativo di bypass multimediale. Inoltre, **sempre l'esclusione** viene usata quando esiste una connettività completa tra client e gateway PSTN. In questa configurazione tutte le subnet sono mappate a uno e solo un ID di bypass, calcolato dal sistema.

Con le **informazioni sull'uso di siti e aree**geografiche, l'ID di bypass associato alla configurazione del sito e dell'area geografica viene usato per prendere la decisione di bypass. Questa configurazione offre la flessibilità necessaria per configurare il bypass per le topologie più comuni, in quanto offre un controllo preciso quando si verifica un bypass, oltre a supportare le interazioni con il controllo di ammissione alle chiamate (CAC). Il sistema cerca di semplificare l'attività assegnando automaticamente gli ID di bypass come indicato di seguito.

  - Il sistema assegna automaticamente un singolo ID di bypass univoco a ogni area geografica.

  - Qualsiasi sito connesso a un'area geografica su un collegamento WAN senza vincoli di larghezza di banda eredita lo stesso ID di bypass dell'area geografica.

  - Un sito associato all'area geografica su un collegamento WAN con larghezza di banda vincolata viene assegnato un ID di bypass diverso da quello dell'area geografica.

  - Le subnet associate a ogni sito ereditano l'ID di bypass per il sito.

<div>

## <a name="see-also"></a>Vedere anche


[Panoramica del bypass multimediale in Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Requisiti tecnici per il bypass multimediale in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

