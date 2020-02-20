---
title: 'Lync Server 2013: aggiungere un criterio percorso a un sito di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a817a1a94b6e02167d488212dd532537cec0146
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a>Aggiungere un criterio percorso a un sito di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-24_

Negli esempi seguenti viene illustrato come aggiungere il criterio percorso **Redmond** definito in [create location Policies in Lync Server 2013](lync-server-2013-create-location-policies.md) a un sito di rete esistente e come creare un nuovo sito di rete in cui viene utilizzato il criterio percorso **Redmond** .

Per informazioni dettagliate sull'utilizzo dei siti di rete, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - **New-CsNetworkSite**

  - **Get-CsNetworkSite**

  - **Set-CsNetworkSite**

  - **Remove-CsNetworkSite**

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>Per assegnare un criterio percorso a un sito di rete esistente

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire i cmdlet seguenti per modificare un sito di rete esistente.
    
    Assegnare il criterio percorso con tag **Redmond** a un sito di rete esistente denominato **Redmond**.
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a>Per assegnare un criterio percorso a un nuovo sito di rete

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet seguente per creare un nuovo sito di rete.
    
    Creare un nuovo sito di rete nell'area di rete e assegnare il criterio percorso contrassegnato come **Redmond**.
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

