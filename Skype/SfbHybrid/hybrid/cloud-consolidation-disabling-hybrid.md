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
description: Questo articolo include la procedura dettagliata per disabilitare l'ambiente ibrido come parte del consolidamento del cloud per Teams e Skype for Business.
ms.openlocfilehash: 18bda898563e10dbf964ba149f27202372fbcceb
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656702"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-the-cloud"></a><span data-ttu-id="1fc70-103">Disabilitare la configurazione ibrida per completare la migrazione nel cloud</span><span class="sxs-lookup"><span data-stu-id="1fc70-103">Disable your hybrid configuration to complete migration to the cloud</span></span>

<span data-ttu-id="1fc70-104">Questo articolo descrive come disabilitare la configurazione ibrida prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="1fc70-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="1fc70-105">Questo è il passaggio 2 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:</span><span class="sxs-lookup"><span data-stu-id="1fc70-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="1fc70-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="1fc70-106">Step 1.</span></span> <span data-ttu-id="1fc70-107">[Spostare tutti gli utenti necessari da locale a online.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="1fc70-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="1fc70-108">**Passaggio 2. Disabilitare la configurazione ibrida.**</span><span class="sxs-lookup"><span data-stu-id="1fc70-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="1fc70-109">(Questo articolo)</span><span class="sxs-lookup"><span data-stu-id="1fc70-109">(This article)</span></span>

- <span data-ttu-id="1fc70-110">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="1fc70-110">Step 3.</span></span> <span data-ttu-id="1fc70-111">[Spostare gli endpoint dell'applicazione ibrida da locale a online.](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="1fc70-111">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="1fc70-112">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="1fc70-112">Step 4.</span></span> <span data-ttu-id="1fc70-113">Rimuovere la distribuzione locale di [Skype for Business.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="1fc70-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="overview"></a><span data-ttu-id="1fc70-114">Panoramica</span><span class="sxs-lookup"><span data-stu-id="1fc70-114">Overview</span></span>

<span data-ttu-id="1fc70-115">Dopo aver aggiornato tutti gli utenti da Skype for Business locale a Teams Only in Microsoft 365, è possibile rimuovere le autorizzazioni per la distribuzione locale di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="1fc70-115">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="1fc70-116">Prima di rimuovere la distribuzione locale di Skype for Business e rimuovere qualsiasi hardware, è necessario separare logicamente la distribuzione locale da Microsoft 365 disabilitando la distribuzione ibrida.</span><span class="sxs-lookup"><span data-stu-id="1fc70-116">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="1fc70-117">La disabilitazione ibrida prevede i tre passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1fc70-117">Disabling hybrid consists of the following three steps:</span></span>

1. <span data-ttu-id="1fc70-118">Aggiornare i record NS in modo che puntino a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1fc70-118">Update DNS records to point to Microsoft 365.</span></span>

2. <span data-ttu-id="1fc70-119">Disabilitare lo spazio di indirizzi SIP condiviso (noto anche come "dominio diviso") nell'organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1fc70-119">Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization.</span></span>

3. <span data-ttu-id="1fc70-120">Disabilitare la possibilità in locale di comunicare con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1fc70-120">Disable the ability in on-premises to communicate with Microsoft 365.</span></span>

<span data-ttu-id="1fc70-121">Questi passaggi separano logicamente la distribuzione locale di Skype for Business Server da Microsoft 365 e devono essere evasi insieme come unità.</span><span class="sxs-lookup"><span data-stu-id="1fc70-121">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and should be done together as a unit.</span></span> <span data-ttu-id="1fc70-122">In questo articolo vengono forniti i dettagli per ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="1fc70-122">Details for each step are provided in this article.</span></span> <span data-ttu-id="1fc70-123">Al termine, puoi rimuovere le autorizzazioni per la distribuzione locale di Skype for Business usando uno dei due metodi indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="1fc70-123">Once that is complete, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced below.</span></span>

> [!Important] 
> <span data-ttu-id="1fc70-124">Una volta completata questa separazione logica, gli attributi msRTCSIP da Active Directory locale hanno ancora valori e continueranno a essere sincronizzati tramite Azure AD Connect in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1fc70-124">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="1fc70-125">La modalità di rimozione delle autorizzazioni per l'ambiente locale dipende dal fatto che si intenda o meno lasciare tali attributi sul posto o prima di cancellarli da Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="1fc70-125">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="1fc70-126">Tenere presente che la cancellazione degli attributi msRTCSIP locali dopo la migrazione dall'ambiente locale potrebbe comportare la perdita del servizio per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1fc70-126">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="1fc70-127">I dettagli e i compromessi dei due approcci di rimozione delle autorizzazioni sono descritti più avanti.</span><span class="sxs-lookup"><span data-stu-id="1fc70-127">Details and tradeoffs of the two decommissioning approaches are described later.</span></span>

## <a name="detailed-steps"></a><span data-ttu-id="1fc70-128">Passaggi dettagliati</span><span class="sxs-lookup"><span data-stu-id="1fc70-128">Detailed Steps</span></span>

1. <span data-ttu-id="1fc70-129">*Aggiornare DNS in modo che punti a Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="1fc70-129">*Update DNS to point to Microsoft 365.*</span></span> <span data-ttu-id="1fc70-130">Il DNS esterno dell'organizzazione per l'organizzazione locale deve essere aggiornato in modo che i record di Skype for Business puntino a Microsoft 365 anziché alla distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="1fc70-130">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="1fc70-131">In particolare:</span><span class="sxs-lookup"><span data-stu-id="1fc70-131">Specifically:</span></span>

    |<span data-ttu-id="1fc70-132">Tipo di record</span><span class="sxs-lookup"><span data-stu-id="1fc70-132">Record type</span></span>|<span data-ttu-id="1fc70-133">Nome</span><span class="sxs-lookup"><span data-stu-id="1fc70-133">Name</span></span>|<span data-ttu-id="1fc70-134">TTL</span><span class="sxs-lookup"><span data-stu-id="1fc70-134">TTL</span></span>|<span data-ttu-id="1fc70-135">Value</span><span class="sxs-lookup"><span data-stu-id="1fc70-135">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="1fc70-136">SRV</span><span class="sxs-lookup"><span data-stu-id="1fc70-136">SRV</span></span>|<span data-ttu-id="1fc70-137">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="1fc70-137">_sipfederationtls._tcp</span></span>|<span data-ttu-id="1fc70-138">3600</span><span class="sxs-lookup"><span data-stu-id="1fc70-138">3600</span></span>|<span data-ttu-id="1fc70-139">100 1 5061 sipfed.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="1fc70-139">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="1fc70-140">SRV</span><span class="sxs-lookup"><span data-stu-id="1fc70-140">SRV</span></span>|<span data-ttu-id="1fc70-141">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="1fc70-141">_sip._tls</span></span>|<span data-ttu-id="1fc70-142">3600</span><span class="sxs-lookup"><span data-stu-id="1fc70-142">3600</span></span>|<span data-ttu-id="1fc70-143">100 1 443 sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="1fc70-143">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="1fc70-144">CNAME</span><span class="sxs-lookup"><span data-stu-id="1fc70-144">CNAME</span></span>| <span data-ttu-id="1fc70-145">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1fc70-145">lyncdiscover</span></span>|   <span data-ttu-id="1fc70-146">3600</span><span class="sxs-lookup"><span data-stu-id="1fc70-146">3600</span></span>|   <span data-ttu-id="1fc70-147">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="1fc70-147">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="1fc70-148">CNAME</span><span class="sxs-lookup"><span data-stu-id="1fc70-148">CNAME</span></span>| <span data-ttu-id="1fc70-149">sip</span><span class="sxs-lookup"><span data-stu-id="1fc70-149">sip</span></span>|    <span data-ttu-id="1fc70-150">3600</span><span class="sxs-lookup"><span data-stu-id="1fc70-150">3600</span></span>|   <span data-ttu-id="1fc70-151">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="1fc70-151">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="1fc70-152">Inoltre, i record CNAME per meet o dialin (se presente) possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="1fc70-152">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="1fc70-153">Infine, tutti i record DNS per Skype for Business nella rete interna devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="1fc70-153">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="1fc70-154">In rari casi, la modifica del DNS dall'puntare in locale a Microsoft 365 per l'organizzazione può causare la federazione con altre organizzazioni a smettere di funzionare finché l'altra organizzazione non aggiorna la configurazione della federazione:</span><span class="sxs-lookup"><span data-stu-id="1fc70-154">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="1fc70-155">Tutte le organizzazioni federate che utilizzano il modello di federazione diretta precedente (noto anche come Server partner consentito) dovranno aggiornare le voci di dominio consentite per l'organizzazione per rimuovere il nome di dominio completo del proxy.</span><span class="sxs-lookup"><span data-stu-id="1fc70-155">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="1fc70-156">Questo modello di federazione legacy non è basato sui record DNS SRV, quindi una configurazione di questo tipo diventerà non aggiornata dopo che l'organizzazione si sposta nel cloud.</span><span class="sxs-lookup"><span data-stu-id="1fc70-156">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="1fc70-157">Qualsiasi organizzazione federata che non dispone di un provider di hosting abilitato per sipfed.online.lync. <span> com dovrà aggiornare la configurazione per abilitarla.</span><span class="sxs-lookup"><span data-stu-id="1fc70-157">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="1fc70-158">Questa situazione è possibile solo se l'organizzazione federata è puramente locale e non ha mai federato con un tenant ibrido o online.</span><span class="sxs-lookup"><span data-stu-id="1fc70-158">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="1fc70-159">In tal caso, la federazione con queste organizzazioni non funzionerà finché non abilita il provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="1fc70-159">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="1fc70-160">Se si sospetta che uno dei partner federati utilizzi la federazione diretta o che non sia federato con un'organizzazione online o ibrida, è consigliabile inviare loro una comunicazione in proposito mentre si prepara a completare la migrazione al cloud.</span><span class="sxs-lookup"><span data-stu-id="1fc70-160">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="1fc70-161">*Disabilitare lo spazio di indirizzi SIP condiviso nell'organizzazione di Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="1fc70-161">*Disable shared sip address space in Microsoft 365 organization.*</span></span> <span data-ttu-id="1fc70-162">Il comando seguente deve essere eseguito da una finestra di PowerShell di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="1fc70-162">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  <span data-ttu-id="1fc70-163">*Disabilitare la possibilità in locale di comunicare con Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="1fc70-163">*Disable the ability in on-premises to communicate with Microsoft 365.*</span></span> <span data-ttu-id="1fc70-164">Il comando seguente deve essere eseguito da una finestra di PowerShell locale:</span><span class="sxs-lookup"><span data-stu-id="1fc70-164">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="1fc70-165">Gestione degli attributi dopo lo spostamento degli utenti dall'ambiente locale al cloud</span><span class="sxs-lookup"><span data-stu-id="1fc70-165">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="1fc70-166">Per impostazione predefinita, tutti gli utenti precedentemente abilitati per Skype for Business Server e successivamente spostati nel cloud hanno ancora attributi msRTCSIP configurati in Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="1fc70-166">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="1fc70-167">Questi attributi, in particolare l'indirizzo sip (msRTCSIP-PrimaryUserAddress) e il numero di telefono potenzialmente (msRTCSIP-Line), continuano a essere sincronizzati in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1fc70-167">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="1fc70-168">Se sono necessarie modifiche a uno degli attributi msRTCSIP, queste modifiche devono essere apportate in Active Directory locale e quindi sincronizzate con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1fc70-168">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="1fc70-169">Tuttavia, una volta rimossa la distribuzione di Skype for Business Server, gli strumenti di Skype for Business Server non saranno disponibili per gestire questi attributi.</span><span class="sxs-lookup"><span data-stu-id="1fc70-169">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="1fc70-170">Sono disponibili due opzioni per gestire questa situazione:</span><span class="sxs-lookup"><span data-stu-id="1fc70-170">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="1fc70-171">Lasciare gli utenti abilitati per gli account del server Skype for Business così com'è e gestire gli attributi msRTCSIP con gli strumenti di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1fc70-171">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="1fc70-172">Questo garantisce la perdita del servizio per gli utenti migrati e consente di rimuovere facilmente la distribuzione di Skype for Business Server eliminando (ad esempio, la cancellazione) dei server, senza una rimozione completa.</span><span class="sxs-lookup"><span data-stu-id="1fc70-172">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="1fc70-173">Tuttavia, i nuovi utenti con licenza non avranno questi attributi popolati in Active Directory locale e dovranno essere gestiti online.</span><span class="sxs-lookup"><span data-stu-id="1fc70-173">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="1fc70-174">Cancellare tutti gli attributi msRTCSIP dagli utenti migrati in Active Directory locale e gestire questi attributi utilizzando gli strumenti online.</span><span class="sxs-lookup"><span data-stu-id="1fc70-174">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="1fc70-175">Questo metodo consente un approccio di gestione coerente per gli utenti esistenti e nuovi, tuttavia può potenzialmente causare una perdita temporanea del servizio durante il processo di rimozione delle autorizzazioni locale.</span><span class="sxs-lookup"><span data-stu-id="1fc70-175">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="1fc70-176">Metodo 1 - Gestire gli indirizzi SIP e i numeri di telefono per gli utenti in Active Directory</span><span class="sxs-lookup"><span data-stu-id="1fc70-176">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="1fc70-177">Gli amministratori possono gestire gli utenti che in precedenza erano stati spostati da Skype for Business Server locale al cloud, anche dopo la rimozione della distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="1fc70-177">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="1fc70-178">Se si desidera apportare modifiche all'indirizzo SIP di un utente o al numero di telefono di un utente (e l'indirizzo sip o il numero di telefono ha già un valore in Active Directory locale), è necessario eseguire questa operazione in Active Directory locale e consentire il flusso dei valori fino ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1fc70-178">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="1fc70-179">Questo non richiede Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="1fc70-179">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="1fc70-180">È invece possibile modificare questi attributi direttamente in Active Directory locale, utilizzando lo snap-in MMC Utenti e computer di Active Directory (come illustrato di seguito) o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1fc70-180">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="1fc70-181">Se si utilizza lo snap-in MMC, aprire la pagina delle proprietà dell'utente, fare clic sulla scheda Editor attributi e individuare gli attributi appropriati da modificare:</span><span class="sxs-lookup"><span data-stu-id="1fc70-181">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="1fc70-182">Per modificare l'indirizzo SIP di un utente, modificare la proprietà `msRTCSIP-PrimaryUserAddress` .</span><span class="sxs-lookup"><span data-stu-id="1fc70-182">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="1fc70-183">Si noti che, `ProxyAddresses` se l'attributo contiene un indirizzo sip, aggiornare anche tale valore come procedura consigliata.</span><span class="sxs-lookup"><span data-stu-id="1fc70-183">Note, if the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="1fc70-184">Anche se l'indirizzo sip in viene ignorato da O365 se viene popolato, può essere utilizzato `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` da altri componenti locali.</span><span class="sxs-lookup"><span data-stu-id="1fc70-184">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="1fc70-185">Per modificare il numero di telefono di un utente, modificare `msRTCSIP-Line` *se ha già un valore*.</span><span class="sxs-lookup"><span data-stu-id="1fc70-185">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Strumento Utenti e computer di Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="1fc70-187">Se l'utente in origine non aveva un valore per l'ambiente locale prima dello spostamento, è possibile modificare il numero di telefono utilizzando il parametro - nel `msRTCSIP-Line` `onpremLineUri` cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) nel modulo PowerShell di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="1fc70-187">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="1fc70-188">Questi passaggi non sono necessari per i nuovi utenti creati dopo la disabilitazione ibrida e possono essere gestiti direttamente nel cloud.</span><span class="sxs-lookup"><span data-stu-id="1fc70-188">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="1fc70-189">Se si ha familiarità con l'uso della combinazione di questi metodi e con l'abbandono degli attributi msRTCSIP in locale in Active Directory, è sufficiente ri-immagine dei server Skype for Business locali.</span><span class="sxs-lookup"><span data-stu-id="1fc70-189">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="1fc70-190">Tuttavia, se preferisci cancellare tutti gli attributi msRTCSIP ed eseguire una disinstallazione tradizionale di Skype for Business Server, usa il metodo 2.</span><span class="sxs-lookup"><span data-stu-id="1fc70-190">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="1fc70-191">Metodo 2 - Cancellare gli attributi di Skype for Business per tutti gli utenti locali in Active Directory</span><span class="sxs-lookup"><span data-stu-id="1fc70-191">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="1fc70-192">Questa opzione richiede ulteriori sforzi e una pianificazione adeguata perché gli utenti che in precedenza erano stati spostati da Skype for Business Server locale al cloud devono essere nuovamente provisioning.</span><span class="sxs-lookup"><span data-stu-id="1fc70-192">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="1fc70-193">Questi utenti possono essere categorizzati in due categorie diverse: gli utenti senza Sistema telefonico e gli utenti con Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="1fc70-193">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="1fc70-194">Gli utenti con sistema telefonico sperimenteranno una perdita temporanea del servizio telefonico nell'ambito della transizione del numero di telefono dalla gestione in Active Directory locale al cloud.</span><span class="sxs-lookup"><span data-stu-id="1fc70-194">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="1fc70-195">**È consigliabile eseguire un progetto pilota che coinvolge un numero limitato di utenti con Sistema telefonico prima di avviare le operazioni in blocco degli utenti.**</span><span class="sxs-lookup"><span data-stu-id="1fc70-195">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="1fc70-196">Per distribuzioni di grandi dimensioni gli utenti possono essere elaborati in gruppi più piccoli in finestre di tempo diverse.</span><span class="sxs-lookup"><span data-stu-id="1fc70-196">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="1fc70-197">Questo processo è più semplice per gli utenti che hanno un indirizzo SIP e UserPrincipalName corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="1fc70-197">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="1fc70-198">Per le organizzazioni con utenti con valori non corrispondenti tra questi due attributi, è necessario fare attenzione come indicato di seguito per una transizione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="1fc70-198">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="1fc70-199">Se sono stati configurati endpoint di applicazioni ibride locali per operatori automatici o code di chiamata, assicurarsi di spostare questi endpoint in Microsoft 365 prima di rimuovere Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1fc70-199">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="1fc70-200">Verificare che il seguente cmdlet di PowerShell di Skype for Business locale restituisca un risultato vuoto.</span><span class="sxs-lookup"><span data-stu-id="1fc70-200">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="1fc70-201">Un risultato vuoto indica che nessun utente è ospitato in locale e che è stato spostato in Microsoft 365 o è stato disabilitato:</span><span class="sxs-lookup"><span data-stu-id="1fc70-201">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="1fc70-202">Registrare il numero di telefono corrente degli utenti (LineUri), UserPrincipalName e le informazioni correlate eseguendo il cmdlet di PowerShell di Skype for Business Server locale seguente per esportare i dati degli utenti:</span><span class="sxs-lookup"><span data-stu-id="1fc70-202">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="1fc70-203">Prima di procedere con SfbUserSettings.csv file e verificare che tutti i dati utente siano stati esportati correttamente.</span><span class="sxs-lookup"><span data-stu-id="1fc70-203">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="1fc70-204">È consigliabile conservare una copia di questo file.</span><span class="sxs-lookup"><span data-stu-id="1fc70-204">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="1fc70-205">Non utilizzare questo file nei passaggi seguenti per l'elaborazione degli utenti.</span><span class="sxs-lookup"><span data-stu-id="1fc70-205">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="1fc70-206">Creare un file con un gruppo di utenti da utilizzare nei passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="1fc70-206">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="1fc70-207">Una volta completato correttamente il primo gruppo di utenti, procedere con il gruppo di utenti successivo.</span><span class="sxs-lookup"><span data-stu-id="1fc70-207">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="1fc70-208">Nell'esempio seguente i gruppi di utenti vengono selezionati in ordine alfabetico, ma è possibile filtrare gli utenti in base ai criteri che corrispondono al modo in cui si desidera elaborare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1fc70-208">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="1fc70-209">Prima di procedere con SfbUsers.csv file e verificare che i dati utente siano stati esportati correttamente.</span><span class="sxs-lookup"><span data-stu-id="1fc70-209">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="1fc70-210">In un passaggio successivo saranno necessari LineUri (numero di telefono), UserPrincipalName, SamAccountName e SipAddress da questo file.</span><span class="sxs-lookup"><span data-stu-id="1fc70-210">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="1fc70-211">Eliminare le informazioni sugli attributi relative a Skype for Business Server da Active Directory per il set di utenti pronti per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1fc70-211">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="1fc70-212">Esistono 2 passaggi per questo processo, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1fc70-212">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="1fc70-213">Dopo il successivo ciclo di sincronizzazione AAD dopo l'esecuzione di questo passaggio, gli utenti con Sistema telefonico che in precedenza erano stati spostati da un Skype for Business Server locale al cloud perderanno la possibilità di effettuare e ricevere chiamate fino al completamento e alla conferma del passaggio 8 nel passaggio 9.</span><span class="sxs-lookup"><span data-stu-id="1fc70-213">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="1fc70-214">Inoltre, assicurati di aver salvato i numeri di telefono e le informazioni correlate dell'utente secondo il passaggio 2, poiché queste informazioni sono necessarie per tale passaggio.</span><span class="sxs-lookup"><span data-stu-id="1fc70-214">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="1fc70-215">Successivamente, per lo stesso set di utenti, cancellare il valore di msRTCSIP-DeploymentLocator usando PowerShell di Active Directory locale:</span><span class="sxs-lookup"><span data-stu-id="1fc70-215">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="1fc70-216">Eseguire il seguente cmdlet di PowerShell di Skype for Business locale per aggiungere nuovamente il valore dell'indirizzo sip ai proxyAddresses di Active Directory locali.</span><span class="sxs-lookup"><span data-stu-id="1fc70-216">Run the following on-premise Skype for Business PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="1fc70-217">In questo modo si evitano problemi di interoperabilità che si basano su questo attributo.</span><span class="sxs-lookup"><span data-stu-id="1fc70-217">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="1fc70-218">Eseguire Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="1fc70-218">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="1fc70-219">Attendere il completamento del provisioning degli utenti.</span><span class="sxs-lookup"><span data-stu-id="1fc70-219">Wait for user provisioning to complete.</span></span> <span data-ttu-id="1fc70-220">È possibile monitorare lo stato di avanzamento del provisioning degli utenti eseguendo il seguente comando di PowerShell di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="1fc70-220">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="1fc70-221">Il seguente comando di PowerShell di Skype for Business online restituisce un risultato vuoto non appena il processo viene completato.</span><span class="sxs-lookup"><span data-stu-id="1fc70-221">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="1fc70-222">Eseguire il comando di PowerShell di Skype for Business online seguente per assegnare numeri di telefono e abilitare gli utenti per Sistema telefonico:</span><span class="sxs-lookup"><span data-stu-id="1fc70-222">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="1fc70-223">Se hai ancora endpoint Skype for Business (client Skype o telefoni di terze parti), devi anche impostare -HostedVoiceMail su $true.</span><span class="sxs-lookup"><span data-stu-id="1fc70-223">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="1fc70-224">Se l'organizzazione usa solo endpoint di Teams per gli utenti abilitati alla funzionalità vocale, questa impostazione non è applicabile agli utenti.</span><span class="sxs-lookup"><span data-stu-id="1fc70-224">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="1fc70-225">Verificare che il provisioning degli utenti con funzionalità sistema telefonico sia stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="1fc70-225">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="1fc70-226">Il seguente comando di PowerShell di Skype for Business online restituisce un risultato vuoto non appena il processo viene completato.</span><span class="sxs-lookup"><span data-stu-id="1fc70-226">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="1fc70-227">Ripetere i passaggi da 3 a 9 finché non vengono elaborati tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1fc70-227">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="1fc70-228">Verificare che tutti gli utenti siano stati elaborati correttamente eseguendo i due comandi di PowerShell seguenti.</span><span class="sxs-lookup"><span data-stu-id="1fc70-228">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="1fc70-229">Comando di PowerShell locale di Skype for Business Server locale:</span><span class="sxs-lookup"><span data-stu-id="1fc70-229">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="1fc70-230">Comando di PowerShell di Skype for Business online:</span><span class="sxs-lookup"><span data-stu-id="1fc70-230">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="1fc70-231">Dopo aver completato tutti i passaggi nel metodo 2, vedere Spostare gli endpoint dell'applicazione ibrida da locale a [online](decommission-move-on-prem-endpoints.md) e [Rimuovere Skype for Business Server](decommission-remove-on-prem.md) locale per ulteriori passaggi per rimuovere la distribuzione locale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1fc70-231">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="1fc70-232">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fc70-232">See also</span></span>

- [<span data-ttu-id="1fc70-233">Consolidamento cloud per Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1fc70-233">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="1fc70-234">Rimuovi le autorizzazioni dell'ambiente locale Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1fc70-234">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

