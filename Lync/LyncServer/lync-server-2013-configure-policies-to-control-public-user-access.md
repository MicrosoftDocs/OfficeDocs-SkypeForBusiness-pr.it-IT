---
title: "Lync Server 2013: configurare i criteri per il controllo dell'accesso degli utenti pubblici"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12a6e5d94cef7c9f25bb1c4091a981603f66da82
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="6ba36-102">Configurazione di criteri per il controllo dell'accesso degli utenti pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ba36-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ba36-103">_**Ultimo argomento modificato:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="6ba36-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="6ba36-104">La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblica, tra cui la\!rete Windows Live di servizi Internet, Yahoo e AOL.</span><span class="sxs-lookup"><span data-stu-id="6ba36-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="6ba36-105">È possibile configurare uno o più criteri di accesso utente esterno per controllare se gli utenti pubblici possono collaborare con gli utenti interni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ba36-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="6ba36-106">La connettività per la messaggistica istantanea pubblica è una funzionalità aggiunta che si basa sulla configurazione della distribuzione e degli utenti.</span><span class="sxs-lookup"><span data-stu-id="6ba36-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="6ba36-107">Dipende anche dal provisioning del servizio nel provider di messaggistica istantanea pubblico.</span><span class="sxs-lookup"><span data-stu-id="6ba36-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="6ba36-108">Per informazioni su come eseguire il provisioning della distribuzione per l'utilizzo dei provider pubblici, vedere la guida sulla guida al provisioning della connettività per la messaggistica istantanea pubblica per Microsoft Lync Server, Office Communications Server e Live Communications Server:[https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="6ba36-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="6ba36-109">Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="6ba36-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="6ba36-110">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="6ba36-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="6ba36-111">Messenger fino alla data di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="6ba36-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="6ba36-112">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="6ba36-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="6ba36-113">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="6ba36-113">has been announced.</span></span> <span data-ttu-id="6ba36-114">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6ba36-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="6ba36-115">Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="6ba36-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="6ba36-116">Messaggero.</span><span class="sxs-lookup"><span data-stu-id="6ba36-116">Messenger.</span></span> <span data-ttu-id="6ba36-117">La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</span><span class="sxs-lookup"><span data-stu-id="6ba36-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="6ba36-118">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="6ba36-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="6ba36-119">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="6ba36-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="6ba36-120">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="6ba36-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="6ba36-121">Per accedere al sito di provisioning di connettività per messaggistica istantanea pubblica di Microsoft Lync Server, utilizzare il seguente collegamento:[https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="6ba36-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="6ba36-122">Per controllare l'accesso degli utenti pubblici, è possibile configurare i criteri a livello globale, di sito e di utente.</span><span class="sxs-lookup"><span data-stu-id="6ba36-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="6ba36-123">Per informazioni dettagliate sui tipi di criteri che è possibile configurare, vedere [configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6ba36-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="6ba36-124">Le impostazioni criteri di Lync Server applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="6ba36-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="6ba36-125">La precedenza dei criteri di Lync Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza).</span><span class="sxs-lookup"><span data-stu-id="6ba36-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="6ba36-126">Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="6ba36-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="6ba36-127">Nel caso degli inviti di messaggistica istantanea, la risposta dipende dal software client.</span><span class="sxs-lookup"><span data-stu-id="6ba36-127">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="6ba36-128">La richiesta viene accettata, a meno che i mittenti esterni siano esplicitamente bloccati da una regola configurata dall'utente, ovvero le impostazioni negli elenchi **Consenti** e **blocca** client dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6ba36-128">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="6ba36-129">Inoltre, gli inviti di messaggistica istantanea possono essere bloccati se un utente decide di bloccare tutti i messaggi istantanei provenienti da utenti che non sono presenti nell'elenco **Consenti** .</span><span class="sxs-lookup"><span data-stu-id="6ba36-129">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6ba36-130">È possibile configurare i criteri per controllare l'accesso degli utenti pubblici, anche se non è stata abilitata la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6ba36-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="6ba36-131">I criteri configurati, tuttavia, verranno applicati solo dopo aver abilitato la federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6ba36-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="6ba36-132">Per informazioni dettagliate sull'abilitazione della Federazione, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="6ba36-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="6ba36-133">Inoltre, se si specifica un criterio utente per il controllo dell'accesso degli utenti pubblici, il criterio si applica solo agli utenti abilitati per Lync Server e configurati per l'utilizzo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="6ba36-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="6ba36-134">Per informazioni dettagliate sulla specifica degli utenti pubblici che possono accedere a Lync Server, vedere <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="6ba36-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="6ba36-135">Utilizzare la procedura seguente per configurare un criterio per il supporto dell'accesso da parte di utenti di uno o più provider di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="6ba36-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="6ba36-136">Per configurare un criterio di accesso esterno per il supporto dell'accesso degli utenti pubblici</span><span class="sxs-lookup"><span data-stu-id="6ba36-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="6ba36-137">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="6ba36-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6ba36-138">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ba36-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6ba36-139">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6ba36-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6ba36-140">Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="6ba36-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="6ba36-141">Nella pagina **Criteri di accesso esterno** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ba36-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="6ba36-142">Per configurare i criteri globali per il supporto dell'accesso degli utenti pubblici, fare clic sul criterio globale, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="6ba36-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="6ba36-p109">Per creare un nuovo criterio sito fare clic su **Nuovo** e quindi su **Criteri sito**. In **Seleziona un sito** fare clic sul sito appropriato nell'elenco e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ba36-p109">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="6ba36-145">Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="6ba36-145">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="6ba36-146">In **nuovi criteri di accesso esterno**, creare un nome univoco nel campo **nome** che indica le coperture dei criteri utente, ad esempio **EnablePublicUsers** per i criteri utente che abilitano le comunicazioni per gli utenti pubblici.</span><span class="sxs-lookup"><span data-stu-id="6ba36-146">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="6ba36-147">Per modificare criteri esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="6ba36-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="6ba36-148">(Facoltativo) Se si desidera aggiungere o modificare una descrizione, specificare le informazioni per i criteri in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="6ba36-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="6ba36-149">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ba36-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="6ba36-150">Per abilitare l'accesso degli utenti pubblici per i criteri, selezionare la casella di controllo **Abilita comunicazioni con utenti pubblici** .</span><span class="sxs-lookup"><span data-stu-id="6ba36-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="6ba36-151">Per disabilitare l'accesso degli utenti pubblici per i criteri, deselezionare la casella di controllo **Abilita comunicazioni con utenti pubblici** .</span><span class="sxs-lookup"><span data-stu-id="6ba36-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="6ba36-152">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="6ba36-152">Click **Commit**.</span></span>

<span data-ttu-id="6ba36-153">Per abilitare l'accesso degli utenti pubblici, è necessario abilitare anche il supporto della federazione nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6ba36-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="6ba36-154">Per ulteriori informazioni, vedere [Configure policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="6ba36-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="6ba36-155">Se si tratta di un criterio utente, è inoltre necessario applicare il criterio agli utenti pubblici che si desidera consentire la collaborazione con gli utenti pubblici.</span><span class="sxs-lookup"><span data-stu-id="6ba36-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="6ba36-156">Per informazioni dettagliate, vedere [assegnazione di criteri per utente in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6ba36-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ba36-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ba36-157">See Also</span></span>


[<span data-ttu-id="6ba36-158">Creare o modificare provider federati SIP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ba36-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="6ba36-159">Gestire i provider federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ba36-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

