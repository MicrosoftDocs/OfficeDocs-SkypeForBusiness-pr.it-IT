---
title: 'Lync Server 2013: convalidare gli indirizzi'
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
ms.openlocfilehash: 397c1037937e100f1981a689f0860362d852ed10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a>Convalidare gli indirizzi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-17_

Prima di pubblicare il database della posizione, è necessario convalidare le nuove posizioni in base alla guida stradario (Master Street Address Guide) gestita dal proprio trunk SIP o dal provider di servizi E9-1-1 della rete PSTN (Public Switched Telephone Network).

Per informazioni dettagliate sui provider di servizi E9-1-1 trunk SIP, vedere [scelta di un provider di servizi E9-1-1 per Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Per informazioni dettagliate sulla convalida degli indirizzi, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>Per convalidare gli indirizzi presenti nel database della posizione

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire i cmdlet seguenti per configurare la connessione del provider di servizi di emergenza.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  Eseguire il cmdlet seguente per convalidare gli indirizzi nel database della posizione.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    Puoi anche usare il cmdlet **Test-CsLisCivicAddress** per convalidare singoli indirizzi.

</div>

</div>

<span> </span>

</div>

</div>

</div>

