---
title: 'Lync Server 2013: Criteri di segreteria telefonica ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a23f5fa67a34d479bbc5b9d5c9bf55071b187c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="a22d0-102">Criteri di segreteria telefonica ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a22d0-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a22d0-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a22d0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a22d0-104">Un criterio di segreteria *telefonica ospitata* fornisce informazioni all'applicazione di routing di Lync Server 2013 ExUM su dove instradare le chiamate per gli utenti le cui cassette postali si trovano in un servizio di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="a22d0-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a22d0-105">I criteri di segreteria telefonica ospitati sono obbligatori solo per l'integrazione di Lync Server 2013 con messaggistica unificata ospitata.</span><span class="sxs-lookup"><span data-stu-id="a22d0-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="a22d0-106">Non sono necessarie per l'integrazione con la messaggistica unificata di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="a22d0-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="a22d0-107">Ambito dei criteri di segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="a22d0-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="a22d0-108">L'ambito dei criteri di segreteria telefonica ospitata determina il livello gerarchico a cui si applicano i criteri.</span><span class="sxs-lookup"><span data-stu-id="a22d0-108">Hosted voice mail policy scope determines the hierarchical level at which the policy applies.</span></span> <span data-ttu-id="a22d0-109">È possibile configurare i criteri di segreteria telefonica ospitata con i livelli di ambito seguenti:</span><span class="sxs-lookup"><span data-stu-id="a22d0-109">You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="a22d0-110">Il criterio *globale* può potenzialmente interessare tutti gli utenti della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a22d0-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="a22d0-111">Se un utente è abilitato per l'accesso alla messaggistica unificata di Exchange ospitata e non è stato assegnato un criterio per utente e se al sito dell'utente non è stato assegnato un criterio per il sito, viene applicato il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="a22d0-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="a22d0-112">Il criterio globale viene installato con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a22d0-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="a22d0-113">È possibile modificarla in base alle proprie esigenze, ma non è possibile rinominarla o eliminarla.</span><span class="sxs-lookup"><span data-stu-id="a22d0-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="a22d0-114">I criteri del *sito* possono influire su tutti gli utenti ospitati nel sito per cui sono definiti i criteri.</span><span class="sxs-lookup"><span data-stu-id="a22d0-114">A *site* policy can affect all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="a22d0-115">Se un utente è configurato per l'accesso alla messaggistica unificata di Exchange ospitata e non è stato assegnato un criterio per utente, verranno applicati i criteri del sito.</span><span class="sxs-lookup"><span data-stu-id="a22d0-115">If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="a22d0-116">Un criterio *per utente* può interessare solo singoli utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="a22d0-116">A *per-user* policy can affect only individual users or groups.</span></span> <span data-ttu-id="a22d0-117">Per applicare un criterio per utente, è necessario assegnare esplicitamente il criterio a singoli utenti, gruppi e oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="a22d0-117">To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a22d0-118">Nella maggior parte dei casi è necessario un solo criterio di segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="a22d0-118">In most cases, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="a22d0-119">È spesso possibile modificare il criterio globale in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="a22d0-119">You can often modify the global policy to meet all your needs.</span></span> <span data-ttu-id="a22d0-120">Se si distribuiscono più criteri per la segreteria telefonica ospitata, tutti questi criteri hanno un ambito per utente.</span><span class="sxs-lookup"><span data-stu-id="a22d0-120">If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="a22d0-121">Attributi dei criteri di segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="a22d0-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="a22d0-122">Un criterio per la segreteria telefonica definisce due attributi che l'applicazione di routing di Lync Server 2013 ExUM viene inserita nell'URI della richiesta di un messaggio di invito inviato all'implementazione della messaggistica unificata di Exchange ospitata:</span><span class="sxs-lookup"><span data-stu-id="a22d0-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="a22d0-123">**Destinazione:** Il nome di dominio completo (FQDN) del servizio di messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="a22d0-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="a22d0-124">Questo valore viene usato dal server perimetrale locale di Lync Server per scopi di routing.</span><span class="sxs-lookup"><span data-stu-id="a22d0-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a22d0-125">Il nome di dominio completo per Exchange Online è exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a22d0-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="a22d0-126">**Organizzazione:** Il nome di dominio completo del tenant nel servizio di messaggistica unificata di Exchange ospitata per le cassette postali degli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a22d0-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="a22d0-127">Un criterio per la segreteria telefonica può contenere più organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a22d0-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="a22d0-128">Se nel criterio è inclusa più di un'organizzazione, questo attributo deve essere un elenco delimitato da virgole dei tenant di Exchange Server che ospitano le cassette postali degli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a22d0-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a22d0-129">L'amministratore del tenant del servizio di messaggistica unificata di Exchange ospitata fornirà i valori necessari per le impostazioni dell'attributo di destinazione e organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a22d0-129">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings.</span></span> <span data-ttu-id="a22d0-130">Per configurare i criteri, è necessario eseguire il cmdlet New-CsHostedVoicemailPolicy o usare il cmdlet Set-CsHostedVoicemailPolicy per modificarne uno esistente, ad esempio il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="a22d0-130">To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="a22d0-131">Per informazioni dettagliate sulla gestione dei criteri di segreteria telefonica ospitata, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="a22d0-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="a22d0-132">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a22d0-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="a22d0-133">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a22d0-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="a22d0-134">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a22d0-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="a22d0-135">Assegnazione dei criteri per la segreteria telefonica per utente</span><span class="sxs-lookup"><span data-stu-id="a22d0-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="a22d0-136">Se i criteri per la segreteria telefonica ospitata sono definiti con ambito per utente, è necessario assegnarlo esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="a22d0-136">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it.</span></span> <span data-ttu-id="a22d0-137">Puoi eseguire il cmdlet Grant-CsHostedVoicemailPolicy per assegnare i criteri a singoli utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="a22d0-137">You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="a22d0-138">Per informazioni dettagliate sull'assegnazione o la rimozione di un criterio di segreteria telefonica ospitata per utente, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="a22d0-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="a22d0-139">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a22d0-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="a22d0-140">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="a22d0-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

