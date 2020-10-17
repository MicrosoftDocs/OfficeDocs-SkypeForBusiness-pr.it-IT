---
title: 'Lync Server 2013: convalidare gli indirizzi'
description: 'Lync Server 2013: convalidare gli indirizzi.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcbb8789912b3bcbcfb60dd79807f06c2957c1f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547272"
---
# <a name="validate-addresses-in-lync-server-2013"></a>Convalidare gli indirizzi in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-17_

Prima di pubblicare il database delle posizioni, è necessario convalidare le nuove posizioni in base allo stradario generale gestito dal provider dei servizi di emergenza del trunk SIP o della rete PSTN (Public Switched Telephone Network) .

Per informazioni dettagliate sui provider di servizi E9-1-1 trunk SIP, vedere [scelta di un provider di servizi E9-1-1 per Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Per informazioni dettagliate sulla convalida degli indirizzi, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>Per convalidare gli indirizzi presenti nel database delle posizioni

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire i seguenti cmdlet per configurare la connessione del provider dei servizi di emergenza.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  Per convalidare gli indirizzi nel database delle posizioni, eseguire il cmdlet seguente.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    Per convalidare indirizzi singoli, è inoltre possibile utilizzare il cmdlet **Test-CsLisCivicAddress**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

