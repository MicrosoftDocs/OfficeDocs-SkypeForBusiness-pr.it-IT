---
title: Prerequisiti di sicurezza e configurazione per VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Riepilogo: informazioni sui prerequisiti di sicurezza e configurazione per VoIP aziendale in Skype for Business Server.'
ms.openlocfilehash: 77efbf231f83c6d3c31254c9ab742de7e2b226e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830846"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="ce488-103">Prerequisiti di sicurezza e configurazione per VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce488-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="ce488-104">**Riepilogo:** Informazioni sui prerequisiti di sicurezza e configurazione per VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce488-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="ce488-105">Prima di distribuire VoIP aziendale, verificare che l'infrastruttura soddisfi i prerequisiti hardware di sicurezza, configurazione utente e specifici dello scenario seguenti.</span><span class="sxs-lookup"><span data-stu-id="ce488-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="ce488-106">Diritti amministrativi e infrastruttura dei certificati</span><span class="sxs-lookup"><span data-stu-id="ce488-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="ce488-107">Prima della distribuzione, controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ce488-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="ce488-108">Gli amministratori che distribuiscono VoIP aziendale devono essere membri del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ce488-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="ce488-109">Gli amministratori che eseguono le attività di configurazione devono disporre di diritti appropriati:</span><span class="sxs-lookup"><span data-stu-id="ce488-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="ce488-110">**CsVoiceAdministrator:** questo ruolo di amministratore consente di eseguire attività di configurazione vocale, di gestire le applicazioni vocali e di assegnare criteri vocali agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="ce488-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="ce488-p101">**CsUserAdministrator:** questo ruolo di amministratore consente di gestire le proprietà degli utenti, ad esempio l'abilitazione di VoIP aziendale per un utente. Consente inoltre di assegnare criteri per utente, ad eccezione del criterio di archiviazione, di spostare gli utenti e di gestire i telefoni di area comune e i dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="ce488-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="ce488-113">**CsAdministrator:** questo ruolo di amministratore consente di eseguire tutte le attività di CsVoiceAdministrator e CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ce488-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="ce488-114">La distribuzione e la configurazione dell'infrastruttura MKI (Managed Key Infrastructure) vengono eseguite utilizzando un'infrastruttura di autorità di certificazione (CA) Microsoft o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="ce488-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ce488-115">Per informazioni dettagliate sui requisiti dei certificati in Skype for Business Server, vedere Requisiti ambientali per [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o Server per Skype for Business Server [2019.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="ce488-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="ce488-116">Configurazione utente</span><span class="sxs-lookup"><span data-stu-id="ce488-116">User configuration</span></span>

<span data-ttu-id="ce488-117">Se il Mediation Server è stato collocato con ogni pool Front End o server Standard Edition durante la distribuzione front-end, le impostazioni utente necessarie per VoIP aziendale sono state configurate automaticamente durante l'installazione dei file per tali ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="ce488-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="ce488-118">Se si sta procedendo ora alla distribuzione del carico di lavoro di VoIP aziendale, prima di iniziare il processo di distribuzione designare un numero di telefono primario per ogni utente che si intende abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="ce488-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="ce488-119">In qualità di amministratori, è necessario verificare che questo numero sia univoco.</span><span class="sxs-lookup"><span data-stu-id="ce488-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="ce488-120">Prima dell'implementazione, tutti i numeri di telefono principali devono essere normalizzati (formattati correttamente) e copiati nella proprietà **URI** linea di ogni utente tramite il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce488-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ce488-121">Per esempi di numeri di telefono principali necessari per VoIP aziendale distribuzione, vedere [Regole di normalizzazione di esempio.](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules)</span><span class="sxs-lookup"><span data-stu-id="ce488-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="ce488-122">Passaggi successivi: Installare i file o configurare la connettività PSTN</span><span class="sxs-lookup"><span data-stu-id="ce488-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="ce488-123">Dopo aver verificato i prerequisiti software e ambientali per VoIP aziendale è possibile:</span><span class="sxs-lookup"><span data-stu-id="ce488-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="ce488-124">Installare il Mediation Server, come descritto in Distribuire un Mediation Server in Generatore di topologie [in Skype for Business Server,](deploy-a-mediation-server.md)ma solo se si desidera distribuire un Mediation Server autonomo o un pool perché i Mediation Server vengono installati come parte del processo di distribuzione del pool Front End o del server Standard Edition quando sono collocati.</span><span class="sxs-lookup"><span data-stu-id="ce488-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="ce488-125">Oppure, iniziare a configurare le impostazioni per instradare le chiamate VoIP aziendale utenti, come descritto [in Configurare i trunk in Skype for Business Server.](configure-trunks.md)</span><span class="sxs-lookup"><span data-stu-id="ce488-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

