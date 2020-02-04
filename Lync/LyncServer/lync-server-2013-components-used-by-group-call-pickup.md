---
title: 'Lync Server 2013: componenti usati dal ritiro delle chiamate di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b9c810d5835d113a26bd3a15295f75a71552590
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Componenti usati dal ritiro delle chiamate di gruppo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-30_

Il ritiro delle chiamate di gruppo viene distribuito automaticamente quando si distribuisce VoIP aziendale e l'applicazione Call Park. Puoi abilitare il ritiro delle chiamate di gruppo configurando la tabella Orbit di Call Park con intervalli distinti di numeri designati come numeri di gruppo di prelievo chiamate e quindi assegnando gli utenti per chiamare i gruppi di prelievo e abilitare gli utenti per il ritiro delle chiamate di gruppo. I seguenti componenti di Lync Server supportano il pick-up delle chiamate di gruppo:

  - **Application Service**   Application Service offre una piattaforma per la distribuzione, l'hosting e la gestione di applicazioni di comunicazioni unificate, ad esempio l'applicazione Call Park. Il servizio applicazione viene installato automaticamente in ogni server front-end in un pool Front-end e in ogni server Standard Edition.

  - **Call Park application**   l'applicazione Call Park è una delle applicazioni di comunicazioni unificate ospitate dal servizio applicazione. Il ritiro delle chiamate di gruppo si basa sull'applicazione Call Park.

  - **Lync Server Management Shell**   si usa Lync Server Management Shell per gestire i gruppi di prelievo delle chiamate di gruppo.

  - **Strumento di SEFAUtil Resource Kit**   si usa l'utilità di attivazione delle funzionalità di estensione secondaria (SEFAUtil) per assegnare gli utenti a un gruppo di raccolta chiamate e per abilitare o disabilitare il ritiro delle chiamate per gli utenti.

</div>

<span> </span>

</div>

</div>

</div>

