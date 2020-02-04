---
title: "Lync Server 2013: configurazione dei criteri globali per l'archiviazione"
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
ms.openlocfilehash: c14cbb69ce620498e1d804483f97c47da37e8522
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a><span data-ttu-id="12794-102">Configurazione dei criteri globali per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12794-102">Configuring the global policy for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12794-103">_**Argomento Ultima modifica:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="12794-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="12794-104">Quando si distribuiscono i server front-end, Lync Server crea un criterio globale per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="12794-104">When you deploy your Front End Servers, Lync Server creates a global policy for Archiving.</span></span> <span data-ttu-id="12794-105">Per impostazione predefinita, l'archiviazione è disabilitata nel criterio globale.</span><span class="sxs-lookup"><span data-stu-id="12794-105">By default, Archiving is disabled in the global policy.</span></span> <span data-ttu-id="12794-106">Il criterio globale controlla se l'archiviazione è abilitata per le comunicazioni interne ed esterne per l'intera distribuzione, a meno che non vengano configurati i criteri del sito o degli utenti, che eseguono l'override del criterio globale o se si usa l'integrazione di Microsoft Exchange per alcuni o tutti Gli utenti.</span><span class="sxs-lookup"><span data-stu-id="12794-106">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="12794-107">Se si usa l'integrazione di Microsoft Exchange, il criterio globale non si applica agli utenti ospitati in Exchange 2013 e le cassette postali vengono inserite in blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="12794-107">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange 2013 and have the mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="12794-108">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere funzionamento [dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) documentazione di pianificazione, documentazione di distribuzione o documentazione operativa.</span><span class="sxs-lookup"><span data-stu-id="12794-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="12794-109">Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti che si trovano in Exchange 2013 e le cassette postali sono inserite in blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="12794-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="12794-110">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurazione dei criteri per l'archiviazione in Lync server 2013 quando si usa l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="12794-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="12794-111">Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="12794-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="12794-112">Per informazioni dettagliate, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="12794-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a><span data-ttu-id="12794-113">Per configurare i criteri globali per l'archiviazione quando si usano i database di archiviazione di Lync Server</span><span class="sxs-lookup"><span data-stu-id="12794-113">To configure the global policy for archiving when using Lync Server Archiving databases</span></span>

1.  <span data-ttu-id="12794-114">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="12794-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="12794-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12794-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="12794-116">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server 2013, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12794-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="12794-117">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="12794-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="12794-118">Nella pagina **criteri di archiviazione** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="12794-118">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="12794-119">In **modifica criteri di archiviazione-globale**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="12794-119">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="12794-120">In **nome**, se non si vuole usare il nome predefinito globale, specificare un nuovo nome per il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="12794-120">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span>
    
      - <span data-ttu-id="12794-121">In **Descrizione**, fornisci informazioni sui criteri, ad esempio criteri globali per *divisioni*.</span><span class="sxs-lookup"><span data-stu-id="12794-121">In **Description**, provide information about what the policy is (for example, Global policy for *divisionName*).</span></span>
    
      - <span data-ttu-id="12794-122">Per controllare l'archiviazione delle comunicazioni interne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .</span><span class="sxs-lookup"><span data-stu-id="12794-122">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="12794-123">Per controllare l'archiviazione delle comunicazioni esterne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .</span><span class="sxs-lookup"><span data-stu-id="12794-123">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="12794-124">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="12794-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

