---
title: 'Lync Server 2013: pubblicare il database delle posizioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 481a8406eeeec6fce25c19336519c4a9bf19da82
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512373"
---
# <a name="publish-the-location-database-from-lync-server-2013"></a>Pubblicare il database delle posizioni da Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-30_

Le nuove posizioni aggiunte al database delle posizioni non vengono rese disponibili per il client finché non vengono pubblicate.

Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per il cmdlet seguente:

  - **Publish-CsLisConfiguration**

Se si utilizzano gateway ELIN (Emergency Location Identification Number), è necessario inoltre caricare i numeri ELIN nel database ALI (Automatic Location Identification) del gestore della rete PSTN (Public Switched Telephone Network). Il gestore della rete PSTN può richiedere di utilizzare un formato specifico per i record ELIN. Contattarlo per informazioni dettagliate. È possibile esportare i record dal database del servizio informazioni percorso e formattarli in base alle esigenze.

<div>

## <a name="to-publish-the-location-database"></a>Per pubblicare il database delle posizioni

  - Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

  - Per pubblicare il database delle posizioni, eseguire il cmdlet seguente.
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

