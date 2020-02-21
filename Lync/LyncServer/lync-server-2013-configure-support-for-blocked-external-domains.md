---
title: 'Lync Server 2013: configurare il supporto per i domini esterni bloccati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f24c7db21daa02ff67dc8eb4ddf375c78f96b6d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="9ef43-102">Configurare il supporto per i domini esterni bloccati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ef43-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ef43-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="9ef43-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="9ef43-104">Se il supporto per i partner federati è configurato, è possibile gestire i domini ai quali impedire di federarsi con l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ef43-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="9ef43-105">L'elenco dei domini bloccati svolgerà la funzione di elenco blocchi (elenco di una serie di voci esplicite da non consentire) e verrà applicato nell'individuazione di domini federati, se questa opzione è abilitata.</span><span class="sxs-lookup"><span data-stu-id="9ef43-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="9ef43-106">Per informazioni dettagliate, vedere [Abilitazione o disabilitazione dell'individuazione dei partner federativi in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span><span class="sxs-lookup"><span data-stu-id="9ef43-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="9ef43-p102">Impedire a uno o più domini esterni di connettersi all'organizzazione. A tale scopo, aggiungere il dominio all'elenco dei domini bloccati.</span><span class="sxs-lookup"><span data-stu-id="9ef43-p102">Block one or more external domains from connecting to your organization. To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="9ef43-109">Per aggiungere un dominio esterno all'elenco dei domini bloccati</span><span class="sxs-lookup"><span data-stu-id="9ef43-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="9ef43-110">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9ef43-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9ef43-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ef43-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9ef43-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9ef43-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9ef43-113">Nella barra di spostamento sinistra fare clic su **Accesso utente esterno**.</span><span class="sxs-lookup"><span data-stu-id="9ef43-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="9ef43-114">Fare clic su **Domini federati**, su **Nuovo** e quindi su **Dominio bloccato**.</span><span class="sxs-lookup"><span data-stu-id="9ef43-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="9ef43-115">In **Nuovi domini federati** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ef43-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="9ef43-116">In **Nome di dominio (o FQDN)** digitare il nome del dominio del partner federato che si desidera bloccare.</span><span class="sxs-lookup"><span data-stu-id="9ef43-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9ef43-117">Il nome può essere costituito da un massimo di 256 caratteri.</span><span class="sxs-lookup"><span data-stu-id="9ef43-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="9ef43-p104">La ricerca in base al nome di dominio del partner federato si basa sulla corrispondenza del suffisso. Se ad esempio si digita <STRONG>contoso.com</STRONG>, la ricerca restituirà anche il dominio <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9ef43-p104">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="9ef43-120">Un dominio di partner federato non può essere contemporaneamente bloccato e consentito.</span><span class="sxs-lookup"><span data-stu-id="9ef43-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="9ef43-121">Lync Server 2013 impedisce l'avvenuto verificarsi in modo da non dover sincronizzare gli elenchi.</span><span class="sxs-lookup"><span data-stu-id="9ef43-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="9ef43-122">(Facoltativo) In **Commento** digitare le informazioni che si desidera condividere con gli altri amministratori di sistema su questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="9ef43-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="9ef43-123">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="9ef43-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="9ef43-124">Ripetere i passaggi da 4 a 6 per ogni partner federato che si desidera bloccare.</span><span class="sxs-lookup"><span data-stu-id="9ef43-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="9ef43-125">Per consentire l'accesso degli utenti federati, è inoltre necessario abilitare il supporto per l'accesso degli utenti federati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ef43-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="9ef43-126">Per ulteriori informazioni, vedere [Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="9ef43-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="9ef43-127">È inoltre necessario configurare e applicare il criterio agli utenti per i quali si desidera consentire la collaborazione con gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="9ef43-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="9ef43-128">Per ulteriori informazioni, vedere [Configure policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="9ef43-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

