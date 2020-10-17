---
title: 'Lync Server 2013: cmdlet di interoperabilità'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability cmdlets
ms:assetid: 18444a0b-7b66-4540-a262-775ea10b3b7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204714(v=OCS.15)
ms:contentKeyID: 48183527
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b9509fe93e1efbde72896cead2f06ab907bbe46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498453"
---
# <a name="interoperability-cmdlets-in-lync-server-2013"></a><span data-ttu-id="a7e70-102">Cmdlet di interoperabilità in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7e70-102">Interoperability cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7e70-103">_**Ultimo argomento modificato:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="a7e70-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="a7e70-104">I cmdlet di interoperabilità vengono utilizzati per configurare l'autenticazione da server a server e l'autorizzazione tra Microsoft Lync Server 2013 e altri prodotti server, ad esempio Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7e70-104">The interoperability cmdlets are used to configure server-to-server authentication and authorization between Microsoft Lync Server 2013 and other server products such as Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="a7e70-105">Con l'autenticazione e l'autorizzazione server-server i server riescono a scambiarsi e a condividere i dati facilmente.</span><span class="sxs-lookup"><span data-stu-id="a7e70-105">Server-to-server authentication and authorization enables these servers to seamless exchange and share data.</span></span>

<div>

## <a name="interoperability-cmdlets"></a><span data-ttu-id="a7e70-106">Cmdlet di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="a7e70-106">Interoperability Cmdlets</span></span>

<span data-ttu-id="a7e70-107">Di seguito è riportato un elenco di cmdlet che si riferiscono direttamente alla configurazione e alla gestione dell'interoperabilità tra Microsoft Lync Server 2013 e altri prodotti server:</span><span class="sxs-lookup"><span data-stu-id="a7e70-107">The following is a list of cmdlets that relate directly to configuring and managing interoperability between Microsoft Lync Server 2013 and other server products:</span></span>

<span data-ttu-id="a7e70-108">**Cmdlet di interoperabilità**</span><span class="sxs-lookup"><span data-stu-id="a7e70-108">**Interoperability Cmdlets**</span></span>

  - <span data-ttu-id="a7e70-109">[Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7e70-109">[Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="a7e70-110">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7e70-110">[Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="a7e70-111">[Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7e70-111">[Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="a7e70-112">[New-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7e70-112">[New-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="a7e70-113">[Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7e70-113">[Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="a7e70-114">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7e70-114">[Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="a7e70-115">[Get-CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7e70-115">[Get-CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="a7e70-116">[New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7e70-116">[New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="a7e70-117">[Remove-CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7e70-117">[Remove-CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="a7e70-118">[Set-CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="a7e70-118">[Set-CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

