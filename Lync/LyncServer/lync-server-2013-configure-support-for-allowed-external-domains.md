---
title: 'Lync Server 2013: Configurare il supporto per i domini esterni consentiti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfab1a41f39d975d2920bdf97ea601618277f35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="93bc7-102">Configurare il supporto per i domini esterni consentiti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93bc7-102">Configure support for allowed external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93bc7-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="93bc7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="93bc7-104">Se è stato configurato il supporto per i partner federati, è possibile gestire i domini specifici che possono essere federati con l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="93bc7-104">If you have configured support for federated partners, you can manage which specific domains can federate with your organization.</span></span> <span data-ttu-id="93bc7-105">Si configurano uno o più domini esterni specifici come consentiti domini federati.</span><span class="sxs-lookup"><span data-stu-id="93bc7-105">You configure one or more specific external domains as allowed federated domains.</span></span> <span data-ttu-id="93bc7-106">A questo scopo, Aggiungi ogni dominio all'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="93bc7-106">To do this, add each domain to the list of allowed domains.</span></span> <span data-ttu-id="93bc7-107">Anche se l'individuazione dei partner è abilitata per l'organizzazione, eseguire questa operazione se il dominio è un partner federato che potrebbe essere necessario comunicare con più di 1.000 degli utenti o potrebbe essere necessario inviare più di 20 messaggi al secondo.</span><span class="sxs-lookup"><span data-stu-id="93bc7-107">Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second.</span></span> <span data-ttu-id="93bc7-108">Se l'individuazione dei partner non è abilitata per l'organizzazione, solo gli utenti di domini esterni aggiunti all'elenco dei domini consentiti possono partecipare alla messaggistica istantanea e alle conferenze con gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="93bc7-108">If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization.</span></span> <span data-ttu-id="93bc7-109">Se si vuole limitare l'accesso a un dominio federato a un server specifico che usa il servizio Access Edge del partner federato, è possibile specificare il nome di dominio del server che usa il servizio Access Edge per ogni dominio nell'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="93bc7-109">If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93bc7-110">Questa procedura descrive come configurare il supporto per specifici domini, ma l'implementazione del supporto per gli utenti federati richiede anche l'abilitazione del supporto per gli utenti federati per l'organizzazione e la configurazione e l'applicazione di criteri per il controllo degli utenti che possono collaborare con gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="93bc7-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="93bc7-111">Per informazioni dettagliate sull'abilitazione del supporto per gli utenti federati, vedere <A href="lync-server-2013-enable-or-disable-remote-user-access.md">abilitare o disabilitare l'accesso da utenti remoti in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="93bc7-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="93bc7-112">Per informazioni dettagliate sulla configurazione dei criteri per il controllo della Federazione, vedere <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configurare i criteri per controllare l'accesso degli utenti federati in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="93bc7-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="93bc7-113">Per aggiungere un dominio esterno all'elenco dei domini consentiti</span><span class="sxs-lookup"><span data-stu-id="93bc7-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="93bc7-114">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="93bc7-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="93bc7-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93bc7-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="93bc7-116">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="93bc7-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="93bc7-117">Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**e quindi su **domini federati**.</span><span class="sxs-lookup"><span data-stu-id="93bc7-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="93bc7-118">Nella pagina **domini federati** fare clic su **nuovo**e quindi su **dominio consentito**.</span><span class="sxs-lookup"><span data-stu-id="93bc7-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="93bc7-119">In **nuovi domini federati**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="93bc7-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="93bc7-120">In **Domain Name (o FQDN)** Digitare il nome del dominio del partner federato.</span><span class="sxs-lookup"><span data-stu-id="93bc7-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="93bc7-121">Questo nome deve essere univoco e non può essere già presente come dominio consentito per il server che ha eseguito il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="93bc7-121">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service.</span></span> <span data-ttu-id="93bc7-122">Il nome non può superare i 256 caratteri di lunghezza.</span><span class="sxs-lookup"><span data-stu-id="93bc7-122">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="93bc7-123">La ricerca nel nome di dominio del partner federativo esegue una corrispondenza con suffisso.</span><span class="sxs-lookup"><span data-stu-id="93bc7-123">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="93bc7-124">Ad esempio, se si digita <STRONG>contoso.com</STRONG>, la ricerca restituirà anche il dominio <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="93bc7-124">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="93bc7-125">Un dominio partner federato non può essere bloccato e consentito simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="93bc7-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="93bc7-126">Lync Server 2013 impedisce che ciò avvenga in modo da non dover sincronizzare gli elenchi.</span><span class="sxs-lookup"><span data-stu-id="93bc7-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="93bc7-127">Se si vuole limitare l'accesso per il dominio federato agli utenti di un server specifico che ha eseguito il servizio Access Edge, in **Access Edge Services (FQDN)** Digitare il nome di dominio completo del server del dominio federato in cui è in uso il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="93bc7-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="93bc7-128">Se si vogliono aggiungere altre informazioni, in **Commento**Digitare le informazioni che si desidera condividere con altri amministratori di sistema su questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="93bc7-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="93bc7-129">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="93bc7-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="93bc7-130">Ripetere i passaggi da 4 a 6 per ogni dominio di partner federato che si vuole consentire.</span><span class="sxs-lookup"><span data-stu-id="93bc7-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="93bc7-131">Per abilitare l'accesso degli utenti federati, devi anche abilitare il supporto per l'accesso degli utenti federati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="93bc7-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="93bc7-132">Per informazioni dettagliate, vedere [abilitare o disabilitare l'accesso remoto agli utenti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="93bc7-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="93bc7-133">Inoltre, è necessario configurare e applicare il criterio agli utenti che si vuole poter collaborare con gli utenti federati.</span><span class="sxs-lookup"><span data-stu-id="93bc7-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="93bc7-134">Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti federati in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="93bc7-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

