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
ms.openlocfilehash: cb35c064c304360adb27ecae73dd93c0e616711a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="382d4-102">Convalidare gli indirizzi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="382d4-102">Validate addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="382d4-103">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="382d4-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="382d4-104">Prima di pubblicare il database delle posizioni, è necessario convalidare le nuove posizioni in base allo stradario generale gestito dal provider dei servizi di emergenza del trunk SIP o della rete PSTN (Public Switched Telephone Network) .</span><span class="sxs-lookup"><span data-stu-id="382d4-104">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="382d4-105">Per informazioni dettagliate sui provider di servizi E9-1-1 trunk SIP, vedere [scelta di un provider di servizi E9-1-1 per Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span><span class="sxs-lookup"><span data-stu-id="382d4-105">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="382d4-106">Per informazioni dettagliate sulla convalida degli indirizzi, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="382d4-106">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="382d4-107">**Get-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="382d4-107">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="382d4-108">**Set-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="382d4-108">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="382d4-109">**Remove-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="382d4-109">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="382d4-110">**Get-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="382d4-110">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="382d4-111">**Test-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="382d4-111">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="382d4-112">Per convalidare gli indirizzi presenti nel database delle posizioni</span><span class="sxs-lookup"><span data-stu-id="382d4-112">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="382d4-113">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="382d4-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="382d4-114">Eseguire i seguenti cmdlet per configurare la connessione del provider dei servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="382d4-114">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="382d4-115">Per convalidare gli indirizzi nel database delle posizioni, eseguire il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="382d4-115">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="382d4-116">Per convalidare indirizzi singoli, è inoltre possibile utilizzare il cmdlet **Test-CsLisCivicAddress**.</span><span class="sxs-lookup"><span data-stu-id="382d4-116">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

