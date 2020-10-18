---
title: 'Lync Server 2013: creare un criterio di segreteria telefonica ospitata a livello di sito'
description: 'Lync Server 2013: creare un criterio di segreteria telefonica ospitata a livello di sito.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd578359a8d20562e8887b61b86d53332e6f8d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578372"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="1164f-103">Creare un criterio di segreteria telefonica ospitata a livello di sito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1164f-103">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1164f-104">_**Ultimo argomento modificato:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="1164f-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="1164f-p101">Un criterio a livello di *sito* può influire su tutti gli utenti situati nel sito per cui il criterio viene definito. Se un utente è configurato per l'accesso alla messaggistica unificata di Exchange ospitata e non gli è stato assegnato un criterio per utente, verrà applicato il criterio a livello di sito. Se non è stato distribuito un criterio a livello di sito, verrà applicato il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="1164f-p101">A *site* policy can impact all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies. If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="1164f-108">Per informazioni dettagliate sulla configurazione dei criteri di sito, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="1164f-108">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="1164f-109">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="1164f-109">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="1164f-110">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="1164f-110">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="1164f-111">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="1164f-111">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="1164f-112">Per creare un criterio segreteria telefonica ospitata con ambito sito</span><span class="sxs-lookup"><span data-stu-id="1164f-112">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="1164f-113">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1164f-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1164f-p102">Eseguire il cmdlet New-CsHostedVoicemailPolicy per creare il criterio. Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="1164f-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="1164f-116">In questo esempio viene creato un criterio segreteria telefonica ospitata con ambito sito e vengono impostati i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="1164f-116">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="1164f-117">**Identity** specifica un identificatore univoco per il criterio, che include l'ambito.</span><span class="sxs-lookup"><span data-stu-id="1164f-117">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="1164f-118">Per un criterio con ambito sito, è necessario specificare il valore del parametro Identity nel formato `site:` *\<name\>* , ad esempio `site:Redmond` .</span><span class="sxs-lookup"><span data-stu-id="1164f-118">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="1164f-p104">**Destination** specifica il nome di dominio completo (FQDN) del servizio Messaggistica unificata di Exchange ospitato. Questo parametro è facoltativo, ma se si tenta di abilitare un utente per la segreteria telefonica ospitata e il criterio assegnato all'utente non dispone di un valore Destination, l'abilitazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1164f-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="1164f-121">**Description** fornisce informazioni descrittive facoltative sul criterio.</span><span class="sxs-lookup"><span data-stu-id="1164f-121">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="1164f-122">L' **organizzazione** specifica un elenco delimitato da virgole dei tenant di Exchange che ospitano gli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1164f-122">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="1164f-123">Ogni tenant deve essere specificato come FQDN di quel tenant nel servizio di messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="1164f-123">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

