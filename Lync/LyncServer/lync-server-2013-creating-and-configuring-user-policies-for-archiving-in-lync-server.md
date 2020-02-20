---
title: Creazione e configurazione dei criteri utente per l'archiviazione in Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8c3c83f06f7bc01d81acc18cb0c9cedb4b0ef7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="aabc8-102">Creazione e configurazione dei criteri utente per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aabc8-102">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aabc8-103">_**Ultimo argomento modificato:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="aabc8-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="aabc8-104">Per abilitare o disabilitare l'archiviazione per utenti specifici ospitati in Lync Server, è necessario innanzitutto creare un criterio utente e quindi applicare il criterio a uno o più utenti o gruppi di utente.</span><span class="sxs-lookup"><span data-stu-id="aabc8-104">To enable or disable Archiving for specific users homed on Lync Server, you must first create a user policy and then apply the policy to one or more users or user groups.</span></span> <span data-ttu-id="aabc8-105">Per informazioni dettagliate sull'applicazione di criteri utente a determinati utenti e gruppi di utenti, vedere [applicazione di un criterio di archiviazione di Lync Server a un utente in Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="aabc8-105">For details about applying user policies to specific users and user groups, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

<span data-ttu-id="aabc8-106">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, sito e utente, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="aabc8-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, in the Deployment documentation, or in the Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="aabc8-107">Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di conservazione sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le relative cassette postali vengono conservate sul posto.</span><span class="sxs-lookup"><span data-stu-id="aabc8-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="aabc8-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="aabc8-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="aabc8-109">Specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="aabc8-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="aabc8-110">Per ulteriori informazioni, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="aabc8-110">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a><span data-ttu-id="aabc8-111">Per configurare un criterio di archiviazione per gli utenti ospitati in Lync Server</span><span class="sxs-lookup"><span data-stu-id="aabc8-111">To configure an archiving policy for users homed on Lync Server</span></span>

1.  <span data-ttu-id="aabc8-112">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="aabc8-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aabc8-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aabc8-113">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="aabc8-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server 2013, vedere [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aabc8-114">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aabc8-115">Nella barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="aabc8-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="aabc8-116">Fare clic su **Nuovo** e quindi su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="aabc8-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="aabc8-117">In **Nuovi criteri di archiviazione** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aabc8-117">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="aabc8-118">In **Nome** specificare un nome per i criteri utente.</span><span class="sxs-lookup"><span data-stu-id="aabc8-118">In **Name**, specify the name for the user policy.</span></span>
    
      - <span data-ttu-id="aabc8-119">In **Descrizione** immettere informazioni sugli scopi dei criteri utente, ad esempio "Criteri utente per il reparto legale".</span><span class="sxs-lookup"><span data-stu-id="aabc8-119">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
      - <span data-ttu-id="aabc8-120">Per controllare l'archiviazione delle comunicazioni interne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.</span><span class="sxs-lookup"><span data-stu-id="aabc8-120">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="aabc8-121">Per controllare l'archiviazione delle comunicazioni esterne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="aabc8-121">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="aabc8-122">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="aabc8-122">Click **Commit**.</span></span>

<span data-ttu-id="aabc8-123">I criteri utente si applicano solo agli utenti a cui vengono assegnati.</span><span class="sxs-lookup"><span data-stu-id="aabc8-123">A user policy applies only to users to whom you assign the policy.</span></span> <span data-ttu-id="aabc8-124">Per informazioni dettagliate sull'applicazione di un criterio utente a utenti specifici, vedere [applicazione di un criterio di archiviazione di Lync Server a un utente in Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="aabc8-124">For details about applying a user policy to specific users, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

