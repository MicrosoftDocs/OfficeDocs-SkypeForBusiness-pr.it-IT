---
title: 'Lync Server 2013: assegnare un criterio di segreteria telefonica ospitata per utente'
description: 'Lync Server 2013: assegnare un criterio di segreteria telefonica ospitata per utente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559892"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="24d78-103">Assegnare criteri di segreteria telefonica ospitata per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24d78-103">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="24d78-p101">La distribuzione di uno o più criteri di segreteria telefonica ospitata per utente è facoltativa. Se si distribuiscono i criteri per utente, è necessario assegnarli in modo esplicito a utenti, gruppi o oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="24d78-p101">Deploying one or more per-user hosted voice mail policies is optional. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="24d78-106">Per informazioni dettagliate sull'assegnazione o la rimozione dell'assegnazione dei criteri di segreteria telefonica ospitata per utente, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="24d78-106">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="24d78-107">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="24d78-107">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="24d78-108">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="24d78-108">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="24d78-109">Per assegnare criteri di segreteria telefonica ospitata per utente</span><span class="sxs-lookup"><span data-stu-id="24d78-109">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="24d78-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="24d78-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="24d78-p102">Eseguire il cmdlet Grant-CsHostedVoicemailPolicy per assegnare criteri di segreteria telefonica ospitata per utente a singoli utenti, gruppi e oggetti contatto. Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="24d78-p102">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects. For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="24d78-113">In questo esempio il criterio ExRedmond è stato assegnato all'utente Davide Garghentini.</span><span class="sxs-lookup"><span data-stu-id="24d78-113">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="24d78-p103">**Identity** specifica l'account utente da modificare. Il valore di Identity può essere specificato utilizzando uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="24d78-p103">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="24d78-116">Indirizzo SIP dell'utente</span><span class="sxs-lookup"><span data-stu-id="24d78-116">The user's SIP address</span></span>
    
      - <span data-ttu-id="24d78-117">Nome dell'entità utente di Active Directory</span><span class="sxs-lookup"><span data-stu-id="24d78-117">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="24d78-118">Nome di accesso del dominio dell'utente \\ (ad esempio, Contoso \\ kenmyer)</span><span class="sxs-lookup"><span data-stu-id="24d78-118">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="24d78-119">Nome visualizzato dei servizi di dominio Active Directory dell'utente, ad esempio Davide Garghentini.</span><span class="sxs-lookup"><span data-stu-id="24d78-119">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="24d78-120">Se si utilizza il Display-Name come valore Identity, è possibile utilizzare il \* carattere jolly asterisco ().</span><span class="sxs-lookup"><span data-stu-id="24d78-120">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="24d78-121">Ad esempio, il parametro Identity " \* Smith" restituisce tutti gli utenti che dispongono di un Display-Name che termina con il valore stringa "Smith".</span><span class="sxs-lookup"><span data-stu-id="24d78-121">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="24d78-122">Il nome account SAM di Active Directory dell'utente non può essere utilizzato come valore di Identity perché non è necessariamente univoco nella foresta.</span><span class="sxs-lookup"><span data-stu-id="24d78-122">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


