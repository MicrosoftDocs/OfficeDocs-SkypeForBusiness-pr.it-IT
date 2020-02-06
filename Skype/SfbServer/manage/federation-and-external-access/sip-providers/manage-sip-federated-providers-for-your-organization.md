---
title: Gestire i provider federati SIP per l'organizzazione
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Informazioni su come configurare il supporto per gli utenti di provider federati SIP.
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818367"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="6ee6f-103">Gestire i provider federati SIP per l'organizzazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6ee6f-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="6ee6f-104">Per configurare il supporto per gli utenti di provider federati SIP, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ee6f-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="6ee6f-105">Configurare uno o più criteri di accesso degli utenti esterni per supportare la comunicazione con i contatti del provider federativo SIP</span><span class="sxs-lookup"><span data-stu-id="6ee6f-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="6ee6f-106">Specificare i provider ospitati che si desidera supportare</span><span class="sxs-lookup"><span data-stu-id="6ee6f-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="6ee6f-107">Specificare i provider di messaggistica istantanea pubblici che si desidera supportare</span><span class="sxs-lookup"><span data-stu-id="6ee6f-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="6ee6f-108">Creare o modificare provider federati SIP pubblici in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6ee6f-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="6ee6f-109">La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di usare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider pubblici.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="6ee6f-110">Skype for Business Server include configurazioni di provider pubbliche per la messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="6ee6f-111">Ogni provider pubblico è configurato con il nome di dominio completo di Edge Server del provider e il livello di verifica predefinito **consente agli utenti di comunicare solo con persone presenti nell'elenco contatti che usano questo provider**.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="6ee6f-112">Come impostazione predefinita, nessuno dei provider pubblici è abilitato.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="6ee6f-113">Prima di abilitare i provider pubblici, è consigliabile completare il contratto di licenza e il provisioning.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="6ee6f-114">È possibile abilitare il provider prima di completare il lavoro di licenza e provisioning.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="6ee6f-115">Gli utenti non saranno in grado di comunicare con i contatti di tali provider finché non viene completato il lavoro pre-requisito.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="6ee6f-116">Per informazioni dettagliate sulle licenze e sul provisioning dei provider pubblici, vedere [configurare i criteri per controllare l'accesso degli utenti pubblici](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="6ee6f-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="6ee6f-117">Usare la procedura seguente per creare o modificare provider pubblici.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="6ee6f-118">Per creare o modificare provider pubblici</span><span class="sxs-lookup"><span data-stu-id="6ee6f-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="6ee6f-119">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6ee6f-120">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6ee6f-121">Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**, quindi fare clic su **provider federati SIP**.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="6ee6f-122">Se è necessario creare un nuovo provider pubblico, fare clic su **nuovo** e quindi su **provider pubblico**.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="6ee6f-123">Se è necessario modificare una voce dall'elenco di provider pubblici, selezionare un provider pubblico, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="6ee6f-124">Nella pagina **Modifica provider FEDERATO SIP** è possibile digitare o modificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ee6f-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="6ee6f-125">**Abilitare le comunicazioni con questo provider**   la selezione di questa impostazione consente agli utenti di questo provider di usare la messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="6ee6f-126">**Nome provider:**   una proprietà obbligatoria, digitare il nome del provider che verrà riflesso nell'elenco dei provider federati SIP.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="6ee6f-127">**Access Edge service (FQDN):**   una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider che si sta configurando.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="6ee6f-128">Queste informazioni vengono fornite come elemento predefinito e devono essere modificate solo se il provider pubblico apporta una modifica al nome di dominio completo del servizio Access Edge presso il provider pubblico.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="6ee6f-129">**Livello di verifica predefinito:**   l'impostazione predefinita **consente agli utenti di comunicare con persone nell'elenco contatti che usano questo provider** limiterà la comunicazione ai contatti accettati e inclusi nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="6ee6f-130">Selezionando **Consenti agli utenti di comunicare con tutti i membri che usano questo provider** , viene eliminata la restrizione che deve essere stata ricevuta e accettata da un contatto.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="6ee6f-131">Questa impostazione non limita chi può contattarti dalla rete del provider pubblico.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="6ee6f-132">Dopo aver configurato le impostazioni, fare clic su **conferma** per salvare o su **Annulla per annullare** le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="6ee6f-133">Creare o modificare provider federati SIP ospitati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6ee6f-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="6ee6f-134">La connettività di messaggistica istantanea del provider ospitata consente agli utenti dell'organizzazione di usare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider ospitati.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="6ee6f-135">Ogni provider ospitato è configurato con il nome di dominio completo del server perimetrale del provider e il livello di verifica predefinito **consente agli utenti di comunicare solo con persone presenti nell'elenco contatti che usano questo provider**.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="6ee6f-136">Usare la procedura seguente per creare o modificare i provider ospitati.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="6ee6f-137">Per creare o modificare i provider ospitati</span><span class="sxs-lookup"><span data-stu-id="6ee6f-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="6ee6f-138">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6ee6f-139">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6ee6f-140">Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**, quindi fare clic su **provider federati SIP**.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="6ee6f-141">Se è necessario creare un nuovo provider ospitato, fare clic su **nuovo** e quindi su **provider ospitati**.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="6ee6f-142">Se è necessario modificare una voce dall'elenco di provider ospitati, selezionare un provider ospitata, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="6ee6f-143">Nella pagina **Modifica provider FEDERATO SIP** è possibile digitare o modificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ee6f-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="6ee6f-144">**Abilitare le comunicazioni con questo provider**   Selezionare questa impostazione consente le comunicazioni con gli utenti del provider.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="6ee6f-145">**Nome provider:**   una proprietà obbligatoria, digitare il nome del provider che verrà riflesso nell'elenco dei provider federati SIP.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="6ee6f-146">**Access Edge service (FQDN):**   una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider ospitato che si sta configurando.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="6ee6f-147">Queste informazioni devono essere fornite dal provider ospitato e devono essere modificate solo se il provider ospitato apporta una modifica all'FQDN del servizio Access Edge presso il provider ospitata.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="6ee6f-148">**Livello di verifica predefinito:**   l'impostazione predefinita **consente agli utenti di comunicare con persone nell'elenco contatti che usano questo provider** limiterà la comunicazione ai contatti accettati e inclusi nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="6ee6f-149">Selezionando **Consenti agli utenti di comunicare con tutti i membri che usano questo provider** , viene eliminata la restrizione che deve essere stata ricevuta e accettata da un contatto.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="6ee6f-150">Questa impostazione non limita chi può contattarti dalla rete del provider ospitata.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="6ee6f-151">Dopo aver configurato le impostazioni, fare clic su **conferma** per salvare o su **Annulla per annullare** le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6ee6f-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="6ee6f-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ee6f-152">See Also</span></span>


[<span data-ttu-id="6ee6f-153">Configurare i criteri per controllare l'accesso degli utenti pubblici</span><span class="sxs-lookup"><span data-stu-id="6ee6f-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="6ee6f-154">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="6ee6f-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

