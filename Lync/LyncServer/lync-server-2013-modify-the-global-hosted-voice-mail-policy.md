---
title: 'Lync Server 2013: modificare il criterio di segreteria telefonica ospitata globalmente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9a7e9dcb3c626c076d51fa32fa195f0787a922c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515173"
---
# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="c06dc-102">Modificare i criteri globali di segreteria telefonica ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c06dc-102">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c06dc-103">_**Ultimo argomento modificato:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="c06dc-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="c06dc-104">I criteri di segreteria telefonica *globale* ospitati sono installati con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c06dc-104">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="c06dc-105">È possibile modificarli in base a specifiche esigenze, ma non è possibile rinominarli né eliminarli.</span><span class="sxs-lookup"><span data-stu-id="c06dc-105">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="c06dc-106">Per modificare i criteri globali, utilizzare il cmdlet Set-CsHostedVoicemailPolicy per impostare i parametri sui valori appropriati per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c06dc-106">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="c06dc-107">Per informazioni dettagliate sul cmdlet [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c06dc-107">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="c06dc-108">Per modificare i criteri globali di segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="c06dc-108">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="c06dc-109">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c06dc-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c06dc-110">Eseguire il cmdlet Set-CsHostedVoicemailPolicy per impostare i parametri dei criteri globali per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c06dc-110">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="c06dc-111">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c06dc-111">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="c06dc-112">Poiché questo comando non specifica il parametro Identity del criterio, l'interfaccia della riga di comando di Windows PowerShell imposta i seguenti valori sui criteri di segreteria telefonica ospitata globale:</span><span class="sxs-lookup"><span data-stu-id="c06dc-112">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="c06dc-p103">**Destination** specifica il nome di dominio completo (FQDN) del servizio Messaggistica unificata di Exchange ospitato. Questo parametro è facoltativo, ma se si tenta di abilitare un utente per la segreteria telefonica ospitata e il criterio assegnato all'utente non dispone di un valore Destination, l'abilitazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c06dc-p103">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="c06dc-115">L' **organizzazione** specifica un elenco delimitato da virgole dei tenant di Exchange che gli utenti di Lync Server Home.</span><span class="sxs-lookup"><span data-stu-id="c06dc-115">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="c06dc-116">Ogni tenant deve essere specificato come FQDN sul tenant nel servizio di messaggistica unificata di Exchange ospitato.</span><span class="sxs-lookup"><span data-stu-id="c06dc-116">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c06dc-p105">Nell'esempio di cmdlet precedente, il valore "corp1.litwareinc.com" sostituisce eventuali valori già presenti nel parametro Organization. Se ad esempio i criteri contengono già un elenco di organizzazioni delimitate da virgola, l'elenco completo verrà sostituito. Se si desidera aggiungere un'organizzazione all'elenco anziché sostituire l'intero elenco, eseguire un comando analogo al seguente.</span><span class="sxs-lookup"><span data-stu-id="c06dc-p105">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter. For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced. If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

