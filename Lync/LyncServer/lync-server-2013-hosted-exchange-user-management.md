---
title: 'Lync Server 2013: gestione degli utenti di Exchange ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cceaeaa869d1e058251a62d237c563143a4ae4c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="ec50b-102">Gestione degli utenti di Exchange ospitati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec50b-102">Hosted Exchange user management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec50b-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ec50b-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ec50b-104">Per fornire servizi di segreteria telefonica per gli utenti di Lync Server 2013 le cui cassette postali si trovano in un servizio di Exchange ospitato, è necessario abilitare gli account utente per la segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="ec50b-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec50b-105">Prima che un utente di Lync Server 2013 possa essere abilitato per la segreteria telefonica ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata che si applica all'account utente corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ec50b-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="ec50b-106">I criteri possono avere ambito globale, a livello di sito o per utente, purché siano applicabili all'utente da abilitare.</span><span class="sxs-lookup"><span data-stu-id="ec50b-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="ec50b-107">Per ulteriori informazioni, vedere <A href="lync-server-2013-hosted-voice-mail-policies.md">criteri di segreteria telefonica ospitata in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ec50b-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="ec50b-108">Attributo msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="ec50b-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="ec50b-109">Lync Server 2013 introduce un nuovo attributo utente denominato **msExchUCVoiceMailSettings**, creato come parte della preparazione dello schema di Active Directory di lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ec50b-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="ec50b-110">Questo attributo multivalore contiene le impostazioni della segreteria telefonica condivise da Lync Server 2013 e il servizio Exchange ospitato.</span><span class="sxs-lookup"><span data-stu-id="ec50b-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="ec50b-111">Il servizio Exchange ospitato può in alcuni casi impostare il valore dell'attributo msExchUCVoiceMailSettings nel processo di abilitazione della messaggistica unificata di Exchange oppure durante il trasferimento di cassette postali in un computer Exchange Server ospitato.</span><span class="sxs-lookup"><span data-stu-id="ec50b-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="ec50b-112">Se questo attributo non è impostato da Exchange, l'amministratore di Lync Server 2013 deve impostarlo eseguendo il cmdlet Set-CsUser, come descritto in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ec50b-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="ec50b-113">Le coppie chiave/valore dell'attributo e i relativi autori sono illustrati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ec50b-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="ec50b-114">Coppie chiave/valore dell'attributo msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="ec50b-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec50b-115">Valore</span><span class="sxs-lookup"><span data-stu-id="ec50b-115">Value</span></span></th>
<th><span data-ttu-id="ec50b-116">Author</span><span class="sxs-lookup"><span data-stu-id="ec50b-116">Author</span></span></th>
<th><span data-ttu-id="ec50b-117">Significato</span><span class="sxs-lookup"><span data-stu-id="ec50b-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec50b-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="ec50b-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="ec50b-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="ec50b-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="ec50b-120">L'utente è stato abilitato per l'accesso alla messaggistica unificata ospitata da Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="ec50b-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="ec50b-121">L'applicazione di routing della messaggistica unificata di Exchange verificherà i criteri di segreteria telefonica ospitata per i dettagli del routing.</span><span class="sxs-lookup"><span data-stu-id="ec50b-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec50b-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="ec50b-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="ec50b-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="ec50b-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="ec50b-124">L'utente è stato disabilitato per l'accesso alla messaggistica unificata ospitata da Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="ec50b-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec50b-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="ec50b-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="ec50b-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="ec50b-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="ec50b-127">L'utente è stato abilitato per l'accesso alla messaggistica unificata ospitata da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ec50b-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="ec50b-128">L'applicazione di routing Lync Server 2013 ExUM verificherà i criteri di segreteria telefonica ospitata dell'utente per i dettagli del routing.</span><span class="sxs-lookup"><span data-stu-id="ec50b-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec50b-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="ec50b-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="ec50b-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="ec50b-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="ec50b-131">L'utente è stato disabilitato per l'accesso alla messaggistica unificata ospitata da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ec50b-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ec50b-132">Se l'attributo ha già valori diversi da una delle coppie chiave/valore di Lync Server 2013 (CSHostedVoiceMail = 0 o CSHostedVoiceMail = 1), un avviso indicherà che l'attributo può essere gestito da un'altra applicazione.</span><span class="sxs-lookup"><span data-stu-id="ec50b-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="ec50b-133">Questo messaggio di avviso verrà ad esempio visualizzato se la coppia chiave/valore ExchangeHostedVoiceMail=0 o ExchangeHostedVoiceMail=1 è già presente.</span><span class="sxs-lookup"><span data-stu-id="ec50b-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="ec50b-134">In questo caso, è possibile modificare il valore in Active Directory o eseguire il cmdlet seguente per impostarlo su null:</span><span class="sxs-lookup"><span data-stu-id="ec50b-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="ec50b-135">Set-CsUser –identity user –HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="ec50b-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="ec50b-136">Abilitazione degli utenti per la segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="ec50b-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="ec50b-137">Per consentire l'instradamento delle chiamate alla segreteria telefonica di un utente nella messaggistica unificata di Exchange ospitata, è necessario eseguire il cmdlet Set-CsUser per impostare il valore del parametro *HostedVoiceMail*.</span><span class="sxs-lookup"><span data-stu-id="ec50b-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="ec50b-138">Questo parametro segnala inoltre che Lync Server 2013 accende l'indicatore di "segreteria telefonica chiamata".</span><span class="sxs-lookup"><span data-stu-id="ec50b-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="ec50b-139">Nell'esempio seguente l'account utente di Luisa Cazzaniga viene abilitato per la segreteria telefonica ospitata:</span><span class="sxs-lookup"><span data-stu-id="ec50b-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="ec50b-p108">Il cmdlet verifica che i criteri di segreteria telefonica ospitata (globali, a livello di sito o per utente) siano applicabili all'utente. Se nessun criterio è applicabile il cmdlet non riesce.</span><span class="sxs-lookup"><span data-stu-id="ec50b-p108">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user. If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="ec50b-142">Nell'esempio seguente l'account utente di Luisa Cazzaniga viene disabilitato per la segreteria telefonica ospitata:</span><span class="sxs-lookup"><span data-stu-id="ec50b-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="ec50b-p109">Il cmdlet verifica che nessun criterio di segreteria telefonica ospitata (globali, a livello di sito o per utente) sia applicabile all'utente. Se un criterio è applicabile il cmdlet non riesce.</span><span class="sxs-lookup"><span data-stu-id="ec50b-p109">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user. If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="ec50b-145">Per informazioni dettagliate sull'utilizzo del cmdlet Set-CsUser, vedere la documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ec50b-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

