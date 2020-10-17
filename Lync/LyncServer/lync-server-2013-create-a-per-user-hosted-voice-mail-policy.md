---
title: 'Lync Server 2013: creare un criterio di segreteria telefonica ospitata per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04dc942c0cd44c6390c8a7d6627c5da4b551b94c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501893"
---
# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="fab19-102">Creare criteri di segreteria telefonica ospitata per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fab19-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fab19-103">_**Ultimo argomento modificato:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="fab19-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="fab19-104">Un criterio *per utente* può avere effetto solo su singoli utenti, gruppi e oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="fab19-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="fab19-105">Per distribuire un criterio per utente, è necessario assegnarlo esplicitamente a uno o più utenti, gruppi o oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="fab19-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="fab19-106">Per ulteriori informazioni, vedere [assegnare criteri di segreteria telefonica ospitata per utente in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span><span class="sxs-lookup"><span data-stu-id="fab19-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="fab19-107">Per informazioni dettagliate sull'utilizzo dei criteri di segreteria telefonica ospitata per utente, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="fab19-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="fab19-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="fab19-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="fab19-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="fab19-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="fab19-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="fab19-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="fab19-111">Per creare un criterio segreteria telefonica ospitata per utente</span><span class="sxs-lookup"><span data-stu-id="fab19-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="fab19-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="fab19-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="fab19-p102">Eseguire il cmdlet New-CsHostedVoicemailPolicy per creare il criterio, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fab19-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="fab19-115">Nell'esempio precedente viene creato un criterio segreteria telefonica ospitata con ambito per utente e vengono impostati i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="fab19-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="fab19-p103">**Identity** specifica un identificatore univoco per il criterio, che include l'ambito. Per un criterio con ambito per utente, questo valore di parametro viene specificato come stringa semplice, ad esempio ExRedmond.</span><span class="sxs-lookup"><span data-stu-id="fab19-p103">**Identity** specifies a unique identifier for the policy, which includes the scope. For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="fab19-p104">**Destination** specifica il nome di dominio completo (FQDN) del servizio Messaggistica unificata di Exchange ospitato. Questo parametro è facoltativo, ma se si tenta di abilitare un utente per la segreteria telefonica ospitata e il criterio assegnato all'utente non dispone di un valore Destination, l'abilitazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="fab19-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="fab19-120">**Description** fornisce informazioni descrittive facoltative sul criterio.</span><span class="sxs-lookup"><span data-stu-id="fab19-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="fab19-121">L' **organizzazione** specifica un elenco delimitato da virgole dei tenant di Exchange che ospitano gli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fab19-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="fab19-122">Ogni tenant deve essere specificato come FQDN del tenant nel servizio Messaggistica unificata di Exchange ospitato.</span><span class="sxs-lookup"><span data-stu-id="fab19-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fab19-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fab19-123">See Also</span></span>


[<span data-ttu-id="fab19-124">Assegnare criteri di segreteria telefonica ospitata per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fab19-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

