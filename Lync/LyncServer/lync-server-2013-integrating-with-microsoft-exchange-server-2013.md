---
title: 'Lync Server 2013: integrazione con Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ba140e4f7e33684a280a9d9c4b71f1d7e141a65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="9b905-102">Integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b905-102">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b905-103">_**Argomento Ultima modifica:** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="9b905-103">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="9b905-104">Exchange e Lync Server hanno una lunga storia di integrazione e compatibilità.</span><span class="sxs-lookup"><span data-stu-id="9b905-104">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="9b905-105">Questa integrazione è più evidente all'interno della rispettiva applicazione client.</span><span class="sxs-lookup"><span data-stu-id="9b905-105">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="9b905-106">Ad esempio, le informazioni sulla presenza di Lync possono essere segnalate in Microsoft Outlook; allo stesso modo, Lync può usare il calendario di Outlook per aggiornare automaticamente le informazioni sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="9b905-106">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="9b905-107">Ad esempio, Lync può cambiare lo stato in occupato ogni volta che il calendario mostra che è stata pianificata una riunione. Anche se non è necessario eseguire Exchange per eseguire Lync Server (o viceversa), non c'è dubbio che l'uso dei due prodotti conferisca alla stessa definizione del termine "Better Together".</span><span class="sxs-lookup"><span data-stu-id="9b905-107">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="9b905-108">Questo vale soprattutto per il rilascio di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b905-108">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="9b905-109">Oltre alle funzionalità, ad esempio messaggistica unificata e messaggi ISTANTANEi e presenza, disponibili in Microsoft Exchange Server 2010 e Microsoft Lync Server 2010, le versioni di 2013 dei prodotti server includono una serie di nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9b905-109">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="9b905-110">Queste funzionalità includono elementi quali:</span><span class="sxs-lookup"><span data-stu-id="9b905-110">These capabilities include such things as:</span></span>

  - <span data-ttu-id="9b905-111">**Integrazione dell'archiviazione di Lync**.</span><span class="sxs-lookup"><span data-stu-id="9b905-111">**Lync Archiving Integration**.</span></span> <span data-ttu-id="9b905-112">In Lync Server gli amministratori di 2013 hanno ancora la possibilità di archiviare le trascrizioni di messaggistica istantanea e Web Conferencing in SQL Server, allo stesso modo in cui queste trascrizioni sono state archiviate in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9b905-112">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="9b905-113">In alternativa, tuttavia, gli amministratori possono scegliere di archiviare le trascrizioni in Exchange 2013, archiviando tali trascrizioni nelle singole cassette postali degli utenti nello stesso modo in cui gli archivi di Exchange si scambiano le comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="9b905-113">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="9b905-114">Questo significa un unico repository per tutte le comunicazioni elettroniche (sia da Exchange che da Lync Server), che rende molto più semplice cercare e recuperare le comunicazioni archiviate in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="9b905-114">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="9b905-115">**Archivio contatti unificato**.</span><span class="sxs-lookup"><span data-stu-id="9b905-115">**Unified Contact Store**.</span></span> <span data-ttu-id="9b905-116">In Lync Server 2010 gli utenti dovevano mantenere elenchi di contatti distinti in Outlook e Lync; Infatti, per assicurarti di avere gli stessi contatti disponibili in entrambi i prodotti, hai dovuto mantenere gli elenchi di contatti duplicati, uno per Outlook e uno per Lync.</span><span class="sxs-lookup"><span data-stu-id="9b905-116">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="9b905-117">Con Lync Server 2013, tuttavia, i contatti utente possono essere archiviati in Exchange 2013 e nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="9b905-117">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="9b905-118">L'uso di un singolo archivio contatti consente agli utenti di mantenere un solo set di contatti, con lo stesso set di contatti disponibile in Lync 2013, Outlook 2013 e Outlook Web Access 2013.</span><span class="sxs-lookup"><span data-stu-id="9b905-118">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="9b905-119">**Pianificazione delle riunioni di Lync da OWA**.</span><span class="sxs-lookup"><span data-stu-id="9b905-119">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="9b905-120">Con Lync Server 2013 ed Exchange 2013 Integration, gli utenti possono pianificare le riunioni Lync da Outlook Web Access 2013.</span><span class="sxs-lookup"><span data-stu-id="9b905-120">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="9b905-121">**Foto ad alta risoluzione**.</span><span class="sxs-lookup"><span data-stu-id="9b905-121">**High resolution photos**.</span></span> <span data-ttu-id="9b905-122">Lync 2010 può visualizzare solo le piccole foto dei contatti; Questo perché le foto sono state archiviate in Active Directory e Active Directory impone un pixel di 48 per la limitazione delle dimensioni di 48 pixel per le foto archiviate.</span><span class="sxs-lookup"><span data-stu-id="9b905-122">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="9b905-123">Con Lync Server 2013, tuttavia, le foto possono essere archiviate in Microsoft Exchange; che consente di avere foto ad alta risoluzione grandi quanto 648 pixel per 648 pixel.</span><span class="sxs-lookup"><span data-stu-id="9b905-123">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="9b905-124">Come ci si potrebbe aspettare, Lync 2013 è stato aggiornato per consentire la visualizzazione di queste fotografie ad alta risoluzione.</span><span class="sxs-lookup"><span data-stu-id="9b905-124">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="9b905-125">Tieni presente che queste nuove funzionalità richiedono l'uso di Lync Server 2013 ed Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="9b905-125">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="9b905-126">Oltre a ciò, gli utenti che desiderano sfruttare pienamente queste nuove funzionalità devono avere account su Lync Server 2013 ed Exchange 2013 e devono usare le versioni più recenti del software client (ad esempio Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="9b905-126">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="9b905-127">Ad esempio, l'archivio contatti unificato non è disponibile per gli utenti residenti in Lync Server 2010; allo stesso modo, le foto ad alta risoluzione non possono essere visualizzate in Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="9b905-127">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="9b905-128">Questa documentazione contiene informazioni su come integrare Lync Server 2013 ed Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="9b905-128">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="9b905-129">includendo informazioni dettagliate sull'abilitazione di nuove funzionalità, ad esempio l'integrazione di archiviazione e l'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="9b905-129">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="9b905-130">Ciò che questa documentazione non fa è discutere la configurazione iniziale e le configurazioni di questi due prodotti.</span><span class="sxs-lookup"><span data-stu-id="9b905-130">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="9b905-131">Per informazioni dettagliate sulla distribuzione di Lync Server 2013, vedere Lync Server 2013 Tech [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)Center at.</span><span class="sxs-lookup"><span data-stu-id="9b905-131">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="9b905-132">Per informazioni dettagliate sulla distribuzione di Exchange 2013, vedere Exchange 2013 Tech [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)Center at.</span><span class="sxs-lookup"><span data-stu-id="9b905-132">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9b905-133">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9b905-133">In This Section</span></span>

[<span data-ttu-id="9b905-134">Prerequisiti per l'integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b905-134">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="9b905-135">Configurazione delle applicazioni partner in Microsoft Lync Server 2013 e Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b905-135">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="9b905-136">Configurazione di Microsoft Lync Server 2013 per l'archiviazione di Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b905-136">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="9b905-137">Configurazione di Microsoft SharePoint Server 2013 per la ricerca di dati di Microsoft Lync Server 2013 archiviati</span><span class="sxs-lookup"><span data-stu-id="9b905-137">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="9b905-138">Configurazione di Microsoft Lync Server 2013 per l'uso dell'archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="9b905-138">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="9b905-139">Configurazione dell'uso di foto ad alta risoluzione in Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b905-139">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="9b905-140">Configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per Microsoft Lync Server 2013 Voice mail</span><span class="sxs-lookup"><span data-stu-id="9b905-140">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="9b905-141">Integrazione di Microsoft Lync Server 2013 e Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="9b905-141">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

