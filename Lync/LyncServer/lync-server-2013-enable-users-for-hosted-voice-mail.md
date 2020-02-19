---
title: 'Lync Server 2013: abilitare gli utenti per la segreteria telefonica ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dc71125b42fab144b1c6ba15064e84c6be50b57
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="8866b-102">Abilitare gli utenti per la segreteria telefonica ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8866b-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8866b-103">_**Ultimo argomento modificato:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="8866b-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="8866b-104">Seguire la procedura per abilitare gli utenti di Lync Server 2013 per la segreteria telefonica in un servizio di messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="8866b-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="8866b-105">Per ulteriori informazioni, vedere [gestione degli utenti di Exchange ospitati in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8866b-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="8866b-106">Per informazioni dettagliate sul cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8866b-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8866b-107">Prima che un utente di Lync Server 2013 possa essere abilitato per la segreteria telefonica ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata che si applica al proprio account utente.</span><span class="sxs-lookup"><span data-stu-id="8866b-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="8866b-108">Per ulteriori informazioni, vedere <A href="lync-server-2013-hosted-voice-mail-policies.md">criteri di segreteria telefonica ospitata in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8866b-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="8866b-109">Per abilitare gli utenti per la segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="8866b-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="8866b-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8866b-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8866b-111">Eseguire il cmdlet Set-CsUser per configurare l'account utente per la segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="8866b-111">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail.</span></span> <span data-ttu-id="8866b-112">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="8866b-112">For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="8866b-113">Nell'esempio precedente vengono impostati i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="8866b-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="8866b-114">**HostedVoiceMail** consente di instradare le chiamate di posta vocale di un utente alla messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="8866b-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="8866b-115">Segnala inoltre Microsoft Lync 2013 per accendere l'indicatore "segreteria telefonica chiamata".</span><span class="sxs-lookup"><span data-stu-id="8866b-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="8866b-p104">**Identity** specifica l'account utente da modificare. Il valore di Identity può essere specificato utilizzando uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="8866b-p104">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="8866b-118">Indirizzo SIP dell'utente</span><span class="sxs-lookup"><span data-stu-id="8866b-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="8866b-119">Nome dell'entità utente di Active Directory</span><span class="sxs-lookup"><span data-stu-id="8866b-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="8866b-120">Nome di accesso del\\dominio dell'utente (ad esempio,\\contoso kenmyer)</span><span class="sxs-lookup"><span data-stu-id="8866b-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="8866b-121">Nome visualizzato dei servizi di dominio Active Directory dell'utente, ad esempio Davide Garghentini.</span><span class="sxs-lookup"><span data-stu-id="8866b-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="8866b-122">Se si utilizza il nome visualizzato come valore Identity, è possibile utilizzare il carattere jolly asterisco\*().</span><span class="sxs-lookup"><span data-stu-id="8866b-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="8866b-123">Ad esempio, il parametro Identity\* "Smith" restituisce tutti gli utenti che dispongono di un nome visualizzato che termina con il valore stringa "Smith".</span><span class="sxs-lookup"><span data-stu-id="8866b-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8866b-124">Il nome account SAM di Active Directory dell'utente non può essere utilizzato come valore di Identity perché non è necessariamente univoco nella foresta.</span><span class="sxs-lookup"><span data-stu-id="8866b-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

