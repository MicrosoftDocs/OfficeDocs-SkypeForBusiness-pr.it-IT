---
title: "Lync Server 2013: configurazione dei criteri globali per l'archiviazione"
description: "Lync Server 2013: configurazione dei criteri globali per l'archiviazione."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8f8125f458c4269626e0b1c929f2acb1a8de0b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556862"
---
# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a><span data-ttu-id="bf150-103">Configurazione dei criteri globali per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf150-103">Configuring the global policy for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf150-104">_**Ultimo argomento modificato:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="bf150-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="bf150-105">Quando si distribuisce i Front End Server, Lync Server crea un criterio globale per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="bf150-105">When you deploy your Front End Servers, Lync Server creates a global policy for Archiving.</span></span> <span data-ttu-id="bf150-106">Per impostazione predefinita, nei criteri globali l'archiviazione è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="bf150-106">By default, Archiving is disabled in the global policy.</span></span> <span data-ttu-id="bf150-107">Il criterio globale determina se l'archiviazione è abilitata per le comunicazioni interne ed esterne per l'intera distribuzione, a meno che non si configurano i criteri di sito o utente, che sostituiscono il criterio globale, o se si utilizza l'integrazione di Microsoft Exchange per alcuni o tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="bf150-107">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="bf150-108">Se si utilizza l'integrazione di Microsoft Exchange, il criterio globale non si applica a tutti gli utenti ospitati in Exchange 2013 e le cassette postali vengono inserite In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="bf150-108">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange 2013 and have the mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="bf150-109">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, sito e utente, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations Documentation.</span><span class="sxs-lookup"><span data-stu-id="bf150-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf150-110">Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange In-Place conservazione determinano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le relative cassette postali vengono inserite In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="bf150-110">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="bf150-111">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bf150-111">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="bf150-112">Specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="bf150-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="bf150-113">Per ulteriori informazioni, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bf150-113">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a><span data-ttu-id="bf150-114">Per configurare i criteri globali per l'archiviazione usando database di archiviazione di Lync Server</span><span class="sxs-lookup"><span data-stu-id="bf150-114">To configure the global policy for archiving when using Lync Server Archiving databases</span></span>

1.  <span data-ttu-id="bf150-115">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="bf150-115">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bf150-116">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf150-116">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="bf150-117">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server 2013, vedere [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bf150-117">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bf150-118">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="bf150-118">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="bf150-119">Nella pagina **Criteri di archiviazione**fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="bf150-119">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="bf150-120">In **Modifica Criteri di archiviazione - Globale** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf150-120">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="bf150-121">In **Nome**, se non si vuole usare il nome predefinito Globale, specificare un nuovo nome per i criteri globali.</span><span class="sxs-lookup"><span data-stu-id="bf150-121">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span>
    
      - <span data-ttu-id="bf150-122">In **Descrizione** immettere le informazioni sui criteri, ad esempio "Criteri globali per *nomeDivisione*".</span><span class="sxs-lookup"><span data-stu-id="bf150-122">In **Description**, provide information about what the policy is (for example, Global policy for *divisionName*).</span></span>
    
      - <span data-ttu-id="bf150-123">Per controllare l'archiviazione delle comunicazioni interne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o sito, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.</span><span class="sxs-lookup"><span data-stu-id="bf150-123">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="bf150-124">Per controllare l'archiviazione delle comunicazioni esterne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o di sito, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="bf150-124">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="bf150-125">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="bf150-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

