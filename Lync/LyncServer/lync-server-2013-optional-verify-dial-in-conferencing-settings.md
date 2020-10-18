---
title: 'Lync Server 2013: (facoltativo) verificare le impostazioni delle conferenze telefoniche con accesso esterno'
description: 'Lync Server 2013: (facoltativo) verificare le impostazioni delle conferenze telefoniche con accesso esterno.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec002cfbd7cdd67498768a360143f88ab4f8e1b7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572562"
---
# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a><span data-ttu-id="409a0-103">Optional Verificare le impostazioni delle conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="409a0-103">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="409a0-104">_**Ultimo argomento modificato:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="409a0-104">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="409a0-p101">Come verifica finale della configurazione delle conferenze telefoniche con accesso esterno, è possibile cercare dial plan con un'area di conferenza telefonica con accesso esterno non utilizzata da alcun numero di accesso e numeri di telefono per i quali non è specificata un'area di conferenza telefonica con accesso esterno. Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="409a0-p101">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region. This step is optional.</span></span>

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="409a0-107">Per trovare dial plan con un'area di conferenza telefonica con accesso esterno non utilizzata da alcun numero di accesso</span><span class="sxs-lookup"><span data-stu-id="409a0-107">To find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1.  <span data-ttu-id="409a0-108">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o del ruolo **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="409a0-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="409a0-109">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="409a0-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="409a0-110">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="409a0-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    <span data-ttu-id="409a0-111">Questo cmdlet restituisce tutti i dial plan con un'area di conferenza telefonica con accesso esterno non utilizzata da alcun numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="409a0-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a><span data-ttu-id="409a0-112">Per trovare numeri di accesso senza aree assegnate</span><span class="sxs-lookup"><span data-stu-id="409a0-112">To find access numbers without assigned regions</span></span>

1.  <span data-ttu-id="409a0-113">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o del ruolo **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="409a0-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="409a0-114">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="409a0-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="409a0-115">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="409a0-115">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    <span data-ttu-id="409a0-116">Questo cmdlet restituisce tutti i numeri di accesso per conferenze telefoniche con accesso esterno non associati ad alcuna area.</span><span class="sxs-lookup"><span data-stu-id="409a0-116">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

