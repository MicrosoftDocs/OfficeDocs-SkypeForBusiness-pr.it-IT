---
title: 'Lync Server 2013: integrazione con Microsoft Exchange Server 2013'
description: 'Lync Server 2013: integrazione con Microsoft Exchange Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54ab4a81e5455bc0a44677b1509876f39ff4d985
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543982"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="a436a-103">Integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="a436a-103">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a436a-104">_**Ultimo argomento modificato:** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="a436a-104">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="a436a-105">Exchange e Lync Server presentano una lunga cronologia di integrazione e compatibilità.</span><span class="sxs-lookup"><span data-stu-id="a436a-105">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="a436a-106">L'integrazione è particolarmente visibile attraverso le rispettive applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="a436a-106">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="a436a-107">Ad esempio, le informazioni sulla presenza di Lync possono essere segnalate in Microsoft Outlook; Analogamente, Lync è in grado di utilizzare il calendario di Outlook per aggiornare automaticamente le informazioni sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="a436a-107">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="a436a-108">Ad esempio, Lync può modificare lo stato in occupato ogni volta che il calendario indica che è stata pianificata una riunione. Anche se non è necessario eseguire Exchange per l'esecuzione di Lync Server (o viceversa), non c'è dubbio che l'utilizzo dei due prodotti insieme incarna la definizione stessa del termine "meglio insieme".</span><span class="sxs-lookup"><span data-stu-id="a436a-108">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="a436a-109">Questo è particolarmente vero per la versione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a436a-109">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="a436a-110">Oltre alle funzionalità, ad esempio messaggistica unificata e presenza, che si trovano in Microsoft Exchange Server 2010 e Microsoft Lync Server 2010, le versioni 2013 dei prodotti server includono una serie di nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a436a-110">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="a436a-111">Tali funzionalità includono elementi quali:</span><span class="sxs-lookup"><span data-stu-id="a436a-111">These capabilities include such things as:</span></span>

  - <span data-ttu-id="a436a-112">**Integrazione dell'archiviazione di Lync**.</span><span class="sxs-lookup"><span data-stu-id="a436a-112">**Lync Archiving Integration**.</span></span> <span data-ttu-id="a436a-113">In Lync Server 2013 gli amministratori hanno ancora la possibilità di archiviare le trascrizioni di messaggistica istantanea e Web Conferencing in SQL Server (allo stesso modo in cui queste trascrizioni sono state archiviate in Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="a436a-113">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="a436a-114">In alternativa, tuttavia, gli amministratori possono scegliere di eseguire le trascrizioni archiviate in Exchange 2013, archiviando tali trascrizioni nelle singole cassette postali degli utenti nello stesso modo in cui Exchange archivia le comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="a436a-114">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="a436a-115">Questo significa che si tratta di un unico repository per tutte le comunicazioni elettroniche (sia da Exchange che Lync Server), in modo da semplificare la ricerca e il recupero delle comunicazioni archiviate in caso di necessità.</span><span class="sxs-lookup"><span data-stu-id="a436a-115">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="a436a-116">**Archivio unificato per i contatti**.</span><span class="sxs-lookup"><span data-stu-id="a436a-116">**Unified Contact Store**.</span></span> <span data-ttu-id="a436a-117">In Lync Server 2010, gli utenti devono mantenere elenchi di contatti distinti in Outlook e Lync. Infatti, per assicurarsi di avere gli stessi contatti disponibili in entrambi i prodotti, è necessario mantenere gli elenchi di contatti duplicati, uno per Outlook e uno per Lync.</span><span class="sxs-lookup"><span data-stu-id="a436a-117">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="a436a-118">Con Lync Server 2013, tuttavia, è possibile archiviare i contatti degli utenti in Exchange 2013 e nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="a436a-118">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="a436a-119">L'utilizzo di un singolo archivio contatti consente agli utenti di mantenere un solo gruppo di contatti, con lo stesso insieme di contatti disponibile in Lync 2013, Outlook 2013 e Outlook Web Access 2013.</span><span class="sxs-lookup"><span data-stu-id="a436a-119">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="a436a-120">**Pianificazione delle riunioni di Lync da OWA**.</span><span class="sxs-lookup"><span data-stu-id="a436a-120">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="a436a-121">Con Lync Server 2013 e l'integrazione di Exchange 2013, gli utenti possono pianificare riunioni di Lync da Outlook Web Access 2013.</span><span class="sxs-lookup"><span data-stu-id="a436a-121">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="a436a-122">**Immagini ad alta risoluzione**.</span><span class="sxs-lookup"><span data-stu-id="a436a-122">**High resolution photos**.</span></span> <span data-ttu-id="a436a-123">Lync 2010 è in grado di visualizzare solo foto di piccole dimensioni dei contatti; Ciò è dovuto al fatto che tali foto sono state archiviate in Active Directory e Active Directory impone un limite di 48 pixel per 48 pixel per le foto archiviate.</span><span class="sxs-lookup"><span data-stu-id="a436a-123">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="a436a-124">Con Lync Server 2013, tuttavia, le foto possono essere archiviate in Microsoft Exchange. che consente di ottenere foto ad alta risoluzione di dimensioni massime di 648 pixel per 648 pixel.</span><span class="sxs-lookup"><span data-stu-id="a436a-124">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="a436a-125">Come si può immaginare, Lync 2013 è stato aggiornato in modo da consentire la visualizzazione di queste fotografie ad alta risoluzione.</span><span class="sxs-lookup"><span data-stu-id="a436a-125">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="a436a-126">Tenere presente che queste nuove funzionalità richiedono l'utilizzo di Lync Server 2013 ed Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a436a-126">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="a436a-127">Inoltre, gli utenti che desiderano sfruttare al massimo queste nuove funzionalità devono disporre di account su Lync Server 2013 ed Exchange 2013 e devono utilizzare le versioni più recenti del software client (ad esempio, Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="a436a-127">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="a436a-128">Ad esempio, l'archivio contatti unificato non è disponibile per gli utenti che sono stati ospitati in Lync Server 2010; Analogamente, le foto ad alta risoluzione non possono essere visualizzate in Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="a436a-128">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="a436a-129">In questa documentazione vengono fornite informazioni sull'integrazione di Lync Server 2013 ed Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a436a-129">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="a436a-130">e istruzioni dettagliate per l'abilitazione di nuove caratteristiche, tra cui l'integrazione dell'archiviazione e l'archivio unificato per i contatti.</span><span class="sxs-lookup"><span data-stu-id="a436a-130">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="a436a-131">La documentazione non tratta della configurazione iniziale dei due prodotti.</span><span class="sxs-lookup"><span data-stu-id="a436a-131">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="a436a-132">Per informazioni dettagliate sulla distribuzione di Lync Server 2013, vedere il Lync Server 2013 Tech Center all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127) .</span><span class="sxs-lookup"><span data-stu-id="a436a-132">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="a436a-133">Per informazioni dettagliate sulla distribuzione di Exchange 2013, vedere Exchange 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528) .</span><span class="sxs-lookup"><span data-stu-id="a436a-133">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a436a-134">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="a436a-134">In This Section</span></span>

[<span data-ttu-id="a436a-135">Prerequisiti per l'integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="a436a-135">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="a436a-136">Configurazione delle applicazioni partner in Microsoft Lync Server 2013 e Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="a436a-136">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="a436a-137">Configurazione di Microsoft Lync Server 2013 per l'utilizzo dell'archiviazione di Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="a436a-137">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="a436a-138">Configurazione di Microsoft SharePoint Server 2013 per la ricerca di dati di Microsoft Lync Server 2013 archiviati</span><span class="sxs-lookup"><span data-stu-id="a436a-138">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="a436a-139">Configurazione di Microsoft Lync Server 2013 per l'utilizzo dell'archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="a436a-139">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="a436a-140">Configurazione dell'utilizzo di foto ad alta risoluzione in Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a436a-140">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="a436a-141">Configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per la segreteria telefonica di Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a436a-141">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="a436a-142">Integrazione di Microsoft Lync Server 2013 e Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="a436a-142">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

