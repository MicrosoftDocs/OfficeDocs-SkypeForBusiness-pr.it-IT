---
title: 'Lync Server 2013: indurimento e protezione di server e applicazioni'
description: 'Lync Server 2013: indurimento e protezione di server e applicazioni.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed1205439208dfdadf5396b976d5d4876fb0aa24
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567442"
---
# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="e07ff-103">Indurimento e protezione di server e applicazioni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e07ff-103">Hardening and protecting servers and applications for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e07ff-104">_**Ultimo argomento modificato:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="e07ff-104">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="e07ff-105">È consigliabile applicare protezione avanzata e sicurezza al sistema operativo e alle applicazioni in base alle procedure consigliate per il componente specifico.</span><span class="sxs-lookup"><span data-stu-id="e07ff-105">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="e07ff-106">In questa sezione viene descritto come applicare protezione avanzata ai server applicazioni e utilizzare Criteri di gruppo per implementare blocchi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e07ff-106">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e07ff-107">È inoltre possibile indurire e proteggere i database utilizzati per la distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e07ff-107">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="e07ff-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-hardening-and-protecting-databases.md">hardening and Protecting the databases of Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e07ff-108">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="e07ff-109">Protezione dei server applicazioni</span><span class="sxs-lookup"><span data-stu-id="e07ff-109">Securing Application Servers</span></span>

<span data-ttu-id="e07ff-p103">Per i server applicazioni, è consigliabile applicare protezione avanzata al sistema operativo e all'applicazione. A un computer Windows Server 2008 dedicato all'esecuzione di Microsoft Internet Security and Acceleration (ISA) Server 2006, ad esempio, è consigliabile applicare protezione avanzata dal punto di vista del sistema operativo e delle applicazioni. La riduzione del numero di servizi in esecuzione e forniti dal server deve costituire l'obiettivo principale.</span><span class="sxs-lookup"><span data-stu-id="e07ff-p103">For applications servers, the operating system and the application should be hardened. For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective. Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="e07ff-113">Protezione dei server virtuali</span><span class="sxs-lookup"><span data-stu-id="e07ff-113">Securing Virtual Servers</span></span>

<span data-ttu-id="e07ff-114">Gli snapshot dei server virtuali contengono copie dei dischi dati del server e dump di dati in memoria, che possono a loro volta contenere dati di crittografia sensibili e pertanto provocare attacchi.</span><span class="sxs-lookup"><span data-stu-id="e07ff-114">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="e07ff-115">Per i server di produzione implementati tramite la virtualizzazione, è consigliabile disabilitare tutti gli snapshot dei server o gestirli in modo molto rigoroso.</span><span class="sxs-lookup"><span data-stu-id="e07ff-115">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="e07ff-116">Per informazioni dettagliate sulla protezione dei server virtuali Hyper-V, vedere la guida alla sicurezza di Hyper-V all'indirizzo: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176) .</span><span class="sxs-lookup"><span data-stu-id="e07ff-116">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="e07ff-117">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="e07ff-117">Group Policy</span></span>

<span data-ttu-id="e07ff-p105">In Windows Server 2008 e Windows Server 2008 R2 Criteri di gruppo offre gestione della configurazione desktop basata su directory. È possibile utilizzare Criteri di gruppo per implementare blocchi di sicurezza definendo impostazioni computer e utente all'interno di un oggetto Criteri di gruppo per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e07ff-p105">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management. You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="e07ff-120">Criteri basati sul Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="e07ff-120">Registry-based policies</span></span>

  - <span data-ttu-id="e07ff-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e07ff-121">Security</span></span>

  - <span data-ttu-id="e07ff-122">Installazione software</span><span class="sxs-lookup"><span data-stu-id="e07ff-122">Software installation</span></span>

  - <span data-ttu-id="e07ff-123">Script</span><span class="sxs-lookup"><span data-stu-id="e07ff-123">Scripts</span></span>

  - <span data-ttu-id="e07ff-124">Reindirizzamento cartelle</span><span class="sxs-lookup"><span data-stu-id="e07ff-124">Folder redirection</span></span>

  - <span data-ttu-id="e07ff-125">Servizi di installazione remota</span><span class="sxs-lookup"><span data-stu-id="e07ff-125">Remote installation services</span></span>

<span data-ttu-id="e07ff-126">Per fornire a un'interfaccia utente per l'amministratore la configurazione di queste impostazioni, i modelli amministrativi vengono forniti con versioni del sistema operativo, rilasci del Service Pack e alcune applicazioni, incluso Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e07ff-126">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="e07ff-127">Il file Communicator. adm è un modello amministrativo fornito con Lync Server 2013, viene installato nella directory% windir% \\ inf \\ e fornisce un'interfaccia per le impostazioni di criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="e07ff-127">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="e07ff-128">Ogni impostazione contenuta nel file Communicator.adm corrisponde a un'impostazione nel Registro di sistema che influisce sul comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e07ff-128">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="e07ff-129">È possibile accedere alle impostazioni da GPedit.dll, disponibile dalla console Utenti e computer di Active Directory e da Console Gestione Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="e07ff-129">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="e07ff-130">Impostazioni di sicurezza di Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="e07ff-130">Group Policy Security Settings</span></span>

<span data-ttu-id="e07ff-131">Criteri di gruppo contiene impostazioni di sicurezza per un oggetto Criteri di gruppo in Configurazione computer/Impostazioni di Windows/Impostazioni protezione quando si accede da GPedit.dll.</span><span class="sxs-lookup"><span data-stu-id="e07ff-131">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="e07ff-132">È possibile importare modelli di sicurezza per configurare le impostazioni di sicurezza per l'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="e07ff-132">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="e07ff-133">La guida alla sicurezza di Windows Server 2008 [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) e Windows server 2008 R2 Security Compliance Management Toolkit [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contengono una serie di modelli di esempio che è possibile modificare per soddisfare le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="e07ff-133">The Windows Server 2008 Security Guide at [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="e07ff-134">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="e07ff-134">Best Practices</span></span>

  - <span data-ttu-id="e07ff-135">Applicare protezione avanzata a tutti i sistemi operativi e le applicazioni server.</span><span class="sxs-lookup"><span data-stu-id="e07ff-135">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="e07ff-136">Proteggere gli snapshot dei server e migliorare la sicurezza di tutti i server virtuali.</span><span class="sxs-lookup"><span data-stu-id="e07ff-136">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="e07ff-137">Utilizzare Criteri di gruppo per implementare blocchi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e07ff-137">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

