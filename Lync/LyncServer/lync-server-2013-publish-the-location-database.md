---
title: 'Lync Server 2013: pubblicare il database della posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2afc13a67ccdad3d27328107e095f1bffa66fdcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a>Pubblicare il database della posizione da Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-30_

I nuovi percorsi aggiunti al database della posizione non verranno resi disponibili al client finché non saranno stati pubblicati.

Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per il cmdlet seguente:

  - **Publish-CsLisConfiguration**

Se si usano i gateway ELIN (Emergency Location Identification Number), è anche necessario caricare i numeri ELINs nel database di identificazione automatica della posizione (ALI) del gestore della rete PSTN (Public Switched Telephone Network). Il gestore PSTN può richiedere l'uso di un formato specifico per i record ELIN. Per informazioni dettagliate, contattare il gestore PSTN. È possibile esportare i record dal database del servizio informazioni sulla posizione e formattarli in base alle esigenze.

<div>

## <a name="to-publish-the-location-database"></a>Per pubblicare il database della posizione

  - Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

  - Eseguire il cmdlet seguente per pubblicare il database della posizione.
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

