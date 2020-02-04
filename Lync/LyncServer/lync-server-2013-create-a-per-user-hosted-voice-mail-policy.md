---
title: 'Lync Server 2013: creare un criterio per la segreteria telefonica ospitata per utente'
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
ms.openlocfilehash: 535515fd11c0cb736b5b6fb4b70d041ea3af8a3c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="8ff09-102">Creare un criterio di segreteria telefonica ospitata per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ff09-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ff09-103">_**Argomento Ultima modifica:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="8ff09-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="8ff09-104">Un criterio *per utente* può influire solo su singoli utenti, gruppi e oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="8ff09-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="8ff09-105">Per distribuire un criterio per utente, è necessario assegnare esplicitamente i criteri a uno o più utenti, gruppi o oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="8ff09-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="8ff09-106">Per informazioni dettagliate, vedere [assegnare un criterio di segreteria telefonica ospitata per utente in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span><span class="sxs-lookup"><span data-stu-id="8ff09-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="8ff09-107">Per informazioni dettagliate sull'uso dei criteri per la segreteria telefonica ospitata per utente, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ff09-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="8ff09-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="8ff09-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="8ff09-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="8ff09-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="8ff09-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="8ff09-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="8ff09-111">Per creare un criterio di segreteria telefonica ospitata per utente</span><span class="sxs-lookup"><span data-stu-id="8ff09-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="8ff09-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8ff09-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8ff09-113">Eseguire il cmdlet New-CsHostedVoicemailPolicy per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="8ff09-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="8ff09-114">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="8ff09-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="8ff09-115">L'esempio precedente crea un criterio di segreteria telefonica ospitata con ambito per utente e imposta i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ff09-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="8ff09-116">**Identity** specifica un identificatore univoco per il criterio, che include l'ambito.</span><span class="sxs-lookup"><span data-stu-id="8ff09-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="8ff09-117">Per un criterio con ambito per utente, il valore di questo parametro viene specificato come stringa semplice, ad esempio ExRedmond.</span><span class="sxs-lookup"><span data-stu-id="8ff09-117">For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="8ff09-118">**Destination** specifica il nome di dominio completo (FQDN) del servizio di messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="8ff09-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="8ff09-119">Questo parametro è facoltativo, ma se tenti di abilitare un utente per la segreteria telefonica ospitata e il criterio assegnato dall'utente non ha un valore di destinazione, l'opzione di abilitazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8ff09-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="8ff09-120">**Descrizione** fornisce informazioni descrittive facoltative sui criteri.</span><span class="sxs-lookup"><span data-stu-id="8ff09-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="8ff09-121">**Organizzazione** specifica un elenco delimitato da virgole dei tenant di Exchange che ospitano gli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ff09-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="8ff09-122">Ogni tenant deve essere specificato come FQDN del tenant nel servizio di messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="8ff09-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ff09-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ff09-123">See Also</span></span>


[<span data-ttu-id="8ff09-124">Assegnare un criterio di segreteria telefonica ospitata per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ff09-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

