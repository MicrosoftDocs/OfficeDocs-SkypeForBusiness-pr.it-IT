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
ms.openlocfilehash: 6530e00a942e2e839eaf4bc2d069212b746e2504
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="aef20-102">Prerequisiti per la sicurezza e la configurazione di Enterprise Voice in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aef20-102">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aef20-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="aef20-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="aef20-104">Verificare che l'infrastruttura soddisfi i prerequisiti hardware specifici per la sicurezza, la configurazione degli utenti e gli scenari.</span><span class="sxs-lookup"><span data-stu-id="aef20-104">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="aef20-105">Diritti amministrativi e infrastruttura dei certificati</span><span class="sxs-lookup"><span data-stu-id="aef20-105">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="aef20-106">Assicurarsi che l'ambiente sia configurato con i gruppi di utenti amministrativi e l'infrastruttura di certificato seguenti per l'uso durante il processo di distribuzione vocale aziendale.</span><span class="sxs-lookup"><span data-stu-id="aef20-106">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="aef20-107">Gli amministratori che distribuiscono VoIP aziendale devono essere membri del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="aef20-107">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="aef20-108">Gli amministratori che eseguono le attività di configurazione devono avere diritti adeguati:</span><span class="sxs-lookup"><span data-stu-id="aef20-108">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="aef20-109">**CsVoiceAdministrator:** Questo ruolo di amministratore può eseguire attività di configurazione vocale, gestire le applicazioni vocali e assegnare criteri vocali agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="aef20-109">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="aef20-110">**CsUserAdministrator:** Questo ruolo di amministratore può gestire le proprietà degli utenti, ad esempio l'abilitazione di VoIP aziendale per un utente.</span><span class="sxs-lookup"><span data-stu-id="aef20-110">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user.</span></span> <span data-ttu-id="aef20-111">Questo ruolo di amministratore può anche assegnare criteri per utente, ad eccezione dei criteri di archiviazione. trasferire utenti; e Gestisci telefoni per area comune e dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="aef20-111">This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="aef20-112">**CsAdministrator:** Questo ruolo di amministratore può eseguire tutte le attività di CsVoiceAdministrator e CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="aef20-112">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="aef20-113">La delega consente a più amministratori di partecipare alla distribuzione di Lync Server senza aprire l'accesso non necessario alle risorse.</span><span class="sxs-lookup"><span data-stu-id="aef20-113">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="aef20-114">L'infrastruttura MKI (Managed Key Infrastructure) viene distribuita e configurata tramite un'infrastruttura di autorità di certificazione (CA) Microsoft o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="aef20-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="aef20-115">Per informazioni dettagliate sui requisiti dei certificati in Lync Server, vedere <A href="lync-server-2013-certificate-infrastructure-requirements.md">requisiti per l'infrastruttura dei certificati per Lync server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="aef20-115">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="aef20-116">Configurazione utente</span><span class="sxs-lookup"><span data-stu-id="aef20-116">User Configuration</span></span>

<span data-ttu-id="aef20-117">Se il Mediation Server è stato collocato con ogni pool Front end o server Standard Edition durante la distribuzione front-end, le impostazioni utente necessarie per Enterprise Voice sono state configurate automaticamente durante l'installazione dei file per i ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="aef20-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="aef20-118">Se si sta distribuendo di nuovo il carico di lavoro VoIP aziendale in questo momento, prima di iniziare il processo di distribuzione, designare un numero di telefono principale per ogni utente che si prevede di abilitare per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="aef20-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="aef20-119">Come amministratore, sei responsabile per verificare che questo numero sia univoco.</span><span class="sxs-lookup"><span data-stu-id="aef20-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="aef20-120">Prima dell'implementazione, tutti i numeri di telefono primari devono essere normalizzati (formattati correttamente) e copiati nella proprietà **URI della linea** di ogni utente usando il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aef20-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="aef20-121">Per gli esempi di numeri di telefono principali necessari per la distribuzione di VoIP aziendale, vedere le <A href="lync-server-2013-dial-plans-and-normalization-rules.md">regole di dial plan e normalizzazione nella sezione Lync server 2013</A> di <A href="lync-server-2013-dial-plans-and-normalization-rules.md">dial plan e regole di normalizzazione in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="aef20-121">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="aef20-122">Passaggi successivi: installare i file o configurare la connettività PSTN</span><span class="sxs-lookup"><span data-stu-id="aef20-122">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="aef20-123">Dopo aver verificato il software e i prerequisiti ambientali per Enterprise Voice, è possibile usare il contenuto seguente per:</span><span class="sxs-lookup"><span data-stu-id="aef20-123">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="aef20-124">Installare il Mediation Server, come descritto in [installare i file per Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), ma solo se si vuole distribuire un server o un pool di mediazione autonomo perché i server di mediazione vengono installati come parte del pool di front-end o del processo di distribuzione del server standard in una posizione collocata.</span><span class="sxs-lookup"><span data-stu-id="aef20-124">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="aef20-125">In alternativa, iniziare la configurazione delle impostazioni per instradare le chiamate per gli utenti di VoIP aziendale, come descritto in [configurazione di Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="aef20-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

