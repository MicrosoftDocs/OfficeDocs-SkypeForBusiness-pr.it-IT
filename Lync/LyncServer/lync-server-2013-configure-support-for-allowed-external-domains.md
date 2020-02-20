---
title: 'Lync Server 2013: configurare il supporto per i domini esterni consentiti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51190fd787fde408913b71d4a5ce6f1d002a6d28
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="7aa4c-102">Configurare il supporto per i domini esterni consentiti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa4c-102">Configure support for allowed external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aa4c-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7aa4c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7aa4c-p101">Se è stato configurato il supporto per i partner federati, è possibile specificare i domini che possono eseguire la federazione con l'organizzazione. Configurare uno o più domini esterni specifici come domini federati consentiti. A tale scopo, aggiungere ogni dominio all'elenco dei domini consentiti. Anche se per l'organizzazione è abilitata l'individuazione del partner, eseguire questa operazione se il dominio è un partner federato che potrebbe dover comunicare con oltre 1.000 utenti dell'organizzazione o inviare più di 20 messaggi al secondo. Se per l'organizzazione non è abilitata l'individuazione del partner, solo gli utenti dei domini esterni aggiunti all'elenco dei domini consentiti potranno partecipare alla messaggistica istantanea e alle conferenze con gli utenti dell'organizzazione. Se si desidera limitare l'accesso di un dominio federato a un server specifico che esegue il servizio Access Edge del partner federato, è possibile specificare il nome di dominio del server che esegue il servizio Access Edge per ogni dominio incluso nell'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-p101">If you have configured support for federated partners, you can manage which specific domains can federate with your organization. You configure one or more specific external domains as allowed federated domains. To do this, add each domain to the list of allowed domains. Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second. If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization. If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7aa4c-110">Questa procedura descrive come configurare il supporto per domini specifici, ma l'implementazione del supporto per gli utenti federati richiede inoltre di abilitare il supporto per gli utenti federati dell'organizzazione, nonché di configurare e applicare criteri per specificare quali utenti possono collaborare con gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="7aa4c-111">Per informazioni dettagliate sull'abilitazione del supporto per gli utenti federati, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or Disable Remote User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="7aa4c-112">Per informazioni dettagliate sulla configurazione dei criteri per il controllo della Federazione, vedere <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to Control Federated User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="7aa4c-113">Per aggiungere un dominio esterno all'elenco dei domini consentiti</span><span class="sxs-lookup"><span data-stu-id="7aa4c-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="7aa4c-114">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7aa4c-115">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7aa4c-116">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7aa4c-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7aa4c-117">Nella barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Domini federati**.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="7aa4c-118">Nella pagina **Domini federati** fare clic su **Nuovo** e quindi su **Dominio consentito**.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="7aa4c-119">In **Nuovi domini federati** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7aa4c-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="7aa4c-120">In **Nome di dominio (o FQDN)** digitare il nome del dominio del partner federato.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7aa4c-p104">Il nome deve essere univoco e non deve esistere già come dominio consentito per il server che esegue il servizio Access Edge. Il nome può essere costituito da un massimo di 256 caratteri.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-p104">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service. The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="7aa4c-p105">La ricerca in base al nome di dominio del partner federato si basa sulla corrispondenza del suffisso. Se ad esempio si digita <STRONG>contoso.com</STRONG>, la ricerca restituirà anche il dominio <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-p105">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="7aa4c-125">Un dominio di partner federato non può essere contemporaneamente bloccato e consentito.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="7aa4c-126">Lync Server 2013 impedisce l'avvenuto verificarsi in modo da non dover sincronizzare gli elenchi.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="7aa4c-127">Se si desidera limitare l'accesso per questo dominio federato agli utenti di un server specifico che esegue il servizio Access Edge, in **Servizio Access Edge (FQDN)** digitare l'FQDN del server del dominio federato che esegue il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="7aa4c-128">Se si desidera fornire ulteriori informazioni, in **Commento** digitare le informazioni che si desidera condividere con altri amministratori di sistema sulla configurazione.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="7aa4c-129">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="7aa4c-130">Ripetere i passaggi da 4 a 6 per ogni dominio di partner federato che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="7aa4c-131">Per consentire l'accesso degli utenti federati, è inoltre necessario abilitare il supporto per l'accesso degli utenti federati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="7aa4c-132">Per ulteriori informazioni, vedere [Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7aa4c-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="7aa4c-133">È inoltre necessario configurare e applicare il criterio agli utenti per i quali si desidera consentire la collaborazione con gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="7aa4c-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="7aa4c-134">Per ulteriori informazioni, vedere [Configure policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7aa4c-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

