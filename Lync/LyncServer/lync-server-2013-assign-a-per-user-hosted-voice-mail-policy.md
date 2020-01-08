---
title: 'Lync Server 2013: assegnare un criterio di segreteria telefonica ospitata per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2202e1b4c03eb25d12e46c3a533313a54bc76c4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980739"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="be54d-102">Assegnare un criterio di segreteria telefonica ospitata per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be54d-102">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="be54d-103">La distribuzione di uno o più criteri per la segreteria telefonica ospitata per utente è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="be54d-103">Deploying one or more per-user hosted voice mail policies is optional.</span></span> <span data-ttu-id="be54d-104">Se si distribuiscono criteri per utente, è necessario assegnarli esplicitamente a utenti, gruppi o oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="be54d-104">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="be54d-105">Per informazioni dettagliate sull'assegnazione o la rimozione dell'assegnazione di criteri per la segreteria telefonica ospitata per utente, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="be54d-105">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="be54d-106">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="be54d-106">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="be54d-107">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="be54d-107">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="be54d-108">Per assegnare un criterio di segreteria telefonica ospitata per utente</span><span class="sxs-lookup"><span data-stu-id="be54d-108">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="be54d-109">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="be54d-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="be54d-110">Eseguire il cmdlet Grant-CsHostedVoicemailPolicy per assegnare i criteri di segreteria telefonica ospitata per utente a singoli utenti, gruppi e oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="be54d-110">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects.</span></span> <span data-ttu-id="be54d-111">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="be54d-111">For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="be54d-112">In questo esempio sono stati assegnati i criteri di segreteria telefonica ospitati da ExRedmond all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="be54d-112">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="be54d-113">**Identity** specifica l'account utente da modificare.</span><span class="sxs-lookup"><span data-stu-id="be54d-113">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="be54d-114">Il valore Identity può essere specificato usando uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="be54d-114">The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="be54d-115">Indirizzo SIP dell'utente</span><span class="sxs-lookup"><span data-stu-id="be54d-115">The user's SIP address</span></span>
    
      - <span data-ttu-id="be54d-116">L'utente di Active Directory-Principal-Name dell'utente</span><span class="sxs-lookup"><span data-stu-id="be54d-116">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="be54d-117">Nome di accesso al\\dominio dell'utente (ad esempio,\\contoso kenmyer)</span><span class="sxs-lookup"><span data-stu-id="be54d-117">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="be54d-118">Il nome visualizzato dei servizi di dominio Active Directory dell'utente, ad esempio Ken.</span><span class="sxs-lookup"><span data-stu-id="be54d-118">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="be54d-119">Se si usa il nome visualizzato come valore di identità, è possibile usare il carattere jolly\*asterisco ().</span><span class="sxs-lookup"><span data-stu-id="be54d-119">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="be54d-120">Ad esempio, l'identità "\* Smith" restituisce tutti gli utenti che hanno un nome visualizzato che termina con il valore stringa "Smith".</span><span class="sxs-lookup"><span data-stu-id="be54d-120">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="be54d-121">Il nome dell'account SAM di Active Directory dell'utente non può essere usato come valore di identità perché il nome dell'account SAM non è necessariamente univoco nella foresta.</span><span class="sxs-lookup"><span data-stu-id="be54d-121">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


