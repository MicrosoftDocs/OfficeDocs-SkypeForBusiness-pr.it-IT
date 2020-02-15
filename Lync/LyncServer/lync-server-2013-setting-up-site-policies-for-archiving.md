---
title: "Lync Server 2013: impostazione dei criteri del sito per l'archiviazione"
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
ms.openlocfilehash: 2fd9e63ad6aec440c090b4303a32cba37953e1d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="16a84-102">Impostazione dei criteri di sito per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16a84-102">Setting up site policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16a84-103">_**Ultimo argomento modificato:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="16a84-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="16a84-104">È possibile abilitare o disabilitare l'archiviazione per siti specifici creando e configurando un criterio di archiviazione per ognuno di questi siti.</span><span class="sxs-lookup"><span data-stu-id="16a84-104">You can enable or disable Archiving for specific sites by creating and configuring an Archiving policy for each of those sites.</span></span> <span data-ttu-id="16a84-105">Un criterio sito ha la precedenza sui criteri globali, ma i criteri degli utenti eseguono l'override dei criteri sito.</span><span class="sxs-lookup"><span data-stu-id="16a84-105">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="16a84-106">I criteri di archiviazione si applicano solo se non si utilizza l'integrazione di Microsoft Exchange o, se si utilizza l'integrazione di Microsoft Exchange, ma alcuni utenti non sono ospitati in Exchange 2013 e le relative cassette postali vengono conservate sul posto.</span><span class="sxs-lookup"><span data-stu-id="16a84-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="16a84-107">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, sito e utente, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations Documentation.</span><span class="sxs-lookup"><span data-stu-id="16a84-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="16a84-108">Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di conservazione sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti che si trovano in Exchange 2013 e le relative cassette postali vengono conservate sul posto.</span><span class="sxs-lookup"><span data-stu-id="16a84-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="16a84-109">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="16a84-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="16a84-110">È necessario specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione di comunicazioni interne o esterne nei criteri di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="16a84-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="16a84-111">Per ulteriori informazioni, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="16a84-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a><span data-ttu-id="16a84-112">Per creare criteri di archiviazione per un sito</span><span class="sxs-lookup"><span data-stu-id="16a84-112">To create an archiving policy for a site</span></span>

1.  <span data-ttu-id="16a84-113">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="16a84-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16a84-114">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="16a84-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span>

3.  <span data-ttu-id="16a84-115">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="16a84-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="16a84-116">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, sito e utente, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations Documentation.</span><span class="sxs-lookup"><span data-stu-id="16a84-116">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

4.  <span data-ttu-id="16a84-117">Fare clic su **Nuovo** e quindi su **Criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="16a84-117">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="16a84-118">In **Seleziona un sito**fare clic sul sito a cui devono essere applicati i criteri.</span><span class="sxs-lookup"><span data-stu-id="16a84-118">In **Select a site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="16a84-119">In **Crea nuovi criteri di archiviazione** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="16a84-119">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="16a84-120">In **nome**specificare il nome del criterio sito.</span><span class="sxs-lookup"><span data-stu-id="16a84-120">In **Name**, specify the name for the site policy.</span></span>
    
      - <span data-ttu-id="16a84-121">In **Descrizione**fornire informazioni sui criteri di sito, ad esempio criteri sito per Redmond.</span><span class="sxs-lookup"><span data-stu-id="16a84-121">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
      - <span data-ttu-id="16a84-122">Per controllare l'archiviazione delle comunicazioni interne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .</span><span class="sxs-lookup"><span data-stu-id="16a84-122">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="16a84-123">Per controllare l'archiviazione delle comunicazioni esterne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .</span><span class="sxs-lookup"><span data-stu-id="16a84-123">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>

7.  <span data-ttu-id="16a84-124">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="16a84-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

