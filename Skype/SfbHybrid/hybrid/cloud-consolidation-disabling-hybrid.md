---
title: Disabilitare la soluzione ibrida per completare la migrazione al cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: In questa appendice sono riportati i passaggi dettagliati per la disabilitazione dell'ibrido come parte del consolidamento cloud per Teams e Skype for business.
ms.openlocfilehash: 039e8a30495567fe818fe4d60b863f37cf94e049
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918735"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="af6fb-103">Disabilitare la soluzione ibrida per completare la migrazione al cloud</span><span class="sxs-lookup"><span data-stu-id="af6fb-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="af6fb-104">Dopo aver spostato tutti gli utenti dall'infrastruttura locale al cloud, è possibile ritirare la distribuzione locale di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="af6fb-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="af6fb-105">Oltre a rimuovere eventuale hardware, un passaggio critico è quello di separare logicamente la distribuzione locale da Office 365 disabilitando l'ambiente ibrido.</span><span class="sxs-lookup"><span data-stu-id="af6fb-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="af6fb-106">La disattivazione dell'ibrido è costituita da tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="af6fb-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="af6fb-107">Aggiornare i record NS in modo che puntino a Office 365.</span><span class="sxs-lookup"><span data-stu-id="af6fb-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="af6fb-108">Disabilitare il dominio diviso nell'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="af6fb-108">Disable split domain in the Office 365 organization.</span></span>

3. <span data-ttu-id="af6fb-109">Disabilitare l'abilità in locale per comunicare con Office 365.</span><span class="sxs-lookup"><span data-stu-id="af6fb-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="af6fb-110">Questi passaggi devono essere eseguiti insieme come unità.</span><span class="sxs-lookup"><span data-stu-id="af6fb-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="af6fb-111">I dettagli sono riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="af6fb-111">Details are provided below.</span></span> <span data-ttu-id="af6fb-112">Inoltre, vengono fornite linee guida per la gestione dei numeri di telefono per gli utenti migrati dopo che la distribuzione locale è stata disconnessa.</span><span class="sxs-lookup"><span data-stu-id="af6fb-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="af6fb-113">In rari casi, la modifica del DNS dal punto di vista locale a Office 365 per l'organizzazione può causare la Federazione con alcune altre organizzazioni di smettere di funzionare fino a quando l'altra organizzazione non aggiorna la configurazione della Federazione:</span><span class="sxs-lookup"><span data-stu-id="af6fb-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="af6fb-114">Qualsiasi organizzazione federata che utilizza il modello di Federazione diretto meno recente (noto anche come server partner consentito) dovrà aggiornare le voci di dominio consentite per la propria azienda per rimuovere il nome FQDN del proxy.</span><span class="sxs-lookup"><span data-stu-id="af6fb-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="af6fb-115">Questo modello di federazione legacy non è basato sui record DNS SRV, quindi tale configurazione diventerà obsoleta dopo lo spostamento dell'organizzazione nel cloud.</span><span class="sxs-lookup"><span data-stu-id="af6fb-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="af6fb-116">Qualsiasi organizzazione federata che non disponga di un provider di hosting abilitato per sipfed. online. Lync. <span>com sarà necessario aggiornare la propria configurazione per abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="af6fb-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="af6fb-117">Questa situazione è possibile solo se l'organizzazione federata è puramente locale e non è mai stata federata con nessun tenant ibrido o online.</span><span class="sxs-lookup"><span data-stu-id="af6fb-117">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="af6fb-118">In tal caso, la Federazione con queste organizzazioni non funzionerà finché non Abilita il proprio provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="af6fb-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="af6fb-119">Se si sospetta che uno qualsiasi dei partner federati possa utilizzare la Federazione diretta o che non sia stato federato con nessuna organizzazione online o ibrida, è consigliabile inviare loro una comunicazione durante la preparazione per completare la migrazione nel cloud.</span><span class="sxs-lookup"><span data-stu-id="af6fb-119">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="af6fb-120">*Aggiornare il DNS in modo che punti a Office 365.*</span><span class="sxs-lookup"><span data-stu-id="af6fb-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="af6fb-121">Il DNS esterno dell'organizzazione per l'organizzazione locale deve essere aggiornato in modo che i record Skype for business puntino a Office 365 anziché alla distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="af6fb-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="af6fb-122">In particolare:</span><span class="sxs-lookup"><span data-stu-id="af6fb-122">Specifically:</span></span>

    |<span data-ttu-id="af6fb-123">Tipo di record</span><span class="sxs-lookup"><span data-stu-id="af6fb-123">Record type</span></span>|<span data-ttu-id="af6fb-124">Nome</span><span class="sxs-lookup"><span data-stu-id="af6fb-124">Name</span></span>|<span data-ttu-id="af6fb-125">TTL</span><span class="sxs-lookup"><span data-stu-id="af6fb-125">TTL</span></span>|<span data-ttu-id="af6fb-126">Value</span><span class="sxs-lookup"><span data-stu-id="af6fb-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="af6fb-127">SRV</span><span class="sxs-lookup"><span data-stu-id="af6fb-127">SRV</span></span>|<span data-ttu-id="af6fb-128">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="af6fb-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="af6fb-129">3600</span><span class="sxs-lookup"><span data-stu-id="af6fb-129">3600</span></span>|<span data-ttu-id="af6fb-130">100 1 5061 sipfed. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="af6fb-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="af6fb-131">SRV</span><span class="sxs-lookup"><span data-stu-id="af6fb-131">SRV</span></span>|<span data-ttu-id="af6fb-132">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="af6fb-132">_sip._tls</span></span>|<span data-ttu-id="af6fb-133">3600</span><span class="sxs-lookup"><span data-stu-id="af6fb-133">3600</span></span>|<span data-ttu-id="af6fb-134">100 1 443 sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="af6fb-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="af6fb-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="af6fb-135">CNAME</span></span>| <span data-ttu-id="af6fb-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="af6fb-136">lyncdiscover</span></span>|   <span data-ttu-id="af6fb-137">3600</span><span class="sxs-lookup"><span data-stu-id="af6fb-137">3600</span></span>|   <span data-ttu-id="af6fb-138">WEBDIR. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="af6fb-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="af6fb-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="af6fb-139">CNAME</span></span>| <span data-ttu-id="af6fb-140">sip</span><span class="sxs-lookup"><span data-stu-id="af6fb-140">sip</span></span>|    <span data-ttu-id="af6fb-141">3600</span><span class="sxs-lookup"><span data-stu-id="af6fb-141">3600</span></span>|   <span data-ttu-id="af6fb-142">sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="af6fb-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="af6fb-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="af6fb-143">CNAME</span></span>| <span data-ttu-id="af6fb-144">soddisfare</span><span class="sxs-lookup"><span data-stu-id="af6fb-144">meet</span></span>|   <span data-ttu-id="af6fb-145">3600</span><span class="sxs-lookup"><span data-stu-id="af6fb-145">3600</span></span>|   <span data-ttu-id="af6fb-146">WEBDIR. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="af6fb-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="af6fb-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="af6fb-147">CNAME</span></span>| <span data-ttu-id="af6fb-148">Dialin</span><span class="sxs-lookup"><span data-stu-id="af6fb-148">dialin</span></span>  |<span data-ttu-id="af6fb-149">3600</span><span class="sxs-lookup"><span data-stu-id="af6fb-149">3600</span></span>|  <span data-ttu-id="af6fb-150">WEBDIR. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="af6fb-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="af6fb-151">*Disabilitare lo spazio degli indirizzi SIP condiviso nell'organizzazione di Office 365.*</span><span class="sxs-lookup"><span data-stu-id="af6fb-151">*Disable shared SIP address space in Office 365 organization.*</span></span>
<span data-ttu-id="af6fb-152">Il comando seguente deve essere effettuato da una finestra di PowerShell di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="af6fb-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="af6fb-153">*Disabilitare l'abilità in locale per comunicare con Office 365.*</span><span class="sxs-lookup"><span data-stu-id="af6fb-153">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="af6fb-154">Il comando seguente deve essere effettuato da una finestra di PowerShell locale:</span><span class="sxs-lookup"><span data-stu-id="af6fb-154">The command below needs to be done from an on-premises PowerShell window:</span></span>

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="af6fb-155">Gestire i numeri di telefono per gli utenti di cui è stata eseguita la migrazione da locale</span><span class="sxs-lookup"><span data-stu-id="af6fb-155">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="af6fb-156">Gli amministratori possono gestire gli utenti precedentemente spostati da un server Skype for business locale al cloud, anche dopo che la distribuzione locale è stata disattivata.</span><span class="sxs-lookup"><span data-stu-id="af6fb-156">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="af6fb-157">Sono disponibili due diverse possibilità:</span><span class="sxs-lookup"><span data-stu-id="af6fb-157">There are two different possibilities:</span></span>

- <span data-ttu-id="af6fb-158">L'utente non dispone di un valore per LineURI in locale prima dello spostamento.</span><span class="sxs-lookup"><span data-stu-id="af6fb-158">The user did not have a value for LineURI on-premises before the move.</span></span> 

  <span data-ttu-id="af6fb-159">In questo caso, è possibile modificare il LineURI utilizzando i parametri-onpremLineUri nel [cmdlet Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) nel modulo di PowerShell di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="af6fb-159">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

- <span data-ttu-id="af6fb-160">L'utente dispone di un LineURI locale prima dello spostamento (presumibilmente perché l'utente è stato abilitato per VoIP aziendale).</span><span class="sxs-lookup"><span data-stu-id="af6fb-160">The user had a LineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="af6fb-161">Se si desidera modificare il LineURI, è necessario eseguire questa operazione in Active Directory locale e lasciare il flusso di valore fino a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="af6fb-161">If you want to change the LineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="af6fb-162">Questo non richiede Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="af6fb-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="af6fb-163">Questo attributo, msRTCSIP-line, può invece essere modificato direttamente in Active Directory locale, utilizzando lo snap-in MMC utenti e computer di Active Directory o tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af6fb-163">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="af6fb-164">Se si utilizza lo snap-in MMC, aprire alla pagina delle proprietà dell'utente, fare clic su Attribute Editor Tab e trovare msRTCSIP-line.</span><span class="sxs-lookup"><span data-stu-id="af6fb-164">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Strumento utenti e computer di Active Directory](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="af6fb-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af6fb-166">See also</span></span>

[<span data-ttu-id="af6fb-167">Consolidamento cloud per Teams e Skype for business</span><span class="sxs-lookup"><span data-stu-id="af6fb-167">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
