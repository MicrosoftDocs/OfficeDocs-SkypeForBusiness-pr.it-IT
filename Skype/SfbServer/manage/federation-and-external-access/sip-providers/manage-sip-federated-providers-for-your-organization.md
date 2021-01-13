---
title: Gestire i provider federati SIP per l'organizzazione
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Informazioni su come configurare il supporto per gli utenti di provider federati SIP.
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823566"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="649ba-103">Gestire i provider federati SIP per l'organizzazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="649ba-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="649ba-104">Per configurare il supporto per gli utenti di provider federati SIP, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="649ba-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="649ba-105">Configurare uno o più criteri di accesso utente esterno per supportare la comunicazione con i contatti del provider federato SIP</span><span class="sxs-lookup"><span data-stu-id="649ba-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="649ba-106">Specificare quali provider ospitati si desidera supportare</span><span class="sxs-lookup"><span data-stu-id="649ba-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="649ba-107">Specificare i provider di messaggistica istantanea pubblica che si desidera supportare</span><span class="sxs-lookup"><span data-stu-id="649ba-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="649ba-108">Creare o modificare provider federati SIP pubblici in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="649ba-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="649ba-109">La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider pubblici.</span><span class="sxs-lookup"><span data-stu-id="649ba-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="649ba-110">Skype for Business Server dispone di configurazioni di provider pubblico per la messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="649ba-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="649ba-111">Ogni provider pubblico è configurato con il nome di dominio completo del server perimetrale del provider e il livello di verifica predefinito **consente agli utenti di comunicare solo con le persone presenti nell'elenco dei contatti che utilizzano questo provider**.</span><span class="sxs-lookup"><span data-stu-id="649ba-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="649ba-112">Come impostazione predefinita, nessuno dei provider pubblici è abilitato.</span><span class="sxs-lookup"><span data-stu-id="649ba-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="649ba-113">Prima di abilitare i provider pubblici, è necessario completare il contratto di licenza e il provisioning.</span><span class="sxs-lookup"><span data-stu-id="649ba-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="649ba-114">È possibile abilitare il provider prima di completare il lavoro di gestione delle licenze e del provisioning.</span><span class="sxs-lookup"><span data-stu-id="649ba-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="649ba-115">Gli utenti non saranno in grado di comunicare con i contatti su tali provider fino al completamento del lavoro prerequisito.</span><span class="sxs-lookup"><span data-stu-id="649ba-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="649ba-116">Per informazioni dettagliate sulle licenze e il provisioning dei provider pubblici, vedere [Configure policies to Control public User accesso](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="649ba-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="649ba-117">Utilizzare la procedura seguente per creare o modificare provider pubblici.</span><span class="sxs-lookup"><span data-stu-id="649ba-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="649ba-118">Per creare o modificare provider pubblici:</span><span class="sxs-lookup"><span data-stu-id="649ba-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="649ba-119">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="649ba-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="649ba-120">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="649ba-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="649ba-121">Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Provider federati SIP**.</span><span class="sxs-lookup"><span data-stu-id="649ba-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="649ba-122">Se è necessario creare un nuovo provider pubblico, fare clic su **Nuovo** e quindi su **Provider pubblico**.</span><span class="sxs-lookup"><span data-stu-id="649ba-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="649ba-123">Se è necessario modificare una voce dell'elenco di provider pubblici, selezionare un provider pubblico, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="649ba-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="649ba-124">Nella pagina **Modifica Provider federato SIP** è possibile digitare o modificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="649ba-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="649ba-125">**Abilita comunicazioni con questo provider**   Se si seleziona questa impostazione, si abilita la messaggistica istantanea con gli utenti del provider specificato.</span><span class="sxs-lookup"><span data-stu-id="649ba-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="649ba-126">**Nome provider**   Si tratta di una proprietà obbligatoria. Digitare il nome del provider come verrà indicato nell'elenco di provider federati SIP.</span><span class="sxs-lookup"><span data-stu-id="649ba-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="649ba-127">**Servizio Access Edge (FQDN):**   Una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider che si sta configurando.</span><span class="sxs-lookup"><span data-stu-id="649ba-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="649ba-128">Queste informazioni vengono fornite come elementi predefiniti e devono essere modificate solo se il provider pubblico apporta una modifica al nome di dominio completo del servizio Access Edge nel provider pubblico.</span><span class="sxs-lookup"><span data-stu-id="649ba-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="649ba-129">**Livello di verifica predefinito:**    L'impostazione predefinita, **Consenti agli utenti di comunicare solo con le persone incluse nell'elenco Contatti che usano questo provider** consente di comunicare solo con i contatti accettati e presenti nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="649ba-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="649ba-p104">Se si seleziona **Consenti agli utenti di comunicare con chiunque usi questo provider** rimuove la limitazione di dover ricevere e accettare l'invito di un contatto. Questa impostazione non impone limiti sugli utenti della rete del provider pubblico da cui si può essere contattati.</span><span class="sxs-lookup"><span data-stu-id="649ba-p104">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="649ba-132">Al termine della configurazione delle impostazioni, fare clic su **Commit** per salvare o su **Annulla** per annullare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="649ba-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="649ba-133">Creare o modificare provider federati SIP ospitati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="649ba-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="649ba-134">La connettività di messaggistica istantanea (IM) del provider hosted consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider ospitati.</span><span class="sxs-lookup"><span data-stu-id="649ba-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="649ba-135">Ogni provider ospitato è configurato con il nome di dominio completo del server perimetrale del provider e il livello di verifica predefinito **Consenti agli utenti di comunicare solo con le persone incluse nell'elenco Contatti che usano questo provider**.</span><span class="sxs-lookup"><span data-stu-id="649ba-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="649ba-136">Utilizzare la procedura seguente per creare o modificare i provider ospitati.</span><span class="sxs-lookup"><span data-stu-id="649ba-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="649ba-137">Per creare o modificare provider gestiti</span><span class="sxs-lookup"><span data-stu-id="649ba-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="649ba-138">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="649ba-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="649ba-139">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="649ba-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="649ba-140">Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Provider federati SIP**.</span><span class="sxs-lookup"><span data-stu-id="649ba-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="649ba-141">Se è necessario creare un nuovo provider ospitato fare clic su **Nuovo** e quindi su **Provider ospitato**.</span><span class="sxs-lookup"><span data-stu-id="649ba-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="649ba-142">Se è necessario modificare una voce nell'elenco di provider ospitati, selezionare un provider ospitato, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="649ba-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="649ba-143">Nella pagina **Modifica provider federato SIP** è possibile immettere o modificare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="649ba-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="649ba-144">**Abilita comunicazioni con questo provider**   Questa impostazione abilita le comunicazioni con gli utenti del provider.</span><span class="sxs-lookup"><span data-stu-id="649ba-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="649ba-145">**Nome provider**   Si tratta di una proprietà obbligatoria. Digitare il nome del provider come verrà indicato nell'elenco di provider federati SIP.</span><span class="sxs-lookup"><span data-stu-id="649ba-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="649ba-146">**Servizio Access Edge (FQDN):**   Una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider ospitato che si sta configurando.</span><span class="sxs-lookup"><span data-stu-id="649ba-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="649ba-147">Queste informazioni devono essere fornite dal provider ospitato e devono essere modificate solo se il provider ospitato apporta una modifica al nome di dominio completo del servizio Access Edge nel provider ospitato.</span><span class="sxs-lookup"><span data-stu-id="649ba-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="649ba-148">**Livello di verifica predefinito**   L'impostazione predefinita, ovvero **Consenti agli utenti di comunicare solo con le persone incluse nell'elenco Contatti che usano questo provider** limita le comunicazioni ai contatti che sono stati accettati e inclusi nell'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="649ba-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="649ba-p106">Se si seleziona **Consenti agli utenti di comunicare con chiunque usi questo provider**, viene rimossa la limitazione che prevede che sia stato ricevuto e accettato un invito di contatto. Questa impostazione non limita gli utenti dai quali è possibile essere contattati dalla rete del provider ospitato.</span><span class="sxs-lookup"><span data-stu-id="649ba-p106">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="649ba-151">Terminata la configurazione delle impostazioni, fare clic su **Commit** per salvare oppure su **Annulla** per annullare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="649ba-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="649ba-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="649ba-152">See Also</span></span>


[<span data-ttu-id="649ba-153">Configurazione di criteri per il controllo dell'accesso degli utenti pubblici</span><span class="sxs-lookup"><span data-stu-id="649ba-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="649ba-154">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="649ba-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

