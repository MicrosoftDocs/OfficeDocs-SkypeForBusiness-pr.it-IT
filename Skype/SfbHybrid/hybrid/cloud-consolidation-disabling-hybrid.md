---
title: Disabilitare l'ibrido per completare la migrazione al cloud
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questa appendice include i passaggi dettagliati per disabilitare l'ibrido come parte del consolidamento del cloud per Teams e Skype for business.
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185504"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="4ad82-103">Disabilitare l'ibrido per completare la migrazione al cloud</span><span class="sxs-lookup"><span data-stu-id="4ad82-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="4ad82-104">Dopo aver spostato tutti gli utenti dal locale al cloud, è possibile rimuovere la Commissione dalla distribuzione di Skype for business locale.</span><span class="sxs-lookup"><span data-stu-id="4ad82-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="4ad82-105">Oltre a rimuovere qualsiasi hardware, un passaggio critico consiste nel separare logicamente la distribuzione locale da Office 365 disabilitando l'ibrido.</span><span class="sxs-lookup"><span data-stu-id="4ad82-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="4ad82-106">La disattivazione dell'ibrido è costituita da 3 passaggi:</span><span class="sxs-lookup"><span data-stu-id="4ad82-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="4ad82-107">Aggiornare i record DNS in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ad82-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="4ad82-108">Disabilitare il dominio diviso nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ad82-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="4ad82-109">Disabilitare la funzionalità in on-Prem per comunicare con Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ad82-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="4ad82-110">Questa procedura dovrebbe essere eseguita insieme come unità.</span><span class="sxs-lookup"><span data-stu-id="4ad82-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="4ad82-111">Di seguito sono riportati i dettagli.</span><span class="sxs-lookup"><span data-stu-id="4ad82-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="4ad82-112">In rari casi, la modifica del DNS dal punto di riferimento locale a Office 365 per l'organizzazione può causare l'interruzione del funzionamento della Federazione con altre organizzazioni finché l'altra organizzazione non aggiorna la configurazione della Federazione:</span><span class="sxs-lookup"><span data-stu-id="4ad82-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="4ad82-113">Tutte le organizzazioni federate che usano il modello di federazione diretta precedente (noto anche come server partner consentito) dovranno aggiornare le relative voci di dominio consentite per la propria organizzazione per rimuovere l'FQDN del proxy.</span><span class="sxs-lookup"><span data-stu-id="4ad82-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="4ad82-114">Questo modello di federazione legacy non è basato sui record SRV DNS, quindi tale configurazione diventa obsoleta quando l'organizzazione si sposta nel cloud.</span><span class="sxs-lookup"><span data-stu-id="4ad82-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="4ad82-115">Qualsiasi organizzazione federata che non dispone di un provider di hosting abilitato per sipfed. online. Lync. <span>com dovrà aggiornare la configurazione per abilitarla.</span><span class="sxs-lookup"><span data-stu-id="4ad82-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="4ad82-116">Questa situazione è possibile solo se l'organizzazione federata è puramente locale e non è mai stata federata con un tenant ibrido o online.</span><span class="sxs-lookup"><span data-stu-id="4ad82-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="4ad82-117">In questo caso, la Federazione con queste organizzazioni non funzionerà finché non Abilita il proprio provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="4ad82-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="4ad82-118">Se si sospetta che i partner federati possano usare la Federazione diretta o avere federati con qualsiasi organizzazione online o ibrida, è consigliabile inviare loro una comunicazione quando si preparano a completare la migrazione al cloud.</span><span class="sxs-lookup"><span data-stu-id="4ad82-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="4ad82-119">*Aggiornare il DNS in Office 365.*</span><span class="sxs-lookup"><span data-stu-id="4ad82-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="4ad82-120">Il DNS esterno dell'organizzazione per l'organizzazione locale deve essere aggiornato in modo che i record di Skype for business puntino a Office 365 anziché alla distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="4ad82-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="4ad82-121">Specificamente</span><span class="sxs-lookup"><span data-stu-id="4ad82-121">Specifically:</span></span>

    |<span data-ttu-id="4ad82-122">Tipo di record</span><span class="sxs-lookup"><span data-stu-id="4ad82-122">Record type</span></span>|<span data-ttu-id="4ad82-123">Nome</span><span class="sxs-lookup"><span data-stu-id="4ad82-123">Name</span></span>|<span data-ttu-id="4ad82-124">TTL</span><span class="sxs-lookup"><span data-stu-id="4ad82-124">TTL</span></span>|<span data-ttu-id="4ad82-125">Valore</span><span class="sxs-lookup"><span data-stu-id="4ad82-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="4ad82-126">SRV</span><span class="sxs-lookup"><span data-stu-id="4ad82-126">SRV</span></span>|<span data-ttu-id="4ad82-127">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="4ad82-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="4ad82-128">3600</span><span class="sxs-lookup"><span data-stu-id="4ad82-128">3600</span></span>|<span data-ttu-id="4ad82-129">100 1 5061 sipfed. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="4ad82-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4ad82-130">SRV</span><span class="sxs-lookup"><span data-stu-id="4ad82-130">SRV</span></span>|<span data-ttu-id="4ad82-131">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="4ad82-131">_sip._tls</span></span>|<span data-ttu-id="4ad82-132">3600</span><span class="sxs-lookup"><span data-stu-id="4ad82-132">3600</span></span>|<span data-ttu-id="4ad82-133">100 1 443 sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="4ad82-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4ad82-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="4ad82-134">CNAME</span></span>| <span data-ttu-id="4ad82-135">Lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4ad82-135">lyncdiscover</span></span>|   <span data-ttu-id="4ad82-136">3600</span><span class="sxs-lookup"><span data-stu-id="4ad82-136">3600</span></span>|   <span data-ttu-id="4ad82-137">WEBDIR. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="4ad82-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4ad82-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="4ad82-138">CNAME</span></span>| <span data-ttu-id="4ad82-139">SIP</span><span class="sxs-lookup"><span data-stu-id="4ad82-139">sip</span></span>|    <span data-ttu-id="4ad82-140">3600</span><span class="sxs-lookup"><span data-stu-id="4ad82-140">3600</span></span>|   <span data-ttu-id="4ad82-141">sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="4ad82-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4ad82-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="4ad82-142">CNAME</span></span>| <span data-ttu-id="4ad82-143">soddisfano</span><span class="sxs-lookup"><span data-stu-id="4ad82-143">meet</span></span>|   <span data-ttu-id="4ad82-144">3600</span><span class="sxs-lookup"><span data-stu-id="4ad82-144">3600</span></span>|   <span data-ttu-id="4ad82-145">WEBDIR. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="4ad82-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4ad82-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="4ad82-146">CNAME</span></span>| <span data-ttu-id="4ad82-147">telefonica</span><span class="sxs-lookup"><span data-stu-id="4ad82-147">dialin</span></span>  |<span data-ttu-id="4ad82-148">3600</span><span class="sxs-lookup"><span data-stu-id="4ad82-148">3600</span></span>|  <span data-ttu-id="4ad82-149">WEBDIR. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="4ad82-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="4ad82-150">*Disabilitare lo spazio di indirizzi SIP condiviso in Office 365 tenant.*</span><span class="sxs-lookup"><span data-stu-id="4ad82-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="4ad82-151">Il comando seguente deve essere eseguito da una finestra di PowerShell di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="4ad82-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="4ad82-152">*Disabilitare la funzionalità in on-Prem per comunicare con Office 365.*</span><span class="sxs-lookup"><span data-stu-id="4ad82-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="4ad82-153">Il comando seguente deve essere eseguito da una finestra di PowerShell locale.</span><span class="sxs-lookup"><span data-stu-id="4ad82-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="4ad82-154">Se in precedenza è stata importata una sessione di Skype for business online, avviare una nuova sessione di PowerShell per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="4ad82-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="4ad82-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ad82-155">See also</span></span>

[<span data-ttu-id="4ad82-156">Consolidamento cloud per Teams e Skype for business</span><span class="sxs-lookup"><span data-stu-id="4ad82-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)