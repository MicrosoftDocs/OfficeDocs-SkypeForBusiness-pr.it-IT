---
title: Creazione e configurazione di criteri utente per l'archiviazione in Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3adccda55d1ae033acf52d64b093e73fe81dad10
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="fe52d-102">Creazione e configurazione di criteri utente per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe52d-102">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe52d-103">_**Argomento Ultima modifica:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="fe52d-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="fe52d-104">Per abilitare o disabilitare l'archiviazione per utenti specifici ospitati in Lync Server, è necessario prima di tutto creare un criterio utente e quindi applicare il criterio a uno o più utenti o gruppi di utente.</span><span class="sxs-lookup"><span data-stu-id="fe52d-104">To enable or disable Archiving for specific users homed on Lync Server, you must first create a user policy and then apply the policy to one or more users or user groups.</span></span> <span data-ttu-id="fe52d-105">Per informazioni dettagliate sull'applicazione di criteri utente a utenti e gruppi utente specifici, vedere [applicazione di un criterio di archiviazione di Lync Server a un utente in Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fe52d-105">For details about applying user policies to specific users and user groups, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

<span data-ttu-id="fe52d-106">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="fe52d-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, in the Deployment documentation, or in the Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fe52d-107">Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le cassette postali vengono messe sul posto.</span><span class="sxs-lookup"><span data-stu-id="fe52d-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="fe52d-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurazione dei criteri per l'archiviazione in Lync server 2013 quando si usa l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fe52d-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="fe52d-109">Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="fe52d-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="fe52d-110">Per informazioni dettagliate, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fe52d-110">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a><span data-ttu-id="fe52d-111">Per configurare un criterio di archiviazione per gli utenti ospitati in Lync Server</span><span class="sxs-lookup"><span data-stu-id="fe52d-111">To configure an archiving policy for users homed on Lync Server</span></span>

1.  <span data-ttu-id="fe52d-112">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="fe52d-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fe52d-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe52d-113">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="fe52d-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server 2013, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fe52d-114">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fe52d-115">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="fe52d-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="fe52d-116">Fare clic su **Nuovo** e quindi su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="fe52d-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="fe52d-117">In **nuovi criteri di archiviazione**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe52d-117">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="fe52d-118">In **nome**specificare il nome per il criterio utente.</span><span class="sxs-lookup"><span data-stu-id="fe52d-118">In **Name**, specify the name for the user policy.</span></span>
    
      - <span data-ttu-id="fe52d-119">In **Descrizione**, fornisci informazioni sui criteri utente (ad esempio, criteri utente per il reparto legale).</span><span class="sxs-lookup"><span data-stu-id="fe52d-119">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
      - <span data-ttu-id="fe52d-120">Per controllare l'archiviazione delle comunicazioni interne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .</span><span class="sxs-lookup"><span data-stu-id="fe52d-120">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="fe52d-121">Per controllare l'archiviazione delle comunicazioni esterne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .</span><span class="sxs-lookup"><span data-stu-id="fe52d-121">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="fe52d-122">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="fe52d-122">Click **Commit**.</span></span>

<span data-ttu-id="fe52d-123">Un criterio utente si applica solo agli utenti a cui si assegnano i criteri.</span><span class="sxs-lookup"><span data-stu-id="fe52d-123">A user policy applies only to users to whom you assign the policy.</span></span> <span data-ttu-id="fe52d-124">Per informazioni dettagliate sull'applicazione di un criterio utente a utenti specifici, vedere [applicazione di un criterio di archiviazione di Lync Server a un utente in Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fe52d-124">For details about applying a user policy to specific users, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

