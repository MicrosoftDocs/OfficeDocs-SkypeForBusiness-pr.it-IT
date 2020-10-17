---
title: 'Lync Server 2013: creare un criterio di segreteria telefonica ospitata a livello di sito'
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
ms.openlocfilehash: e23f14b1db7c846d5dbaa0aa6861274a7b6a2611
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501883"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="4f604-102">Creare un criterio di segreteria telefonica ospitata a livello di sito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f604-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f604-103">_**Ultimo argomento modificato:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="4f604-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="4f604-p101">Un criterio a livello di *sito* può influire su tutti gli utenti situati nel sito per cui il criterio viene definito. Se un utente è configurato per l'accesso alla messaggistica unificata di Exchange ospitata e non gli è stato assegnato un criterio per utente, verrà applicato il criterio a livello di sito. Se non è stato distribuito un criterio a livello di sito, verrà applicato il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="4f604-p101">A *site* policy can impact all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies. If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="4f604-107">Per informazioni dettagliate sulla configurazione dei criteri di sito, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f604-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="4f604-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4f604-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="4f604-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4f604-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="4f604-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="4f604-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="4f604-111">Per creare un criterio segreteria telefonica ospitata con ambito sito</span><span class="sxs-lookup"><span data-stu-id="4f604-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="4f604-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4f604-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4f604-p102">Eseguire il cmdlet New-CsHostedVoicemailPolicy per creare il criterio. Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="4f604-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="4f604-115">In questo esempio viene creato un criterio segreteria telefonica ospitata con ambito sito e vengono impostati i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f604-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="4f604-116">**Identity** specifica un identificatore univoco per il criterio, che include l'ambito.</span><span class="sxs-lookup"><span data-stu-id="4f604-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="4f604-117">Per un criterio con ambito sito, è necessario specificare il valore del parametro Identity nel formato `site:` *\<name\>* , ad esempio `site:Redmond` .</span><span class="sxs-lookup"><span data-stu-id="4f604-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="4f604-p104">**Destination** specifica il nome di dominio completo (FQDN) del servizio Messaggistica unificata di Exchange ospitato. Questo parametro è facoltativo, ma se si tenta di abilitare un utente per la segreteria telefonica ospitata e il criterio assegnato all'utente non dispone di un valore Destination, l'abilitazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4f604-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="4f604-120">**Description** fornisce informazioni descrittive facoltative sul criterio.</span><span class="sxs-lookup"><span data-stu-id="4f604-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="4f604-121">L' **organizzazione** specifica un elenco delimitato da virgole dei tenant di Exchange che ospitano gli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f604-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="4f604-122">Ogni tenant deve essere specificato come FQDN di quel tenant nel servizio di messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="4f604-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

