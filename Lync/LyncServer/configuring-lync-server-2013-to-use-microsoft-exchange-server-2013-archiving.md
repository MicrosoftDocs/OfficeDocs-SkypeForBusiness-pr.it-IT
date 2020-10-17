---
title: Configurazione di Lync Server 2013 per l'utilizzo dell'archiviazione di Microsoft Exchange Server 2013
description: Configurazione di Lync Server 2013 per l'utilizzo dell'archiviazione di Microsoft Exchange Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80b0673071ec38246e366fe7556b39bd495895d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542942"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a><span data-ttu-id="dc7e9-103">Configurazione di Microsoft Lync Server 2013 per l'utilizzo dell'archiviazione di Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc7e9-103">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc7e9-104">_**Ultimo argomento modificato:** 2014-06-24_</span><span class="sxs-lookup"><span data-stu-id="dc7e9-104">_**Topic Last Modified:** 2014-06-24_</span></span>

<span data-ttu-id="dc7e9-105">Microsoft Lync Server 2013 fornisce agli amministratori la possibilità di archiviare la messaggistica istantanea e le trascrizioni di Web Conferencing nella cassetta postale di Microsoft Exchange Server 2013 di un utente anziché in un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-105">Microsoft Lync Server 2013 gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Microsoft Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="dc7e9-106">Se si abilita questa opzione, le trascrizioni vengono scritte nella cartella Eliminazioni della cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-106">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="dc7e9-107">Questa cartella è nascosta e si trova nella cartella Elementi ripristinabili.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-107">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="dc7e9-108">Anche se questa cartella non è visibile agli utenti finali, la cartella viene indicizzata dal motore di ricerca di Exchange e può essere individuata utilizzando la ricerca di cassette postali di Exchange e/o Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-108">Although this folder is not visible to end-users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="dc7e9-109">Poiché le informazioni vengono memorizzate nella stessa cartella utilizzata dalla funzionalità di archiviazione In-Place di Exchange (responsabile della posta elettronica e di altre comunicazioni di Exchange), gli amministratori possono utilizzare un unico strumento per cercare tutte le comunicazioni elettroniche archiviate per un utente.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-109">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dc7e9-110">Per disabilitare completamente l'archiviazione della conversazione Lync, è inoltre necessario disabilitare la cronologia delle conversazioni di Lync.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-110">To completely disable archiving of Lync conversation, you must also disable Lync conversation history.</span></span> <span data-ttu-id="dc7e9-111">Per ulteriori informazioni, vedere i seguenti argomenti: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-111">For more information, see the following topics: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>, and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span></span>



</div>

<span data-ttu-id="dc7e9-112">Per archiviare le trascrizioni in Exchange 2013, è necessario iniziare configurando l'autenticazione da server a server tra i due server.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-112">In order to archive transcripts to Exchange 2013 you must begin by configuring server-to-server authentication between the two servers.</span></span> <span data-ttu-id="dc7e9-113">Dopo aver effettuato l'autenticazione da server a server, è possibile eseguire le attività seguenti in Microsoft Lync Server 2013 (si noti che, a seconda dell'installazione e della configurazione, potrebbe non essere necessario completare tutte queste attività):</span><span class="sxs-lookup"><span data-stu-id="dc7e9-113">After server-to-server authentication is in place you can then carry out the following tasks in Microsoft Lync Server 2013 (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1.  <span data-ttu-id="dc7e9-114">Abilitare l'archiviazione di Exchange modificando le impostazioni di configurazione dell'archiviazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-114">Enable Exchange archiving by modifying your Lync Server archiving configuration settings.</span></span> <span data-ttu-id="dc7e9-115">Questo passaggio è obbligatorio per tutte le distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-115">This step is required for all deployments.</span></span>

2.  <span data-ttu-id="dc7e9-116">Abilitare l'archiviazione per le comunicazioni interne e/o esterne per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-116">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="dc7e9-117">Questo passaggio è obbligatorio per tutte le distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-117">This step is required for all deployments.</span></span>

3.  <span data-ttu-id="dc7e9-118">Configurare la proprietà ExchangeArchivingPolicy per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-118">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="dc7e9-119">Questo passaggio è necessario solo in Lync Server e Exchange si trovano in foreste diverse.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-119">This step is only required in Lync Server and Exchange are located in different forests.</span></span>

<div>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="dc7e9-120">Passaggio 1: abilitazione dell'archiviazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="dc7e9-120">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="dc7e9-121">L'archiviazione in Lync Server viene gestita principalmente utilizzando le impostazioni di configurazione dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-121">Archiving in Lync Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="dc7e9-122">Quando si installa Lync Server 2013, viene automaticamente assegnata una singola raccolta globale di queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-122">When you install Lync Server 2013 you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="dc7e9-123">Gli amministratori possono facoltativamente creare nuove raccolte di impostazioni di archiviazione nell'ambito del sito. Per impostazione predefinita, l'archiviazione non è abilitata nelle impostazioni globali e non è abilitata per l'archiviazione di Exchange in queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-123">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="dc7e9-124">Per poter utilizzare gli amministratori di archiviazione di Exchange, è necessario configurare le proprietà EnableArchiving e EnableExchangeArchiving nelle impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-124">In order to use Exchange archiving administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="dc7e9-125">La proprietà EnableArchiving può essere impostata su uno di tre possibili valori:</span><span class="sxs-lookup"><span data-stu-id="dc7e9-125">The EnableArchiving property can be set to one of three possible values:</span></span>

  - <span data-ttu-id="dc7e9-126">**Nessuna**.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-126">**None**.</span></span> <span data-ttu-id="dc7e9-127">L'archiviazione è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-127">Archiving is disabled.</span></span> <span data-ttu-id="dc7e9-128">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-128">This is the default value.</span></span> <span data-ttu-id="dc7e9-129">Se EnableArchiving è impostato su None, nel database di archiviazione di Lync Server o in Exchange 2013 non verrà archiviato nulla.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-129">If EnableArchiving is set to None then nothing will be archived in either your Lync Server archiving database or in Exchange 2013.</span></span>

  - <span data-ttu-id="dc7e9-130">**Imsolo**.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-130">**ImOnly**.</span></span> <span data-ttu-id="dc7e9-131">Vengono archiviate solo le trascrizioni dei messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-131">Only instant message transcripts are archived.</span></span> <span data-ttu-id="dc7e9-132">Se è abilitata l'archiviazione di Exchange, queste trascrizioni verranno archiviate in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-132">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="dc7e9-133">Se l'archiviazione di Exchange è disabilitata, queste trascrizioni verranno archiviate in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-133">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

  - <span data-ttu-id="dc7e9-134">**ImAndWebConf**.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-134">**ImAndWebConf**.</span></span> <span data-ttu-id="dc7e9-135">Vengono archiviate sia le trascrizioni dei messaggi istantanei sia quelle di Web Conferencing.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-135">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="dc7e9-136">Se è abilitata l'archiviazione di Exchange, queste trascrizioni verranno archiviate in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-136">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="dc7e9-137">Se l'archiviazione di Exchange è disabilitata, queste trascrizioni verranno archiviate in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-137">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

<span data-ttu-id="dc7e9-138">La proprietà EnableExchangeArchiving è un valore booleano: impostare EnableExchangeArchiving su true ($True) per abilitare l'archiviazione di Exchange o impostare EnableExchangeArchiving su false ($False) per disabilitare l'archiviazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-138">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="dc7e9-139">Ad esempio, questo comando consente di abilitare l'archiviazione delle trascrizioni di messaggistica istantanea e di abilitare anche l'archiviazione di Exchange:</span><span class="sxs-lookup"><span data-stu-id="dc7e9-139">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

<span data-ttu-id="dc7e9-140">Per disabilitare l'archiviazione di Exchange, utilizzare un comando simile al seguente, che consente l'archiviazione di messaggistica istantanea ma disabilita l'archiviazione in Exchange (in altre parole, le trascrizioni verranno archiviate in Lync Server):</span><span class="sxs-lookup"><span data-stu-id="dc7e9-140">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Lync Server):</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> <span data-ttu-id="dc7e9-141">Se la proprietà EnableArchiving è impostata su None, Lync Server non archivierà affatto la messaggistica istantanea e le trascrizioni di Web Conferencing.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-141">If the EnableArchiving property is set to None then Lync Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="dc7e9-142">In tal caso, il server ignorerà semplicemente il valore configurato per EnableExchangeArchiving.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-142">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>



</div>

<span data-ttu-id="dc7e9-143">L'archiviazione di Exchange può anche essere abilitata (o disattivata) utilizzando il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-143">Exchange archiving can also be enabled (or disabled) by using the Lync Server Control Panel.</span></span> <span data-ttu-id="dc7e9-144">A tale scopo, completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="dc7e9-144">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="dc7e9-145">Nel Pannello di controllo fare clic su **Monitoraggio e archiviazione** e quindi su **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-145">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2.  <span data-ttu-id="dc7e9-146">Nella scheda **Configurazione archiviazione** fare doppio clic sulla raccolta delle impostazioni di archiviazione da modificare (ad esempio la raccolta **Globale**).</span><span class="sxs-lookup"><span data-stu-id="dc7e9-146">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3.  <span data-ttu-id="dc7e9-147">Nel riquadro **Modifica impostazione di archiviazione** fare clic sull'elenco a discesa **Impostazione di archiviazione** e selezionare **Archivia sessioni di messaggistica istantanea** per archiviare solo le sessioni di messaggistica istantanea o su **Archivia sessioni di messaggistica istantanea e Web Conferencing** per archiviare sia le sessioni di messaggistica istantanea sia quelle di Web Conferencing.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-147">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4.  <span data-ttu-id="dc7e9-148">Dopo aver scelto gli elementi da archiviare, selezionare la casella di controllo **integrazione di Exchange Server** per abilitare l'archiviazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-148">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="dc7e9-149">Per disabilitare l'archiviazione di Exchange, deselezionare questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-149">To disable Exchange archiving, clear this checkbox.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dc7e9-150">La casella di controllo <STRONG>Integrazione Exchange Server</STRONG> non sarà disponibile se <STRONG>Impostazione di archiviazione</STRONG> è impostata su <STRONG>Disabilita archiviazione</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-150">The <STRONG>Exchange Server integration</STRONG> checkbox will not be available if the <STRONG>Archiving setting</STRONG> is set to <STRONG>Disable archiving</STRONG>.</span></span> <span data-ttu-id="dc7e9-151">È innanzitutto necessario abilitare l'archiviazione e quindi abilitare l'archiviazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-151">You must enable archiving first and then enable Exchange archiving.</span></span>



</div>

<span data-ttu-id="dc7e9-152">Se Lync Server 2013 e Exchange 2013 si trovano nella stessa foresta, l'archiviazione per singoli utenti (o almeno per gli utenti che dispongono di account di posta elettronica su Exchange 2013) viene gestita utilizzando i criteri di conservazione In-Place di Exchange.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-152">If Lync Server 2013 and Exchange 2013 are located in the same forest then archiving for individual users (or at least for users who have email accounts on Exchange 2013) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="dc7e9-153">Se si dispone di utenti ospitati in una versione precedente di Exchange, l'archiviazione per tali utenti verrà gestita utilizzando i criteri di archiviazione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-153">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Lync Server archiving policies.</span></span> <span data-ttu-id="dc7e9-154">Si noti che solo gli utenti con account su Exchange 2013 possono eseguire l'archiviazione delle trascrizioni di Lync in Exchange.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-154">Note that only users with accounts on Exchange 2013 can have their Lync transcripts archived to Exchange.</span></span>

<span data-ttu-id="dc7e9-155">Se Lync Server 2013 e Exchange 2013 sono ubicati in foreste diverse, l'archiviazione per singoli utenti viene gestita configurando la proprietà ExchangeArchivingPolicy per ogni singolo account utente.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-155">If Lync Server 2013 and Exchange 2013 are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="dc7e9-156">Per ulteriori informazioni, vedere il passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-156">See Step 3 for more information.</span></span>

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="dc7e9-157">Passaggio 2: Abilitazione dell'archiviazione delle comunicazioni interne e/o esterne</span><span class="sxs-lookup"><span data-stu-id="dc7e9-157">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="dc7e9-158">Dopo aver abilitato l'archiviazione (e l'archiviazione di Exchange), è necessario modificare i criteri di archiviazione corretti per garantire che le sessioni degli utenti vengano effettivamente archiviate.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-158">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="dc7e9-159">Si noti che l'abilitazione dell'archiviazione (passaggio 1) non consente a Lync Server di avviare l'archiviazione delle trascrizioni di messaggistica istantanea e Web Conferencing.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-159">Note that simply enabling archiving (Step 1) does not cause Lync Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="dc7e9-160">È invece necessario utilizzare i criteri di archiviazione per abilitare l'archiviazione interna e/o esterna.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-160">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="dc7e9-161">Quando si installa Lync Server 2013, viene installato anche un singolo criterio di archiviazione globale contenente due proprietà:</span><span class="sxs-lookup"><span data-stu-id="dc7e9-161">When you install Lync Server 2013 you also install a single, global archiving policy that contains two properties:</span></span>

  - <span data-ttu-id="dc7e9-p119">**ArchiveInternal**. Se impostata su True ($True), indica che verranno archiviate le sessioni di comunicazione interna che interessano solo gli utenti con account Active Directory attivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

  - <span data-ttu-id="dc7e9-p120">**ArchiveExternal**. Se impostata su True ($True), indica che verranno archiviate le sessioni di comunicazione esterna (sessioni che interessano almeno un utente che non ha un account Active Directory attivo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="dc7e9-166">Per impostazione predefinita, i valori di entrambe queste proprietà sono impostati su False, pertanto non vengono archiviate le sessioni di comunicazione né interna né esterna.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-166">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="dc7e9-167">Per modificare il criterio globale, è possibile utilizzare Lync Server Management Shell e il cmdlet Set-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-167">To modify the global policy, you can use the Lync Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="dc7e9-168">Questo comando abilita l'archiviazione delle sessioni di comunicazione sia interna sia esterna:</span><span class="sxs-lookup"><span data-stu-id="dc7e9-168">This command enables the archiving of both internal and external communication sessions:</span></span>

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="dc7e9-p122">In alternativa, è possibile utilizzare New-CsArchivingPolicy per creare un nuovo criterio nell'ambito del sito o per utente. Ad esempio, questo comando crea un nuovo criterio di archiviazione per utente denominato RedmondArchivingPolicy:</span><span class="sxs-lookup"><span data-stu-id="dc7e9-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="dc7e9-p123">Se si crea un criterio per utente, sarà quindi necessario assegnarlo agli utenti appropriati. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dc7e9-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

<span data-ttu-id="dc7e9-173">I criteri di archiviazione possono essere gestiti anche utilizzando il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-173">Archiving policies can also be managed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="dc7e9-174">Nel Pannello di controllo, fare clic su **Monitoraggio e archiviazione**, quindi su **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-174">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="dc7e9-175">Per modificare criteri esistenti, fare doppio clic sui criteri (ad esempio Globale), quindi nel riquadro **Modifica criteri di archiviazione** selezionare o deselezionare le caselle di controllo **Archivia comunicazioni interne** e **Archivia comunicazioni esterne** secondo le esigenze.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-175">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="dc7e9-176">Per creare un nuovo criterio di archiviazione, fare clic su **nuovo** e quindi selezionare criteri **sito** o criteri **utente**.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-176">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="dc7e9-177">Se si creano nuovi criteri utente, è quindi necessario accedere agli account utente appropriati (dalla scheda **Utenti**) e assegnare a tali utenti i nuovi criteri.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-177">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="dc7e9-178">Passaggio 3: Configurazione della proprietà ExchangeArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="dc7e9-178">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="dc7e9-179">Se Lync Server 2013 e Exchange 2013 sono ubicati in foreste diverse, non è sufficiente abilitare semplicemente l'archiviazione di Exchange nelle impostazioni di configurazione dell'archiviazione. Questo non provocherà la messaggistica istantanea e le trascrizioni di Web Conferencing che vengono archiviate in Exchange.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-179">If Lync Server 2013 and Exchange 2013 are located in different forests then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="dc7e9-180">Al contrario, è necessario configurare anche la proprietà ExchangeArchivingPolicy in ognuno degli account utente di Lync Server rilevanti.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-180">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Lync Server user accounts.</span></span> <span data-ttu-id="dc7e9-181">Questa proprietà può essere impostata su uno di quattro possibili valori:</span><span class="sxs-lookup"><span data-stu-id="dc7e9-181">This property can be set to one of four possible values:</span></span>

1.  <span data-ttu-id="dc7e9-182">Inizializzato.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-182">Uninitialized.</span></span> <span data-ttu-id="dc7e9-183">Indica che l'archiviazione si baserà sulle impostazioni di blocco In-Place configurate per la cassetta postale di Exchange dell'utente. Se In-Place blocco non è stato abilitato nella cassetta postale dell'utente, l'utente dovrà archiviare le proprie trascrizioni di messaggistica e Web Conferencing in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-183">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Lync Server.</span></span>

2.  <span data-ttu-id="dc7e9-184">**UseLyncArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-184">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="dc7e9-185">Indica che le trascrizioni di messaggistica istantanea e Web Conferencing dell'utente devono essere archiviate in Lync Server anziché in Exchange.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-185">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Lync Server rather than in Exchange.</span></span>

3.  <span data-ttu-id="dc7e9-186">**Noarchiving**.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-186">**NoArchiving**.</span></span> <span data-ttu-id="dc7e9-187">Indica che le trascrizioni di messaggistica istantanea e Web Conferencing non devono essere archiviate.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-187">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="dc7e9-188">Si noti che questa impostazione sostituisce tutti i criteri di archiviazione di Lync Server assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-188">Note that this setting overrides any Lync Server archiving policies assigned to the user.</span></span>

4.  <span data-ttu-id="dc7e9-189">**ArchivingToExchange**.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-189">**ArchivingToExchange**.</span></span> <span data-ttu-id="dc7e9-190">Indica che le trascrizioni di messaggistica istantanea e Web Conferencing dell'utente devono essere archiviate in Exchange indipendentemente dalle impostazioni di blocco In-Place che sono state assegnate (o meno) alla cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-190">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="dc7e9-191">Ad esempio, per configurare un account utente in modo che le trascrizioni di messaggistica istantanea e Web Conferencing vengano sempre archiviate in Exchange, è possibile utilizzare un comando simile al seguente da Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="dc7e9-191">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="dc7e9-192">Per impostare gli stessi criteri di archiviazione per un gruppo di utenti (ad esempio tutti gli utenti ospitati in un pool di registrazione specificato), è possibile utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="dc7e9-192">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="dc7e9-193">Tenere presente che è necessario utilizzare Lync Server Management Shell (e Windows PowerShell) per configurare il valore della proprietà ExchangeArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-193">Note that you must use the Lync Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="dc7e9-194">Questa proprietà non è esposta agli amministratori del pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc7e9-194">This property is not exposed to administrators in the Lync Server Control Panel.</span></span>

<span data-ttu-id="dc7e9-195">Per visualizzare un elenco di tutti gli utenti a cui è stato assegnato un criterio di archiviazione specifico, è possibile utilizzare un comando simile al seguente che restituisce il nome visualizzato di Active Directory di tutti gli utenti la cui proprietà ExchangeArchivingPolicy è impostata su Uninitialized:</span><span class="sxs-lookup"><span data-stu-id="dc7e9-195">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

<span data-ttu-id="dc7e9-196">In modo analogo, questo comando restituisce il nome visualizzato degli utenti la cui proprietà ExchangeArchivingPolicy non è impostata su UseLyncArchivingPolicy:</span><span class="sxs-lookup"><span data-stu-id="dc7e9-196">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

