---
title: 'Lync Server 2013: criteri di segreteria telefonica ospitata'
description: 'Lync Server 2013: criteri di segreteria telefonica ospitata.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57461f4ffd2c6f2cd733dd7ec2c945c9e7b801c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550102"
---
# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="cb785-103">Criteri di segreteria telefonica ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb785-103">Hosted voice mail policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb785-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="cb785-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="cb785-105">Un *criterio di segreteria telefonica ospitata* fornisce informazioni all'applicazione di routing di Lync Server 2013 ExUM in cui instradare le chiamate per gli utenti le cui cassette postali si trovano in un servizio di Exchange ospitato.</span><span class="sxs-lookup"><span data-stu-id="cb785-105">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cb785-106">I criteri di segreteria telefonica ospitata sono necessari solo per l'integrazione di Lync Server 2013 con messaggistica unificata di Exchange ospitata</span><span class="sxs-lookup"><span data-stu-id="cb785-106">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="cb785-107">Non sono necessari per l'integrazione con la messaggistica unificata di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="cb785-107">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="cb785-108">Ambito del criterio di segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="cb785-108">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="cb785-109">L'ambito dei criteri di segreteria telefonica ospitata determina il livello gerarchico a cui si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="cb785-109">Hosted voice mail policy scope determines the hierarchical level at which the policy applies.</span></span> <span data-ttu-id="cb785-110">È possibile configurare i criteri di segreteria telefonica ospitata con i livelli di ambito seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb785-110">You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="cb785-111">Il criterio *globale* può potenzialmente influire su tutti gli utenti nella distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb785-111">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="cb785-112">Se un utente è abilitato per l'accesso alla messaggistica unificata di Exchange ospitata e non è stato assegnato un criterio per utente, e se non è stato assegnato un criterio sito al sito dell'utente, viene applicato il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="cb785-112">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="cb785-113">Il criterio globale viene installato con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb785-113">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="cb785-114">È possibile modificarli in base a specifiche esigenze, ma non è possibile rinominarli né eliminarli.</span><span class="sxs-lookup"><span data-stu-id="cb785-114">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="cb785-115">Un criterio *sito* può influire su tutti gli utenti ospitati nel sito per cui è definito il criterio.</span><span class="sxs-lookup"><span data-stu-id="cb785-115">A *site* policy can affect all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="cb785-116">Se un utente è configurato per l'accesso alla messaggistica unificata di Exchange ospitata e non è stato assegnato un criterio per utente, viene applicato il criterio sito.</span><span class="sxs-lookup"><span data-stu-id="cb785-116">If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="cb785-117">Un criterio *per utente* può influire solo su singoli utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="cb785-117">A *per-user* policy can affect only individual users or groups.</span></span> <span data-ttu-id="cb785-118">Per applicare un criterio per utente, è necessario assegnare esplicitamente il criterio a singoli utenti, gruppi e oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="cb785-118">To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cb785-119">Nella maggior parte dei casi, è necessario un solo criterio di segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="cb785-119">In most cases, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="cb785-120">Spesso è possibile modificare il criterio globale per soddisfare tutte le esigenze.</span><span class="sxs-lookup"><span data-stu-id="cb785-120">You can often modify the global policy to meet all your needs.</span></span> <span data-ttu-id="cb785-121">Se si distribuiscono più criteri di segreteria telefonica ospitata, tutti i criteri di questo tipo hanno ambito per utente.</span><span class="sxs-lookup"><span data-stu-id="cb785-121">If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="cb785-122">Attributi del criterio di segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="cb785-122">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="cb785-123">Un criterio di segreteria telefonica definisce due attributi che l'applicazione di routing di Lync Server 2013 ExUM inserisce nell'URI della richiesta di un messaggio di invito inviato all'implementazione di messaggistica unificata di Exchange ospitata:</span><span class="sxs-lookup"><span data-stu-id="cb785-123">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="cb785-124">**Destinazione:** Il nome di dominio completo (FQDN) del servizio di messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="cb785-124">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="cb785-125">Questo valore viene utilizzato dal server perimetrale di Lync Server locale per scopi di routing.</span><span class="sxs-lookup"><span data-stu-id="cb785-125">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cb785-126">Per Exchange Online, l'FQDN è exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="cb785-126">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="cb785-127">**Organizzazione:** Il nome di dominio completo del tenant nel servizio di messaggistica unificata di Exchange ospitato che ospita le cassette postali degli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb785-127">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="cb785-128">Un criterio di segreteria telefonica può contenere più organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="cb785-128">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="cb785-129">Se nel criterio è inclusa più di un'organizzazione, questo attributo deve essere un elenco separato da virgole dei tenant del server Exchange che ospita le cassette postali degli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb785-129">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cb785-130">L'amministratore tenant del servizio di messaggistica unificata di Exchange ospitato fornirà i valori necessari per le impostazioni degli attributi di destinazione e dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cb785-130">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings.</span></span> <span data-ttu-id="cb785-131">Per configurare i criteri, è necessario eseguire il cmdlet New-CsHostedVoicemailPolicy o utilizzare il cmdlet Set-CsHostedVoicemailPolicy per modificarne uno esistente, ad esempio il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="cb785-131">To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="cb785-132">Per informazioni dettagliate sulla gestione dei criteri di segreteria telefonica ospitata, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb785-132">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="cb785-133">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cb785-133">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="cb785-134">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cb785-134">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="cb785-135">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cb785-135">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="cb785-136">Per-User assegnazione dei criteri di segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="cb785-136">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="cb785-137">Se il criterio di segreteria telefonica ospitata è definito con ambito per utente, è necessario assegnarlo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="cb785-137">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it.</span></span> <span data-ttu-id="cb785-138">È possibile eseguire il cmdlet Grant-CsHostedVoicemailPolicy per assegnare il criterio a singoli utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="cb785-138">You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="cb785-139">Per informazioni dettagliate sull'assegnazione o la rimozione di criteri di segreteria telefonica ospitata per utente, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb785-139">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="cb785-140">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cb785-140">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="cb785-141">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="cb785-141">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

