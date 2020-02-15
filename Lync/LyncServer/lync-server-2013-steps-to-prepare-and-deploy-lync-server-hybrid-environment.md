---
title: 'Lync Server 2013: passaggi per la preparazione e la distribuzione di un ambiente ibrido di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3326db7ce62279c4295bc13ec262a5a553ca5e62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a><span data-ttu-id="38438-102">Passaggi per la preparazione e la distribuzione dell'ambiente ibrido di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38438-102">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38438-103">_**Ultimo argomento modificato:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="38438-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="38438-104">Nella tabella seguente sono elencati i passaggi necessari per preparare l'ambiente per una distribuzione ibrida con Skype for business online e Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="38438-104">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38438-105">Operazione completata?</span><span class="sxs-lookup"><span data-stu-id="38438-105">Completed?</span></span></th>
<th><span data-ttu-id="38438-106">Passaggio</span><span class="sxs-lookup"><span data-stu-id="38438-106">Step</span></span></th>
<th><span data-ttu-id="38438-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38438-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="38438-108">Creare un account tenant per Office 365 e abilitare Lync Online</span><span class="sxs-lookup"><span data-stu-id="38438-108">Create a tenant account for Office 365 and enable Lync Online</span></span></p></td>
<td><p><span data-ttu-id="38438-109">Informazioni su Office 365 e Lync online in <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="38438-109">Learn about Office 365 and Lync Online at <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</span></span></p>
<p><span data-ttu-id="38438-110">Per assicurarsi che l'ambiente sia pronto per Office 365, vedere i <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">requisiti di sistema</a>.</span><span class="sxs-lookup"><span data-stu-id="38438-110">To make sure that your environment is ready for Office 365, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Requirements</a>.</span></span></p>
<p><span data-ttu-id="38438-111">Per informazioni dettagliate sulla configurazione di Office 365, vedere <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Guida introduttiva a office 365</a> e <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">configurazione di Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="38438-111">For details about setting up Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with Office 365</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Set Up Office 365</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="38438-112">Aggiungere il dominio e verificare la proprietà</span><span class="sxs-lookup"><span data-stu-id="38438-112">Add your domain and verify ownership</span></span></p></td>
<td><p><span data-ttu-id="38438-113">Il dominio è talvolta denominato anche <em>dominio Vanity</em>.</span><span class="sxs-lookup"><span data-stu-id="38438-113">Your domain is sometimes also referred to as your <em>vanity domain</em>.</span></span> <span data-ttu-id="38438-114">È necessario aggiungere il dominio al tenant di Office 365, quindi seguire la procedura per convalidare il dominio con Office 365.</span><span class="sxs-lookup"><span data-stu-id="38438-114">You must add your domain to your Office 365 tenant, and then follow the steps to validate the domain with Office 365.</span></span> <span data-ttu-id="38438-115">In questo modo si conferma che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="38438-115">This is to confirm that you are the owner of the domain.</span></span></p>
<p><span data-ttu-id="38438-116">Per aggiungere il dominio al tenant di Office 365, seguire la procedura descritta in <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">aggiungere il proprio dominio a office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="38438-116">To add your domain to your Office 365 tenant, follow the steps described at <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Add your domain to Office 365</a>.</span></span></p>
<p><span data-ttu-id="38438-117">Completare tutti i passaggi di ogni sezione dell'argomento, tra cui &quot;la modifica dei record DNS per i servizi di Office 365.&quot;</span><span class="sxs-lookup"><span data-stu-id="38438-117">Complete all of the steps in each section in the topic, including &quot;Edit DNS records for your Office 365 services.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="38438-118">Verificare la conformità dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="38438-118">Verify environment readiness</span></span></p></td>
<td><p><span data-ttu-id="38438-119">È possibile utilizzare l'assistente per l'installazione di Office 365 per la distribuzione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="38438-119">You can use the Office 365 Setup Assistant to help you deploy Office 365.</span></span> <span data-ttu-id="38438-120">Per ulteriori informazioni, vedere <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">utilizzo di Setup Assistant per determinare la conformità di Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="38438-120">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Use Setup Assistant to determine Office 365 readiness</a>.</span></span></p>
<p><span data-ttu-id="38438-121">Per informazioni dettagliate sull'utilizzo dello strumento e sulla distribuzione di Office 365, vedere <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Guida alla distribuzione di office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="38438-121">For details about using the tool and deploying Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 deployment guide</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="38438-122">Preparare la sincronizzazione con Active Directory</span><span class="sxs-lookup"><span data-stu-id="38438-122">Prepare for Active Directory synchronization</span></span></p></td>
<td><p><span data-ttu-id="38438-123">La sincronizzazione di Active Directory mantiene continuamente sincronizzata la propria Active Directory locale con Office 365.</span><span class="sxs-lookup"><span data-stu-id="38438-123">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="38438-124">In questo modo è possibile creare versioni sincronizzate di ogni account utente e gruppo, nonché abilitare la sincronizzazione dell'elenco indirizzi globale (GAL) dall'ambiente Microsoft Exchange Server locale a Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="38438-124">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="38438-125">È necessario sincronizzare gli account di Active Directory per tutti gli utenti di Lync nell'organizzazione tra le distribuzioni di Lync locali e online, anche se gli utenti non vengono spostati in Lync Online.</span><span class="sxs-lookup"><span data-stu-id="38438-125">You need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="38438-126">Se non si sincronizzano tutti gli utenti, la comunicazione tra gli utenti locali e quelli online nell'organizzazione potrebbe non funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="38438-126">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>


</div>
<p><span data-ttu-id="38438-127">Per preparare l'ambiente per la sincronizzazione di Active Directory, eseguire i passaggi descritti in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Roadmap della sincronizzazione della directory</a>, inclusa la configurazione di Single Sign-on.</span><span class="sxs-lookup"><span data-stu-id="38438-127">To prepare your environment for Active Directory synchronization, follow the steps described in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Directory synchronization Roadmap</a>, including setting up single sign-on.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="38438-128">Creare certificati per Active Directory Federation Services (AD FS)</span><span class="sxs-lookup"><span data-stu-id="38438-128">Create certificates for Active Directory Federation Services (AD FS)</span></span></p></td>
<td><p><span data-ttu-id="38438-129">Sarà necessario creare i certificati utilizzati per la Federazione delle identità con Office 365.</span><span class="sxs-lookup"><span data-stu-id="38438-129">You will need to create the certificates that are used for identity federation with Office 365.</span></span> <span data-ttu-id="38438-130">Per ulteriori informazioni, vedere la sezione "certificati del server federativo" dell'argomento piano per e deploy AD FS per l'utilizzo con Single Sign-on in <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">elenco di controllo: utilizzare ADFS per implementare e gestire l'accesso Single Sign-on</a>.</span><span class="sxs-lookup"><span data-stu-id="38438-130">For more information, see the “Federation server certificates” section of the Plan for and deploy AD FS for use with single sign-on topic at <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Use AD FS to implement and manage single sign-on</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="38438-131">Assegnare certificati per ADFS</span><span class="sxs-lookup"><span data-stu-id="38438-131">Assign certificates for AD FS</span></span></p></td>
<td><p><span data-ttu-id="38438-132">Dopo aver creato i certificati utilizzati per la Federazione delle identità con Office 365, è necessario installarli e assegnarli.</span><span class="sxs-lookup"><span data-stu-id="38438-132">After you create the certificates that are used for identity federation with Office 365, you must install and assign them.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="38438-133">Spostare gli utenti pilota in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="38438-133">Move pilot users to Skype for Business Online</span></span></p></td>
<td><p><span data-ttu-id="38438-134">Dopo aver completato la procedura per preparare e configurare l'ambiente per Skype for business online, è possibile iniziare a spostare gli utenti pilota in Lync Online.</span><span class="sxs-lookup"><span data-stu-id="38438-134">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to Lync Online.</span></span></p>
<p><span data-ttu-id="38438-135">Vedere <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync online in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="38438-135">See <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="38438-136">Amministrazione degli utenti in una distribuzione ibrida</span><span class="sxs-lookup"><span data-stu-id="38438-136">Administering users in a hybrid deployment</span></span></p></td>
<td><p><span data-ttu-id="38438-137">Per informazioni dettagliate su come amministrare gli utenti in una distribuzione ibrida, vedere <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">amministrazione degli utenti in una distribuzione ibrida di Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="38438-137">For details about how to administer users in a hybrid deployment, see <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

