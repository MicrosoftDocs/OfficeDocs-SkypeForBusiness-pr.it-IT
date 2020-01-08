---
title: 'Lync Server 2013: Configurare il supporto per i domini esterni bloccati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08191e8600f5e247ba6b4a358557ea3def0a1756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="56585-102">Configurare il supporto per i domini esterni bloccati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56585-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56585-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="56585-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="56585-104">Se è stato configurato il supporto per i partner federati, è possibile gestire i domini che verranno bloccati dalla Federazione con l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="56585-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="56585-105">L'elenco dei domini bloccati fungerà da elenco di blocchi (elenco delle voci esplicite che non devono essere consentite) e verrà applicato nell'individuazione di domini federati, se questa opzione è abilitata.</span><span class="sxs-lookup"><span data-stu-id="56585-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="56585-106">Per informazioni dettagliate, vedere [abilitare o disabilitare l'individuazione dei partner federativi in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span><span class="sxs-lookup"><span data-stu-id="56585-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="56585-107">Bloccare uno o più domini esterni dalla connessione alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="56585-107">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="56585-108">A questo scopo, Aggiungi il dominio all'elenco dei domini bloccati.</span><span class="sxs-lookup"><span data-stu-id="56585-108">To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="56585-109">Per aggiungere un dominio esterno all'elenco dei domini bloccati</span><span class="sxs-lookup"><span data-stu-id="56585-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="56585-110">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="56585-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="56585-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56585-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="56585-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="56585-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="56585-113">Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**.</span><span class="sxs-lookup"><span data-stu-id="56585-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="56585-114">Fare clic su **domini federati**, su **nuovo**e quindi su **dominio bloccato**.</span><span class="sxs-lookup"><span data-stu-id="56585-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="56585-115">In **nuovi domini federati**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="56585-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="56585-116">In **Domain Name (o FQDN)** Digitare il nome del dominio del partner federato che si vuole bloccare.</span><span class="sxs-lookup"><span data-stu-id="56585-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="56585-117">Il nome non può superare i 256 caratteri di lunghezza.</span><span class="sxs-lookup"><span data-stu-id="56585-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="56585-118">La ricerca nel nome di dominio del partner federativo esegue una corrispondenza con suffisso.</span><span class="sxs-lookup"><span data-stu-id="56585-118">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="56585-119">Ad esempio, se si digita <STRONG>contoso.com</STRONG>, la ricerca restituirà anche il dominio <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="56585-119">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="56585-120">Un dominio partner federato non può essere bloccato e consentito simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="56585-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="56585-121">Lync Server 2013 impedisce che ciò avvenga in modo da non dover sincronizzare gli elenchi.</span><span class="sxs-lookup"><span data-stu-id="56585-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="56585-122">Opzionale In **Commento**Digitare le informazioni che si desidera condividere con altri amministratori di sistema su questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="56585-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="56585-123">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="56585-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="56585-124">Ripetere i passaggi da 4 a 6 per ogni partner federato che si vuole bloccare.</span><span class="sxs-lookup"><span data-stu-id="56585-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="56585-125">Per abilitare l'accesso degli utenti federati, devi anche abilitare il supporto per l'accesso degli utenti federati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="56585-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="56585-126">Per informazioni dettagliate, vedere [abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="56585-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="56585-127">Inoltre, è necessario configurare e applicare il criterio agli utenti che si vuole poter collaborare con gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="56585-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="56585-128">Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti federati in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="56585-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

