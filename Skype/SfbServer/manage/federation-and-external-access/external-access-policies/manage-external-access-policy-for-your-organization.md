---
title: Gestire i criteri di accesso esterno per l'organizzazione
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
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
description: Dopo avere distribuito uno o più server Edge Server, è necessario abilitare i tipi di accesso esterno da supportare per l'organizzazione.
ms.openlocfilehash: 71797e865860107d23095659461c1b02e6d47cd7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817256"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="74b99-103">Gestire i criteri di accesso esterno per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="74b99-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="74b99-104">Dopo avere distribuito uno o più server Edge Server, è necessario abilitare i tipi di accesso esterno da supportare per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="74b99-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="74b99-p101">Per impostazione predefinita, non vi sono criteri configurati per supportare l'accesso utente esterno, inclusi l'accesso utente remoto e federato, anche se il supporto dell'accesso utente esterno è già stato abilitato per l'organizzazione. Per controllare l'uso dell'accesso utente esterno, è necessario configurare uno o più criteri, specificando il tipo di accesso utente esterno supportato per ogni criterio. Per la creazione e la configurazione sono disponibili gli ambiti di criteri seguenti. Per impostazione predefinita, i criteri globali possono essere creati ma non possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="74b99-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="74b99-109">**Criteri globali**   Il criterio globale viene creato quando si distribuiscono i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="74b99-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="74b99-110">Per impostazione predefinita, nei criteri globali non vengono abilitate opzioni di accesso per gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="74b99-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="74b99-111">Per supportare l'accesso degli utenti esterni a livello globale, è possibile configurare i criteri globali in modo da supportare uno o più tipi di opzioni di accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="74b99-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="74b99-112">I criteri globali si applicano a tutti gli utenti dell'organizzazione, ma i criteri sito e i criteri utente sostituiscono i criteri globali.</span><span class="sxs-lookup"><span data-stu-id="74b99-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="74b99-113">Se si eliminano i criteri globali, questi non vengono rimossi,</span><span class="sxs-lookup"><span data-stu-id="74b99-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="74b99-114">ma ne vengono ripristinate le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="74b99-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="74b99-115">**Criteri sito**   È possibile creare e configurare uno o più criteri sito per limitare il supporto per l'accesso degli utenti esterni a siti specifici.</span><span class="sxs-lookup"><span data-stu-id="74b99-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="74b99-116">La configurazione nel criterio sito ha la priorità sul criterio globale, ma solo per il sito specifico a cui si applica il criterio sito.</span><span class="sxs-lookup"><span data-stu-id="74b99-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="74b99-117">Se ad esempio si abilita l'accesso degli utenti remoti nel criterio globale, è possibile specificare un criterio sito che disabilita l'accesso degli utenti remoti per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="74b99-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="74b99-118">Per impostazione predefinita, un criterio sito viene applicato a tutti gli utenti del sito, ma è possibile assegnare un criterio utente a un utente per ignorare l'impostazione del criterio sito.</span><span class="sxs-lookup"><span data-stu-id="74b99-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="74b99-119">**Criteri utente**   È possibile creare e configurare uno o più criteri utente per limitare il supporto per l'accesso degli utenti remoti a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="74b99-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="74b99-120">La configurazione nel criterio utente ha la priorità sui criteri globale e sito, ma solo per gli utenti specifici a cui viene assegnato il criterio utente.</span><span class="sxs-lookup"><span data-stu-id="74b99-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="74b99-121">Se ad esempio si abilita l'accesso degli utenti remoti nei criteri globale e sito, è possibile specificare un criterio utente che disabilita l'accesso degli utenti remoti e quindi assegnare tale criterio utente a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="74b99-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="74b99-122">Se si crea un criterio utente, è necessario applicarlo a uno o più utenti per renderlo effettivo.</span><span class="sxs-lookup"><span data-stu-id="74b99-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="74b99-123">Le impostazioni criteri applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="74b99-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="74b99-124">La precedenza dei criteri di Skype for Business Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza).</span><span class="sxs-lookup"><span data-stu-id="74b99-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="74b99-125">Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="74b99-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="74b99-126">Queste opzioni includono i tipi di accesso esterno seguenti:</span><span class="sxs-lookup"><span data-stu-id="74b99-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="74b99-127">**Abilitare le comunicazioni con utenti federati**   Abilitare questa opzione se si desidera supportare l'accesso degli utenti ai domini partner federati.</span><span class="sxs-lookup"><span data-stu-id="74b99-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="74b99-128">Questa impostazione consente agli utenti di comunicare con altri domini federati SIP, nonché con provider ospitati come Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="74b99-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365 or Office 365.</span></span> 


  - <span data-ttu-id="74b99-129">**Abilitare le comunicazioni con utenti remoti**   Abilitare questa opzione se si desidera consentire agli utenti dell'organizzazione esterni al firewall, ad esempio telelavoratori e utenti in viaggio, di connettersi a Skype for Business Server tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="74b99-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="74b99-130">**Abilitare le comunicazioni con gli utenti pubblici**   Abilitare questa opzione se si desidera che gli utenti interni siano in grado di comunicare con i contatti del provider di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="74b99-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="74b99-131">Oltre ad abilitare il supporto dell'accesso a utenti esterni, è inoltre necessario configurare i criteri per controllare l'uso dell'accesso agli utenti esterni nell'organizzazione prima che sia disponibile qualsiasi tipo di accesso esterno per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="74b99-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="74b99-132">Per informazioni dettagliate sulla creazione, la configurazione e l'applicazione di criteri per l'accesso agli utenti esterni, vedere [Abilitare o disabilitare l'accesso utente remoto](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="74b99-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="74b99-133">**Per visualizzare i criteri di accesso esterno usando i cmdlet di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="74b99-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="74b99-134">È possibile visualizzare i criteri di accesso esterno con Skype for Business Server Management Shell e il **cmdlet Get-CsExternalAccessPolicy**.</span><span class="sxs-lookup"><span data-stu-id="74b99-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="74b99-135">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74b99-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="74b99-136">Per visualizzare informazioni su tutti i criteri di accesso esterno, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="74b99-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="74b99-137">Il comando restituisce informazioni simili a quelle riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="74b99-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
