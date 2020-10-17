---
title: Prerequisiti di configurazione e sicurezza per VoIP aziendale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8f0f3dd113b10a01f18a0542561de946d4acd0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510473"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="fd14e-102">Prerequisiti di configurazione e sicurezza per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd14e-102">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd14e-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fd14e-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fd14e-104">Verificare che l'infrastruttura soddisfi i prerequisiti di sicurezza, configurazione utente e hardware specifici dello scenario.</span><span class="sxs-lookup"><span data-stu-id="fd14e-104">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="fd14e-105">Diritti amministrativi e infrastruttura di certificazione</span><span class="sxs-lookup"><span data-stu-id="fd14e-105">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="fd14e-106">Verificare che nell'ambiente siano configurati i gruppi di utenti con privilegi amministrativi e l'infrastruttura di certificazione seguenti da utilizzare durante il processo di distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="fd14e-106">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="fd14e-107">Gli amministratori che distribuiscono VoIP aziendale devono essere membri del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fd14e-107">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="fd14e-108">Gli amministratori che eseguono le attività di configurazione devono disporre di diritti appropriati:</span><span class="sxs-lookup"><span data-stu-id="fd14e-108">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="fd14e-109">**CsVoiceAdministrator:** questo ruolo di amministratore consente di eseguire attività di configurazione vocale, di gestire le applicazioni vocali e di assegnare criteri vocali agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="fd14e-109">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="fd14e-p101">**CsUserAdministrator:** questo ruolo di amministratore consente di gestire le proprietà degli utenti, ad esempio l'abilitazione di VoIP aziendale per un utente. Consente inoltre di assegnare criteri per utente, ad eccezione del criterio di archiviazione, di spostare gli utenti e di gestire i telefoni di area comune e i dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="fd14e-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="fd14e-112">**CsAdministrator:** questo ruolo di amministratore consente di eseguire tutte le attività di CsVoiceAdministrator e CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fd14e-112">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="fd14e-113">La delega consente a più amministratori di partecipare alla distribuzione di Lync Server senza aprire un accesso non necessario alle risorse.</span><span class="sxs-lookup"><span data-stu-id="fd14e-113">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="fd14e-114">La distribuzione e la configurazione dell'infrastruttura MKI (Managed Key Infrastructure) vengono eseguite utilizzando un'infrastruttura di autorità di certificazione (CA) Microsoft o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="fd14e-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="fd14e-115">Per informazioni dettagliate sui requisiti dei certificati in Lync Server, vedere <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate Infrastructure requirements for Lync server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="fd14e-115">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="fd14e-116">Configurazione utente</span><span class="sxs-lookup"><span data-stu-id="fd14e-116">User Configuration</span></span>

<span data-ttu-id="fd14e-117">Se il Mediation Server è stato collocato con ogni pool Front end o server Standard Edition durante la distribuzione front-end, le impostazioni utente necessarie per VoIP aziendale sono state configurate automaticamente durante l'installazione dei file per i ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="fd14e-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="fd14e-118">Se si sta procedendo ora alla distribuzione del carico di lavoro di VoIP aziendale, prima di iniziare il processo di distribuzione designare un numero di telefono primario per ogni utente che si intende abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="fd14e-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="fd14e-119">In qualità di amministratori, è necessario verificare che questo numero sia univoco.</span><span class="sxs-lookup"><span data-stu-id="fd14e-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="fd14e-120">Prima dell'implementazione, tutti i numeri di telefono primari devono essere normalizzati (formattati correttamente) e copiati nella proprietà **URI di linea** di ogni utente utilizzando il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd14e-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fd14e-121">Per esempi di numeri di telefono primari necessari per la distribuzione di VoIP aziendale, vedere le <A href="lync-server-2013-dial-plans-and-normalization-rules.md">regole di dial plan e di normalizzazione in Lync server 2013</A> sezione dei <A href="lync-server-2013-dial-plans-and-normalization-rules.md">dial plan e delle regole di normalizzazione in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="fd14e-121">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="fd14e-122">Passaggi successivi: installare i file o configurare la connettività PSTN</span><span class="sxs-lookup"><span data-stu-id="fd14e-122">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="fd14e-123">Dopo avere verificato i prerequisiti software e ambientali per VoIP aziendale, è possibile utilizzare il contenuto seguente per eseguire una delle operazioni indicate di seguito:</span><span class="sxs-lookup"><span data-stu-id="fd14e-123">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="fd14e-124">Installare il Mediation Server, come descritto in [Install the files for Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), ma solo se si desidera distribuire un Mediation Server autonomo o un pool perché i Mediation Server vengono installati come parte del pool Front end o del processo di distribuzione del server Standard Edition durante la collocazione.</span><span class="sxs-lookup"><span data-stu-id="fd14e-124">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="fd14e-125">In alternativa, iniziare a configurare le impostazioni per instradare le chiamate per gli utenti di VoIP aziendale, come descritto in [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="fd14e-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

