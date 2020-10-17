---
title: "Lync Server 2013: configurare i criteri per il controllo dell'accesso degli utenti remoti"
description: "Lync Server 2013: configurare i criteri per il controllo dell'accesso degli utenti remoti."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6408747cfbbc5e7dff8fd198c0de162f49fc5ff2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548712"
---
# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="3d995-103">Configurazione di criteri per il controllo dell'accesso degli utenti remoti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d995-103">Configure policies to control remote user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d995-104">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="3d995-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="3d995-105">È possibile configurare uno o più criteri di accesso utente esterno per controllare se gli utenti remoti possono collaborare con gli utenti interni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d995-105">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="3d995-106">Per controllare l'accesso degli utenti remoti è possibile configurare criteri a livello globale, di sito e di utente.</span><span class="sxs-lookup"><span data-stu-id="3d995-106">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="3d995-107">I criteri a livello di sito hanno la priorità sui criteri globali e i criteri utente hanno la priorità sui criteri a livello di sito e globali.</span><span class="sxs-lookup"><span data-stu-id="3d995-107">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="3d995-108">Per informazioni dettagliate sui tipi di criteri che è possibile configurare, vedere [Managing Federation and External Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="3d995-108">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="3d995-109">Le impostazioni criteri di Lync Server applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="3d995-109">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="3d995-110">La precedenza dei criteri di Lync Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza).</span><span class="sxs-lookup"><span data-stu-id="3d995-110">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="3d995-111">Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="3d995-111">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d995-112">È possibile configurare criteri per il controllo dell'accesso degli utenti remoti anche se non si è abilitato l'accesso utente remoto per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3d995-112">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="3d995-113">I criteri configurati, tuttavia, verranno applicati solo dopo l'abilitazione dell'accesso utente remoto per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3d995-113">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="3d995-114">Per informazioni dettagliate sull'abilitazione dell'accesso degli utenti remoti, vedere <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3d995-114">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="3d995-115">Inoltre, se si specifica un criterio utente per il controllo dell'accesso degli utenti remoti, il criterio si applica solo agli utenti abilitati per Lync Server e configurati per l'utilizzo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="3d995-115">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="3d995-116">Per informazioni dettagliate su come specificare gli utenti che possono accedere a Lync Server da postazioni remote, vedere <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3d995-116">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="3d995-117">Eseguire la procedura seguente per configurare ogni criterio di accesso esterno che si desidera utilizzare per controllare l'accesso degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="3d995-117">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d995-118">Questa procedura descrive come configurare un criterio solo per abilitare le comunicazioni con gli utenti remoti, ma qualsiasi criterio configurato per il supporto dell'accesso utente remoto può configurare anche l'accesso degli utenti federati e l'accesso degli utenti pubblici.</span><span class="sxs-lookup"><span data-stu-id="3d995-118">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="3d995-119">Per informazioni dettagliate sulla configurazione dei criteri per il supporto degli utenti federati, vedere <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to Control Federated User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3d995-119">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="3d995-120">Per informazioni dettagliate sulla configurazione dei criteri per il supporto degli utenti pubblici, vedere <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">creare o modificare provider federati SIP pubblici in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3d995-120">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="3d995-121">Per configurare un criterio di accesso esterno per il supporto dell'accesso utente remoto</span><span class="sxs-lookup"><span data-stu-id="3d995-121">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="3d995-122">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3d995-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3d995-123">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d995-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3d995-124">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3d995-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3d995-125">Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="3d995-125">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="3d995-126">Nella pagina **Criteri di accesso esterno** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d995-126">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="3d995-127">Per configurare il criterio globale per il supporto dell'accesso utente remoto, fare clic sul criterio globale, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3d995-127">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="3d995-p105">Per creare nuovi criteri di sito, fare clic su **Nuovo** e quindi su **Criteri sito**. In **Seleziona un sito** fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d995-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="3d995-p106">Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. In **Nuovi criteri di accesso esterno** creare un nome univoco nel campo **Nome** che indichi lo scopo del criterio, ad esempio **AbilitaUtentiRemoti** per un criterio utente che abilita le comunicazioni per gli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="3d995-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="3d995-132">Per modificare criteri esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3d995-132">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3d995-133">(Facoltativo) Se si desidera aggiungere o modificare una descrizione, specificare le informazioni per i criteri in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="3d995-133">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="3d995-134">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d995-134">Do one of the following:</span></span>
    
      - <span data-ttu-id="3d995-135">Per abilitare l'accesso utente remoto per il criterio, selezionare la casella di controllo **Abilita comunicazioni con utenti remoti**.</span><span class="sxs-lookup"><span data-stu-id="3d995-135">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="3d995-136">Per disabilitare l'accesso utente remoto per il criterio, deselezionare la casella di controllo **Abilita comunicazioni con utenti remoti**.</span><span class="sxs-lookup"><span data-stu-id="3d995-136">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="3d995-137">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3d995-137">Click **Commit**.</span></span>

<span data-ttu-id="3d995-138">Per abilitare l'accesso utente remoto è necessario abilitare anche il supporto dell'accesso utente remoto nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3d995-138">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="3d995-139">Per ulteriori informazioni, vedere [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="3d995-139">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="3d995-140">Se si tratta di un criterio utente è inoltre necessario applicare il criterio agli utenti ai quali si desidera consentire di effettuare l'accesso in remoto.</span><span class="sxs-lookup"><span data-stu-id="3d995-140">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="3d995-141">Per ulteriori informazioni, vedere [assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="3d995-141">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

