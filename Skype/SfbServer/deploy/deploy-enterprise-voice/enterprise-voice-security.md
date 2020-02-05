---
title: Prerequisiti per la sicurezza e la configurazione di VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Riepilogo: informazioni sui prerequisiti per la sicurezza e la configurazione di VoIP aziendale in Skype for Business Server.'
ms.openlocfilehash: 314c25429dbf346a5f62705afa4f19a5b518452a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767239"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="494f5-103">Prerequisiti per la sicurezza e la configurazione di VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="494f5-103">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="494f5-104">**Riepilogo:** Informazioni sui prerequisiti per la sicurezza e la configurazione di VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="494f5-104">**Summary:** Learn about the security and configuration prerequisites for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="494f5-105">Prima di distribuire Enterprise Voice, verificare che l'infrastruttura soddisfi i requisiti di sicurezza, configurazione utente e prerequisiti hardware specifici dello scenario.</span><span class="sxs-lookup"><span data-stu-id="494f5-105">Before deploying Enterprise Voice, verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span> 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="494f5-106">Diritti amministrativi e infrastruttura dei certificati</span><span class="sxs-lookup"><span data-stu-id="494f5-106">Administrative rights and certificate infrastructure</span></span>

<span data-ttu-id="494f5-107">Prima della distribuzione, controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="494f5-107">Before deploying, check the following:</span></span>
  
- <span data-ttu-id="494f5-108">Gli amministratori che distribuiscono VoIP aziendale devono essere membri del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="494f5-108">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>
    
- <span data-ttu-id="494f5-109">Gli amministratori che eseguono le attività di configurazione devono avere diritti adeguati:</span><span class="sxs-lookup"><span data-stu-id="494f5-109">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
  - <span data-ttu-id="494f5-110">**CsVoiceAdministrator:** Questo ruolo di amministratore può eseguire attività di configurazione vocale, gestire le applicazioni vocali e assegnare criteri vocali agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="494f5-110">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
  - <span data-ttu-id="494f5-111">**CsUserAdministrator:** Questo ruolo di amministratore può gestire le proprietà degli utenti, ad esempio l'abilitazione di VoIP aziendale per un utente.</span><span class="sxs-lookup"><span data-stu-id="494f5-111">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user.</span></span> <span data-ttu-id="494f5-112">Questo ruolo di amministratore può anche assegnare criteri per utente, ad eccezione dei criteri di archiviazione. trasferire utenti; e Gestisci telefoni per area comune e dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="494f5-112">This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
  - <span data-ttu-id="494f5-113">**CsAdministrator:** Questo ruolo di amministratore può eseguire tutte le attività di CsVoiceAdministrator e CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="494f5-113">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
- <span data-ttu-id="494f5-114">L'infrastruttura MKI (Managed Key Infrastructure) viene distribuita e configurata tramite un'infrastruttura di autorità di certificazione (CA) Microsoft o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="494f5-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="494f5-115">Per informazioni dettagliate sui requisiti dei certificati in Skype for Business Server, vedere [requisiti ambientali per i requisiti di Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [Server per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="494f5-115">For details about certificate requirements in Skype for Business Server, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
## <a name="user-configuration"></a><span data-ttu-id="494f5-116">Configurazione utente</span><span class="sxs-lookup"><span data-stu-id="494f5-116">User configuration</span></span>

<span data-ttu-id="494f5-117">Se il Mediation Server è stato collocato con ogni pool Front end o server Standard Edition durante la distribuzione front-end, le impostazioni utente necessarie per Enterprise Voice sono state configurate automaticamente durante l'installazione dei file per i ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="494f5-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>
  
<span data-ttu-id="494f5-118">Se si sta distribuendo di nuovo il carico di lavoro VoIP aziendale in questo momento, prima di iniziare il processo di distribuzione, designare un numero di telefono principale per ogni utente che si prevede di abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="494f5-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="494f5-119">Come amministratore, sei responsabile per verificare che questo numero sia univoco.</span><span class="sxs-lookup"><span data-stu-id="494f5-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="494f5-120">Prima dell'implementazione, tutti i numeri di telefono primari devono essere normalizzati (formattati correttamente) e copiati nella proprietà **URI della linea** di ogni utente usando il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="494f5-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user's **Line URI** property using Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="494f5-121">Per esempi di numeri di telefono primari necessari per la distribuzione di VoIP aziendale, Vedi [regole di normalizzazione di esempio](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span><span class="sxs-lookup"><span data-stu-id="494f5-121">For examples of primary phone numbers required for Enterprise Voice deployment, see [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules).</span></span> 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="494f5-122">Passaggi successivi: installare i file o configurare la connettività PSTN</span><span class="sxs-lookup"><span data-stu-id="494f5-122">Next Steps: Install files or configure PSTN connectivity</span></span>

<span data-ttu-id="494f5-123">Dopo aver verificato il software e i prerequisiti ambientali per Enterprise Voice, è possibile:</span><span class="sxs-lookup"><span data-stu-id="494f5-123">After verifying software and environmental prerequisites for Enterprise Voice you can either:</span></span>
  
- <span data-ttu-id="494f5-124">Installare il Mediation Server, come descritto in [distribuire un Mediation Server in Generatore di topologia in Skype for Business Server](deploy-a-mediation-server.md), ma solo se si vuole distribuire un server o un pool di mediazione autonomo perché i server di mediazione vengono installati come parte del pool di front-end o del processo di distribuzione del server Standard Edition durante la collocazione.</span><span class="sxs-lookup"><span data-stu-id="494f5-124">Install the Mediation Server, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>
    
- <span data-ttu-id="494f5-125">In alternativa, iniziare a configurare le impostazioni per instradare le chiamate per gli utenti di VoIP aziendale, come descritto in [configurare Trunks in Skype for Business Server](configure-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="494f5-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configure trunks in Skype for Business Server](configure-trunks.md).</span></span>
    

