---
title: 'Lync Server 2013: Configurare la tabella di codici orbit del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b306733c42e125a97c6bee4a4a42c4d96b7ebd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>Configurare la tabella di codici orbit del parcheggio di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-10_

Call Park USA orbite per le chiamate di parcheggio. Prima che gli utenti possano parcheggiare e recuperare le chiamate, è necessario configurare la tabella Orbit di Call Park. Devi specificare gli intervalli di numeri di interno (orbite) che l'organizzazione riserva alle chiamate di parcheggio e definire il routing per tali intervalli specificando il pool di parcheggio di chiamata che gestisce ogni intervallo. Quando definisci intervalli orbitali, l'obiettivo è quello di avere orbite sufficienti in modo che una qualsiasi orbita non venga riutilizzata troppo rapidamente, ma non così tante orbite che limiti il numero di estensioni disponibili per gli utenti o altri servizi. È possibile creare più intervalli di orbita del parcheggio di chiamata per ogni pool di Lync Server in cui è distribuita l'applicazione Parcheggio di chiamata. Ogni intervallo di Orbit di Call Park deve avere un nome univoco globale e un set di estensioni univoco.

<div>


> [!IMPORTANT]  
> Un intervallo orbit include in genere 100 o meno orbite. Ogni intervallo può essere molto più grande, purché sia più piccolo del massimo di 10.000 orbite per intervallo e si hanno meno di 50.000 orbite per ogni pool. Se un intervallo è troppo piccolo, le orbite vengono riutilizzate più rapidamente.



</div>

Usare blocchi di estensioni virtuali (estensioni che non hanno un utente o un telefono assegnato) per gli intervalli di Orbit.

<div>


> [!NOTE]  
> L'assegnazione di numeri DID (Direct Inward Dialing) come numeri di orbita nella tabella Orbit di parcheggio delle chiamate non è supportata.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

[Creare o modificare un intervallo orbit di Call Park in Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

