---
title: Verificare che tutti gli oggetti contatto della messaggistica unificata di Exchange siano stati rimossi dal pool legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72e18e63dbbc5b64ca61baf9c5635717fc7f3fff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="2b86b-102">Verificare che tutti gli oggetti contatto della messaggistica unificata di Exchange siano stati rimossi dal pool legacy</span><span class="sxs-lookup"><span data-stu-id="2b86b-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b86b-103">_**Ultimo argomento modificato:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="2b86b-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="2b86b-104">Utilizzare lo strumento **OCSUmUtil** o il cmdlet **Get-CsExUmContact** per verificare che gli oggetti contatto di messaggistica unificata di Exchange siano stati rimossi dal pool di Office Communications Server 2007 R2 legacy.</span><span class="sxs-lookup"><span data-stu-id="2b86b-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="2b86b-105">**OCSUmUtil** è contenuto nella cartella seguente:</span><span class="sxs-lookup"><span data-stu-id="2b86b-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="2b86b-106">\\% Programmi%\\file comuni Lync Server 2013\\supporto\\di OcsUmUtil. exe</span><span class="sxs-lookup"><span data-stu-id="2b86b-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="2b86b-107">Lo strumento **OCSUmUtil** deve essere eseguito da un account utente:</span><span class="sxs-lookup"><span data-stu-id="2b86b-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="2b86b-108">Membro del gruppo RTCUniversalServerAdmins e del gruppo RTCUniversalUserAdmins (include i diritti di lettura delle impostazioni di messaggistica unificata di Exchange Server)</span><span class="sxs-lookup"><span data-stu-id="2b86b-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="2b86b-109">Con diritti a livello di dominio per creare oggetti contatto nel contenitore di unità organizzative specificato</span><span class="sxs-lookup"><span data-stu-id="2b86b-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="2b86b-110">Per informazioni dettagliate sull'utilizzo del cmdlet **Get-CsExUmContact** , vedere [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2b86b-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

