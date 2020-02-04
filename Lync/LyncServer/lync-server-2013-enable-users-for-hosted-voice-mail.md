---
title: 'Lync Server 2013: Abilitare gli utenti per la segreteria telefonica ospitata'
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
ms.openlocfilehash: 8e0ce9ee4da6ee0a36e5e5f0028371aab8af523f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="23b22-102">Abilitare gli utenti per la segreteria telefonica ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23b22-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23b22-103">_**Argomento Ultima modifica:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="23b22-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="23b22-104">Seguire la procedura per abilitare gli utenti di Lync Server 2013 per la segreteria telefonica in un servizio di messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="23b22-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="23b22-105">Per informazioni dettagliate, vedere [gestione degli utenti di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="23b22-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="23b22-106">Per informazioni dettagliate sul cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="23b22-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="23b22-107">Prima che un utente di Lync Server 2013 possa essere abilitato per la segreteria telefonica ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata che si applica al proprio account utente.</span><span class="sxs-lookup"><span data-stu-id="23b22-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="23b22-108">Per informazioni dettagliate, vedere Criteri per la segreteria <A href="lync-server-2013-hosted-voice-mail-policies.md">telefonica ospitati in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="23b22-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="23b22-109">Per abilitare gli utenti per la segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="23b22-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="23b22-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="23b22-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="23b22-111">Eseguire il cmdlet Set-CsUser per configurare l'account utente per la segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="23b22-111">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail.</span></span> <span data-ttu-id="23b22-112">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="23b22-112">For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="23b22-113">Nell'esempio precedente vengono impostati i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="23b22-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="23b22-114">**HostedVoiceMail** consente alle chiamate di segreteria telefonica di un utente di essere indirizzate alla messaggistica unificata di Exchange ospitata.</span><span class="sxs-lookup"><span data-stu-id="23b22-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="23b22-115">Segnala inoltre a Microsoft Lync 2013 di illuminare l'indicatore "chiama la segreteria telefonica".</span><span class="sxs-lookup"><span data-stu-id="23b22-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="23b22-116">**Identity** specifica l'account utente da modificare.</span><span class="sxs-lookup"><span data-stu-id="23b22-116">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="23b22-117">Il valore Identity può essere specificato usando uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="23b22-117">The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="23b22-118">Indirizzo SIP dell'utente</span><span class="sxs-lookup"><span data-stu-id="23b22-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="23b22-119">L'utente di Active Directory-Principal-Name dell'utente</span><span class="sxs-lookup"><span data-stu-id="23b22-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="23b22-120">Nome di accesso al\\dominio dell'utente (ad esempio,\\contoso kenmyer)</span><span class="sxs-lookup"><span data-stu-id="23b22-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="23b22-121">Il nome visualizzato dei servizi di dominio Active Directory dell'utente, ad esempio Ken.</span><span class="sxs-lookup"><span data-stu-id="23b22-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="23b22-122">Se si usa il nome visualizzato come valore di identità, è possibile usare il carattere jolly\*asterisco ().</span><span class="sxs-lookup"><span data-stu-id="23b22-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="23b22-123">Ad esempio, l'identità "\* Smith" restituisce tutti gli utenti che hanno un nome visualizzato che termina con il valore stringa "Smith".</span><span class="sxs-lookup"><span data-stu-id="23b22-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23b22-124">Il nome dell'account SAM di Active Directory dell'utente non può essere usato come valore di identità perché il nome dell'account SAM non è necessariamente univoco nella foresta.</span><span class="sxs-lookup"><span data-stu-id="23b22-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

