---
title: 'Lync Server 2013: componenti utilizzati dal prelievo delle chiamate di gruppo'
description: 'Lync Server 2013: componenti utilizzati dal prelievo delle chiamate di gruppo.'
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
ms.openlocfilehash: 517f75dcbac8bfed0e749c061a9696b7667e10ed
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571832"
---
# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Componenti utilizzati dal ritiro delle chiamate di gruppo in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-30_

Il prelievo delle chiamate di gruppo viene distribuito automaticamente quando si distribuisce VoIP aziendale e l'applicazione Parcheggio di chiamata. È possibile abilitare il ritiro delle chiamate di gruppo configurando la tabella orbit del parcheggio di chiamata con intervalli di numeri distinti designati come numeri del gruppo di prelievo di chiamata e quindi assegnando gli utenti ai gruppi di prelievo di chiamata e abilitando gli utenti al ritiro delle chiamate di gruppo. I seguenti componenti di Lync Server supportano il ritiro delle chiamate di gruppo:

  - **Servizio applicazione**     Il servizio applicazione fornisce una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni di comunicazione unificata, ad esempio l'applicazione Parcheggio di chiamata. Il servizio applicazione viene installato automaticamente in tutti i front end server in un pool Front end e in tutti i server Standard Edition.

  - Applicazione Parcheggio di **chiamata**     L'applicazione Parcheggio di chiamata è una delle applicazioni di comunicazione unificate ospitate dal servizio applicazione. Il prelievo delle chiamate di gruppo si basa sull'applicazione Parcheggio di chiamata.

  - **Lync Server Management Shell**     È possibile utilizzare Lync Server Management Shell per gestire i gruppi di prelievo delle chiamate di gruppo.

  - Strumento del Resource **Kit di SEFAUtil**     Per assegnare gli utenti a un gruppo di prelievo delle chiamate e per abilitare o disabilitare il ritiro delle chiamate per gli utenti, è possibile utilizzare l'utilità di attivazione delle funzionalità di estensione secondaria (SEFAUtil).

</div>

<span> </span>

</div>

</div>

</div>

