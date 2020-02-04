---
title: 'Lync Server 2013: applicazione di un criterio di archiviazione di Lync Server a un utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7b82fd0d42aa6a34533f6b5005e15edd2aa5cbd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a><span data-ttu-id="2e989-102">Applicazione di un criterio di archiviazione di Lync Server a un utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e989-102">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e989-103">_**Argomento Ultima modifica:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="2e989-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="2e989-104">Dopo aver creato un criterio utente di Lync Server, è necessario applicarlo a specifici utenti o gruppi utente residenti in Lync Server 2013 prima che possa avere effetto.</span><span class="sxs-lookup"><span data-stu-id="2e989-104">After creating a Lync Server user policy, you must apply it to specific the users or user groups that are homed on Lync Server 2013 before it can take effect.</span></span> <span data-ttu-id="2e989-105">Per informazioni dettagliate sulla creazione di criteri utente per utenti specifici, vedere [creazione e configurazione di criteri utente per l'archiviazione in Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2e989-105">For details about creating user policies for specific users, see [Creating and configuring user policies for Archiving in Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="2e989-106">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla documentazione di distribuzione o alla documentazione operativa.</span><span class="sxs-lookup"><span data-stu-id="2e989-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2e989-107">Per configurare e usare l'archiviazione, è prima necessario distribuire l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2e989-107">In order to configure and use archiving, you must first deploy archiving.</span></span> <span data-ttu-id="2e989-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-archiving.md">distribuzione dell'archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2e989-108">For details, see <A href="lync-server-2013-deploying-archiving.md">Deploying Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="2e989-109">Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le cassette postali vengono messe sul posto.</span><span class="sxs-lookup"><span data-stu-id="2e989-109">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="2e989-110">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurazione dei criteri per l'archiviazione in Lync server 2013 quando si usa l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2e989-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="2e989-111">Devi specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2e989-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="2e989-112">Per informazioni dettagliate, vedere <A href="lync-server-2013-configuring-archiving-options.md">configurazione delle opzioni di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2e989-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a><span data-ttu-id="2e989-113">Per applicare un criterio di archiviazione di Lync Server a un utente</span><span class="sxs-lookup"><span data-stu-id="2e989-113">To apply a Lync Server archiving policy to a user</span></span>

1.  <span data-ttu-id="2e989-114">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="2e989-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2e989-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e989-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="2e989-116">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server 2013, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2e989-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2e989-117">Nella barra di spostamento sinistra fare clic su **utenti**e quindi cercare l'account utente che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="2e989-117">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="2e989-118">Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2e989-118">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2e989-119">In **modifica utenti di Lync Server** in **criteri di archiviazione**Selezionare i criteri utente di archiviazione che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="2e989-119">In **Edit Lync Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2e989-120">Le <STRONG> &lt;impostazioni&gt; automatiche</STRONG> applicano le impostazioni di installazione del server predefinite.</span><span class="sxs-lookup"><span data-stu-id="2e989-120">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="2e989-121">Queste impostazioni vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="2e989-121">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="2e989-122">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="2e989-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

