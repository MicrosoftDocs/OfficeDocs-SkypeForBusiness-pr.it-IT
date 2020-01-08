---
title: 'Lync Server 2013: creare un criterio per la segreteria telefonica ospitata a livello di sito'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9df91e28eeba8bc9769e4fcbeff6ebba2b3746d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="d481f-102">Creare un criterio di segreteria telefonica ospitata a livello di sito in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d481f-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d481f-103">_**Argomento Ultima modifica:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="d481f-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="d481f-104">Un criterio di *sito* può avere un impatto su tutti gli utenti ospitati nel sito per cui sono definiti i criteri.</span><span class="sxs-lookup"><span data-stu-id="d481f-104">A *site* policy can impact all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="d481f-105">Se un utente è configurato per l'accesso alla messaggistica unificata di Exchange ospitata e non è stato assegnato un criterio per utente, verranno applicati i criteri del sito.</span><span class="sxs-lookup"><span data-stu-id="d481f-105">If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies.</span></span> <span data-ttu-id="d481f-106">Se non è stato distribuito un criterio per il sito, si applicano i criteri globali.</span><span class="sxs-lookup"><span data-stu-id="d481f-106">If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="d481f-107">Per informazioni dettagliate sulla configurazione dei criteri del sito, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="d481f-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="d481f-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="d481f-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="d481f-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="d481f-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="d481f-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="d481f-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="d481f-111">Per creare un criterio per la segreteria telefonica ospitata nel sito</span><span class="sxs-lookup"><span data-stu-id="d481f-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="d481f-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d481f-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d481f-113">Eseguire il cmdlet New-CsHostedVoicemailPolicy per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="d481f-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="d481f-114">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="d481f-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="d481f-115">Questo esempio crea un criterio di segreteria telefonica ospitata con l'ambito del sito e imposta i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d481f-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="d481f-116">**Identity** specifica un identificatore univoco per il criterio, che include l'ambito.</span><span class="sxs-lookup"><span data-stu-id="d481f-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="d481f-117">Per un criterio con ambito sito, il valore del parametro Identity deve essere specificato nel `site:` \* \<nome\>\* del formato, ad esempio `site:Redmond`.</span><span class="sxs-lookup"><span data-stu-id="d481f-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="d481f-118">**Destination** specifica il nome di dominio completo (FQDN) del servizio di messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="d481f-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="d481f-119">Questo parametro è facoltativo, ma se tenti di abilitare un utente per la segreteria telefonica ospitata e il criterio assegnato dall'utente non ha un valore di destinazione, l'opzione di abilitazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d481f-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="d481f-120">**Descrizione** fornisce informazioni descrittive facoltative sui criteri.</span><span class="sxs-lookup"><span data-stu-id="d481f-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="d481f-121">**Organizzazione** specifica un elenco delimitato da virgole dei tenant di Exchange che ospitano gli utenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d481f-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="d481f-122">Ogni tenant deve essere specificato come FQDN del tenant nel servizio di messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="d481f-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

