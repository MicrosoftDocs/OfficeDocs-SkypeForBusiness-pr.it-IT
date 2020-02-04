---
title: >
  Lync Server 2013: Configurare criteri per controllare l'accesso degli utenti pubblici
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
ms.openlocfilehash: b348abcce00eb57988c7aa5184c0cfb5ea302adb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a><span data-ttu-id="36338-102">Configurare criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36338-102">Configure policies to control public user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36338-103">_**Argomento Ultima modifica:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="36338-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="36338-104">La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di usare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblici, tra cui la\!rete Windows Live di Internet Services, Yahoo e AOL.</span><span class="sxs-lookup"><span data-stu-id="36338-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live network of Internet services, Yahoo\!, and AOL.</span></span> <span data-ttu-id="36338-105">Si configurano uno o più criteri di accesso degli utenti esterni per controllare se gli utenti pubblici possono collaborare con gli utenti interni di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="36338-105">You configure one or more external user access policies to control whether public users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="36338-106">La connettività di messaggistica istantanea pubblica è una caratteristica aggiunta che si basa sulla configurazione della distribuzione e degli utenti.</span><span class="sxs-lookup"><span data-stu-id="36338-106">Public instant messaging connectivity is an added feature that relies on configuration of your deployment and users.</span></span> <span data-ttu-id="36338-107">Dipende anche dal provisioning del servizio presso il provider di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="36338-107">It also depends on the provisioning of the service at the public IM provider.</span></span> <span data-ttu-id="36338-108">Per informazioni su come eseguire il provisioning della distribuzione per l'uso dei provider pubblici, vedere la Guida introduttiva "Guida al provisioning della connettività per messaggistica istantanea pubblica per Microsoft Lync Server, Office Communications Server e Live Communications Server":[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span><span class="sxs-lookup"><span data-stu-id="36338-108">For information on how to provision your deployment to use the public providers, see the “Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server, and Live Communications Server” guide: [http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="36338-109">A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="36338-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="36338-110">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="36338-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="36338-111">Messenger fino alla data di chiusura del servizio.</span><span class="sxs-lookup"><span data-stu-id="36338-111">Messenger until the service shut down date.</span></span> <span data-ttu-id="36338-112">Data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="36338-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="36338-113">è stato annunciato.</span><span class="sxs-lookup"><span data-stu-id="36338-113">has been announced.</span></span> <span data-ttu-id="36338-114">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="36338-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="36338-115">Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="36338-115">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="36338-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="36338-116">Messenger.</span></span> <span data-ttu-id="36338-117">La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</span><span class="sxs-lookup"><span data-stu-id="36338-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="36338-118">Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="36338-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="36338-119">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="36338-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="36338-120">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</span><span class="sxs-lookup"><span data-stu-id="36338-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="36338-121">Per accedere al sito di provisioning della connettività di messaggistica istantanea pubblica di Microsoft Lync Server, usare il collegamento seguente:[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span><span class="sxs-lookup"><span data-stu-id="36338-121">To access the Microsoft Lync Server Public IM Connectivity Provisioning site, use the following link: [http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)</span></span>

<span data-ttu-id="36338-122">Per controllare l'accesso degli utenti pubblici, è possibile configurare i criteri a livello globale, sito e utente.</span><span class="sxs-lookup"><span data-stu-id="36338-122">To control public user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="36338-123">Per informazioni dettagliate sui tipi di criteri che è possibile configurare, vedere [configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="36338-123">For details about the types of policies that you can configure, see [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) in the Deployment documentation or the Planning documentation.</span></span> <span data-ttu-id="36338-124">Le impostazioni dei criteri di Lync Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="36338-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="36338-125">La precedenza dei criteri di Lync Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza).</span><span class="sxs-lookup"><span data-stu-id="36338-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="36338-126">Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="36338-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<span data-ttu-id="36338-127">In caso di inviti alla messaggistica istantanea, la risposta dipende dal software client.</span><span class="sxs-lookup"><span data-stu-id="36338-127">In the case of IM invitations, the response depends on the client software.</span></span> <span data-ttu-id="36338-128">La richiesta viene accettata a meno che i mittenti esterni non siano esplicitamente bloccati da una regola configurata dall'utente, ovvero le impostazioni negli elenchi **Consenti** e **blocca** del client dell'utente.</span><span class="sxs-lookup"><span data-stu-id="36338-128">The request is accepted unless external senders are explicitly blocked by a user-configured rule (that is, the settings in the user’s client **Allow** and **Block** lists).</span></span> <span data-ttu-id="36338-129">Inoltre, gli inviti di messaggistica istantanea possono essere bloccati se un utente sceglie di bloccare tutti i messaggi istantanei da utenti che non sono presenti nell'elenco **Consenti** .</span><span class="sxs-lookup"><span data-stu-id="36338-129">Additionally, IM invitations can be blocked if a user elects to block all IM from users who are not on his or her **Allow** list.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36338-130">È possibile configurare i criteri per controllare l'accesso degli utenti pubblici, anche se non è stata abilitata la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36338-130">You can configure policies to control public user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="36338-131">Tuttavia, i criteri configurati sono attivi solo quando è abilitata la Federazione per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36338-131">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="36338-132">Per informazioni dettagliate sull'abilitazione della Federazione, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="36338-132">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="36338-133">Inoltre, se specifichi un criterio utente per controllare l'accesso degli utenti pubblici, il criterio si applica solo agli utenti abilitati per Lync Server e configurati per l'uso dei criteri.</span><span class="sxs-lookup"><span data-stu-id="36338-133">Additionally, if you specify a user policy to control public user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="36338-134">Per informazioni dettagliate su come specificare gli utenti pubblici che possono accedere a Lync Server, vedere <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">assegnare criteri di accesso degli utenti esterni a un utente abilitato a Lync in Lync Server 2013</A> nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="36338-134">For details about specifying public users that can sign in to Lync Server, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<span data-ttu-id="36338-135">Usare la procedura seguente per configurare un criterio per supportare l'accesso da parte di utenti di uno o più provider di messaggistica istantanea pubblici.</span><span class="sxs-lookup"><span data-stu-id="36338-135">Use the following procedure to configure a policy to support access by users of one or more public IM providers.</span></span>

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a><span data-ttu-id="36338-136">Per configurare un criterio di accesso esterno per supportare l'accesso degli utenti pubblici</span><span class="sxs-lookup"><span data-stu-id="36338-136">To configure an external access policy to support public user access</span></span>

1.  <span data-ttu-id="36338-137">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="36338-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="36338-138">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="36338-138">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="36338-139">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="36338-139">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="36338-140">Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="36338-140">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="36338-141">Nella pagina **criteri di accesso esterno** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="36338-141">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="36338-142">Per configurare il criterio globale per supportare l'accesso degli utenti pubblici, fare clic sul criterio globale, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="36338-142">To configure the global policy to support public user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="36338-143">Per creare un nuovo criterio sito, fare clic su **nuovo**e quindi su **criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="36338-143">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="36338-144">In **Seleziona un sito**fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="36338-144">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="36338-145">Per creare un nuovo criterio utente, fare clic su **nuovo**e quindi su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="36338-145">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="36338-146">In **nuovi criteri di accesso esterno**, creare un nome univoco nel campo **nome** che indichi le informazioni relative ai criteri utente, ad esempio **EnablePublicUsers** , per un criterio utente che consente le comunicazioni per gli utenti pubblici.</span><span class="sxs-lookup"><span data-stu-id="36338-146">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnablePublicUsers** for a user policy that enables communications for public users).</span></span>
    
      - <span data-ttu-id="36338-147">Per modificare un criterio esistente, fare clic sul criterio appropriato elencato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="36338-147">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="36338-148">Opzionale Se si vuole aggiungere o modificare una descrizione, specificare le informazioni per il criterio in **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="36338-148">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="36338-149">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="36338-149">Do one of the following:</span></span>
    
      - <span data-ttu-id="36338-150">Per abilitare l'accesso degli utenti pubblici al criterio, selezionare la casella di controllo **Abilita comunicazioni con gli utenti pubblici** .</span><span class="sxs-lookup"><span data-stu-id="36338-150">To enable public user access for the policy, select the **Enable communications with public users** check box.</span></span>
    
      - <span data-ttu-id="36338-151">Per disabilitare l'accesso degli utenti pubblici per il criterio, deselezionare la casella di controllo **Abilita comunicazioni con gli utenti pubblici** .</span><span class="sxs-lookup"><span data-stu-id="36338-151">To disable public user access for the policy, clear the **Enable communications with public users** check box.</span></span>

7.  <span data-ttu-id="36338-152">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="36338-152">Click **Commit**.</span></span>

<span data-ttu-id="36338-153">Per abilitare l'accesso degli utenti pubblici, devi anche abilitare il supporto per la Federazione nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36338-153">To enable public user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="36338-154">Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti federati in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="36338-154">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

<span data-ttu-id="36338-155">Se si tratta di un criterio utente, è necessario applicare il criterio anche agli utenti pubblici che si vuole poter collaborare con gli utenti pubblici.</span><span class="sxs-lookup"><span data-stu-id="36338-155">If this is a user policy, you must also apply the policy to public users that you want to be able to collaborate with public users.</span></span> <span data-ttu-id="36338-156">Per informazioni dettagliate, vedere [assegnazione di criteri per utente in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span><span class="sxs-lookup"><span data-stu-id="36338-156">For details, see [Assigning per-user policies in Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36338-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36338-157">See Also</span></span>


[<span data-ttu-id="36338-158">Creare o modificare provider federati SIP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36338-158">Create or edit public SIP federated providers in Lync Server 2013</span></span>](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[<span data-ttu-id="36338-159">Gestire i provider federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36338-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

