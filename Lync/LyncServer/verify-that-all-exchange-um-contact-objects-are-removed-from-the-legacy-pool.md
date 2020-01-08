---
title: Verificare che tutti gli oggetti contatto di messaggistica unificata di Exchange vengano rimossi dal pool legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0db8f4c55d863221c9a66d33a21bbe073bbc225a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="b4c23-102">Verificare che tutti gli oggetti contatto di messaggistica unificata di Exchange vengano rimossi dal pool legacy</span><span class="sxs-lookup"><span data-stu-id="b4c23-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4c23-103">_**Argomento Ultima modifica:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="b4c23-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="b4c23-104">Puoi usare lo strumento **OCSUmUtil** o il cmdlet **Get-CsExUmContact** per verificare che gli oggetti contatto di messaggistica unificata di Exchange siano stati rimossi dal pool legacy di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b4c23-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="b4c23-105">**OCSUmUtil** si trova nella cartella seguente:</span><span class="sxs-lookup"><span data-stu-id="b4c23-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="b4c23-106">\\% Programmi% file\\comuni Lync Server 2013\\supporta\\OcsUmUtil. exe</span><span class="sxs-lookup"><span data-stu-id="b4c23-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="b4c23-107">**OCSUmUtil** deve essere eseguito da un account utente che include:</span><span class="sxs-lookup"><span data-stu-id="b4c23-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="b4c23-108">Appartenenza al gruppo RTCUniversalServerAdmins e RTCUniversalUserAdmins (che include i diritti per la lettura delle impostazioni della messaggistica unificata di Exchange Server)</span><span class="sxs-lookup"><span data-stu-id="b4c23-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="b4c23-109">Diritti di dominio per creare oggetti contatto nel contenitore dell'unità organizzativa specificata</span><span class="sxs-lookup"><span data-stu-id="b4c23-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="b4c23-110">Per informazioni dettagliate sull'uso del cmdlet **Get-CsExUmContact** , vedere [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b4c23-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

