---
title: "Lync Server 2013: Configurare criteri per controllare l'accesso degli utenti remoti"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e542f2a2d836cce507863347384135f97db445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="351a1-102">Configurare criteri per controllare l'accesso degli utenti remoti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="351a1-102">Configure policies to control remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="351a1-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="351a1-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="351a1-104">Si configurano uno o più criteri di accesso degli utenti esterni per controllare se gli utenti remoti possono collaborare con gli utenti interni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="351a1-104">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="351a1-105">Per controllare l'accesso degli utenti remoti, è possibile configurare i criteri a livello globale, sito e utente.</span><span class="sxs-lookup"><span data-stu-id="351a1-105">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="351a1-106">I criteri del sito sostituiscono i criteri globali e i criteri utente sostituiscono il sito e i criteri globali.</span><span class="sxs-lookup"><span data-stu-id="351a1-106">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="351a1-107">Per informazioni dettagliate sui tipi di criteri che è possibile configurare, vedere [gestione della Federazione e accesso esterno a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="351a1-107">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="351a1-108">Le impostazioni dei criteri di Lync Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="351a1-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="351a1-109">La precedenza dei criteri di Lync Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza).</span><span class="sxs-lookup"><span data-stu-id="351a1-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="351a1-110">Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="351a1-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="351a1-111">È possibile configurare i criteri per controllare l'accesso degli utenti remoti, anche se non è stato abilitato l'accesso degli utenti remoti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="351a1-111">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="351a1-112">Tuttavia, i criteri configurati sono attivi solo quando si ha accesso a utenti remoti abilitato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="351a1-112">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="351a1-113">Per informazioni dettagliate sull'abilitazione dell'accesso degli utenti remoti, vedere <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">abilitare o disabilitare la connettività di messaggistica istantanea pubblica e della Federazione in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="351a1-113">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="351a1-114">Inoltre, se specifichi un criterio utente per controllare l'accesso degli utenti remoti, il criterio si applica solo agli utenti abilitati per Lync Server e configurati per l'uso dei criteri.</span><span class="sxs-lookup"><span data-stu-id="351a1-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="351a1-115">Per informazioni dettagliate su come specificare gli utenti che possono accedere a Lync Server da percorsi remoti, vedere <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">assegnare criteri di accesso degli utenti esterni a un utente abilitato a Lync in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="351a1-115">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="351a1-116">Usare la procedura seguente per configurare ogni criterio di accesso esterno che si vuole usare per controllare l'accesso degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="351a1-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="351a1-117">Questa procedura descrive come configurare un criterio solo per abilitare le comunicazioni con gli utenti remoti, ma ogni criterio configurato per supportare l'accesso degli utenti remoti può anche configurare l'accesso degli utenti federati e l'accesso degli utenti pubblici.</span><span class="sxs-lookup"><span data-stu-id="351a1-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="351a1-118">Per informazioni dettagliate sulla configurazione dei criteri per il supporto degli utenti federati, vedere <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configurare i criteri per controllare l'accesso degli utenti federati in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="351a1-118">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="351a1-119">Per informazioni dettagliate sulla configurazione dei criteri per il supporto degli utenti pubblici, vedere <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">creare o modificare provider federati SIP pubblici in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="351a1-119">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="351a1-120">Per configurare un criterio di accesso esterno per supportare l'accesso degli utenti remoti</span><span class="sxs-lookup"><span data-stu-id="351a1-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="351a1-121">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="351a1-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="351a1-122">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="351a1-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="351a1-123">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="351a1-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="351a1-124">Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="351a1-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="351a1-125">Nella pagina **criteri di accesso esterno** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="351a1-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="351a1-126">Per configurare i criteri globali per il supporto dell'accesso degli utenti remoti, fare clic sul criterio globale, scegliere **modifica**e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="351a1-126">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="351a1-127">Per creare un nuovo criterio sito, fare clic su **nuovo**e quindi su **criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="351a1-127">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="351a1-128">In **Seleziona un sito**fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="351a1-128">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="351a1-129">Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="351a1-129">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="351a1-130">In **nuovi criteri di accesso esterno**, creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnableRemoteUsers** , per un criterio utente che consente le comunicazioni per gli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="351a1-130">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="351a1-131">Per modificare un criterio esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="351a1-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="351a1-132">Opzionale Se si vuole aggiungere o modificare una descrizione, specificare le informazioni per il criterio in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="351a1-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="351a1-133">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="351a1-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="351a1-134">Per abilitare l'accesso degli utenti remoti per il criterio, selezionare la casella di controllo **Abilita comunicazioni con utenti remoti** .</span><span class="sxs-lookup"><span data-stu-id="351a1-134">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="351a1-135">Per disabilitare l'accesso degli utenti remoti per il criterio, deselezionare la casella di controllo **Abilita comunicazioni con utenti remoti** .</span><span class="sxs-lookup"><span data-stu-id="351a1-135">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="351a1-136">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="351a1-136">Click **Commit**.</span></span>

<span data-ttu-id="351a1-137">Per abilitare l'accesso remoto agli utenti, è necessario abilitare anche il supporto per l'accesso degli utenti remoti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="351a1-137">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="351a1-138">Per informazioni dettagliate, vedere [abilitare o disabilitare la connettività per la messaggistica istantanea e la Federazione in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="351a1-138">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="351a1-139">Se si tratta di un criterio utente, è necessario applicare il criterio anche agli utenti che si vogliono connettere in remoto.</span><span class="sxs-lookup"><span data-stu-id="351a1-139">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="351a1-140">Per informazioni dettagliate, vedere [assegnare criteri di accesso degli utenti esterni a un utente abilitato a Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="351a1-140">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

