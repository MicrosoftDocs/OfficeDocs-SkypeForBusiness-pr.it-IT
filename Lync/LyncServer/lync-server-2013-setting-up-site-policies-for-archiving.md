---
title: "Lync Server 2013: configurazione dei criteri del sito per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ebb1efdfff09f51b13ada9d1e2aa571ab88c888
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="b3e96-102">Configurazione dei criteri del sito per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3e96-102">Setting up site policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3e96-103">_**Argomento Ultima modifica:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="b3e96-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="b3e96-104">È possibile abilitare o disabilitare l'archiviazione per siti specifici creando e configurando un criterio di archiviazione per ognuno di questi siti.</span><span class="sxs-lookup"><span data-stu-id="b3e96-104">You can enable or disable Archiving for specific sites by creating and configuring an Archiving policy for each of those sites.</span></span> <span data-ttu-id="b3e96-105">Un criterio di sito sostituisce il criterio globale, ma i criteri utente sostituiscono i criteri del sito.</span><span class="sxs-lookup"><span data-stu-id="b3e96-105">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="b3e96-106">I criteri di archiviazione si applicano solo se non si usa l'integrazione di Microsoft Exchange o, se si usa l'integrazione di Microsoft Exchange, ma alcuni utenti non sono residenti in Exchange 2013 e le cassette postali vengono inserite nel blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="b3e96-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="b3e96-107">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere funzionamento [dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) documentazione di pianificazione, documentazione di distribuzione o documentazione operativa.</span><span class="sxs-lookup"><span data-stu-id="b3e96-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3e96-108">Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti che si trovano in Exchange 2013 e le cassette postali sono inserite in blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="b3e96-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="b3e96-109">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurazione dei criteri per l'archiviazione in Lync server 2013 quando si usa l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b3e96-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="b3e96-110">Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione di comunicazioni interne o esterne nei criteri di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b3e96-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="b3e96-111">Per informazioni dettagliate, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b3e96-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a><span data-ttu-id="b3e96-112">Per creare criteri di archiviazione per un sito</span><span class="sxs-lookup"><span data-stu-id="b3e96-112">To create an archiving policy for a site</span></span>

1.  <span data-ttu-id="b3e96-113">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b3e96-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b3e96-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3e96-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span>

3.  <span data-ttu-id="b3e96-115">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="b3e96-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="b3e96-116">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere funzionamento [dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) documentazione di pianificazione, documentazione di distribuzione o documentazione operativa.</span><span class="sxs-lookup"><span data-stu-id="b3e96-116">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

4.  <span data-ttu-id="b3e96-117">Fare clic su **Nuovo** e quindi su **Criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="b3e96-117">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="b3e96-118">In **Seleziona un sito**fare clic sul sito a cui applicare il criterio.</span><span class="sxs-lookup"><span data-stu-id="b3e96-118">In **Select a site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="b3e96-119">In **nuovi criteri di archiviazione**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3e96-119">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="b3e96-120">In **nome**specificare il nome per il criterio del sito.</span><span class="sxs-lookup"><span data-stu-id="b3e96-120">In **Name**, specify the name for the site policy.</span></span>
    
      - <span data-ttu-id="b3e96-121">In **Descrizione**immettere informazioni sui criteri del sito, ad esempio i criteri del sito per Redmond.</span><span class="sxs-lookup"><span data-stu-id="b3e96-121">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
      - <span data-ttu-id="b3e96-122">Per controllare l'archiviazione delle comunicazioni interne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .</span><span class="sxs-lookup"><span data-stu-id="b3e96-122">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="b3e96-123">Per controllare l'archiviazione delle comunicazioni esterne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .</span><span class="sxs-lookup"><span data-stu-id="b3e96-123">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>

7.  <span data-ttu-id="b3e96-124">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="b3e96-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

