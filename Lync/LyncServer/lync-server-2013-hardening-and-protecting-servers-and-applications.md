---
title: 'Lync Server 2013: Protezione avanzata e sicurezza di server e applicazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00fea9bd192dedaf16567209798f12c7bff23e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="0dbc9-102">Protezione avanzata e sicurezza di server e applicazioni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dbc9-102">Hardening and protecting servers and applications for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0dbc9-103">_**Argomento Ultima modifica:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="0dbc9-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="0dbc9-104">È consigliabile indurire e proteggere il sistema operativo e le applicazioni in base alle procedure consigliate per quel componente specifico.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-104">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="0dbc9-105">Questa sezione descrive come indurire i server delle applicazioni e usare criteri di gruppo per implementare i blocco della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-105">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0dbc9-106">È anche possibile indurire e proteggere i database usati per la distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-106">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="0dbc9-107">Per informazioni dettagliate, vedere <A href="lync-server-2013-hardening-and-protecting-databases.md">indurimento e protezione dei database di Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-107">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="0dbc9-108">Protezione dei server applicazioni</span><span class="sxs-lookup"><span data-stu-id="0dbc9-108">Securing Application Servers</span></span>

<span data-ttu-id="0dbc9-109">Per i server delle applicazioni, il sistema operativo e l'applicazione devono essere induriti.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-109">For applications servers, the operating system and the application should be hardened.</span></span> <span data-ttu-id="0dbc9-110">Ad esempio, un computer Windows Server 2008 dedicato all'uso di Microsoft Internet Security and Acceleration (ISA) Server 2006 deve essere indurito dal sistema operativo e dal punto di vista dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-110">For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective.</span></span> <span data-ttu-id="0dbc9-111">L'obiettivo principale è ridurre al minimo il numero di servizi eseguiti e forniti dal server.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-111">Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="0dbc9-112">Protezione dei server virtuali</span><span class="sxs-lookup"><span data-stu-id="0dbc9-112">Securing Virtual Servers</span></span>

<span data-ttu-id="0dbc9-113">Gli snapshot del server virtuale contengono copie dei dischi di dati del server e contengono anche dump di dati in memoria, che possono contenere dati crittografici riservati che potrebbero portare a attacchi.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-113">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="0dbc9-114">Per i server di produzione implementati con la virtualizzazione, è consigliabile disabilitare tutti gli snapshot del server o gestirli in modo molto controllato.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-114">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="0dbc9-115">Per informazioni dettagliate sulla protezione dei server virtuali Hyper-V, vedere la guida alla sicurezza di Hyper- [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)v all'indirizzo:.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-115">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="0dbc9-116">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="0dbc9-116">Group Policy</span></span>

<span data-ttu-id="0dbc9-117">In Windows Server 2008 e Windows Server 2008 R2, criteri di gruppo offre la gestione della configurazione desktop basata su directory.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-117">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management.</span></span> <span data-ttu-id="0dbc9-118">È possibile usare criteri di gruppo per implementare i blocco di sicurezza definendo le impostazioni di computer e utenti in un oggetto Criteri di gruppo per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0dbc9-118">You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="0dbc9-119">Criteri basati sul Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="0dbc9-119">Registry-based policies</span></span>

  - <span data-ttu-id="0dbc9-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0dbc9-120">Security</span></span>

  - <span data-ttu-id="0dbc9-121">Installazione del software</span><span class="sxs-lookup"><span data-stu-id="0dbc9-121">Software installation</span></span>

  - <span data-ttu-id="0dbc9-122">Script</span><span class="sxs-lookup"><span data-stu-id="0dbc9-122">Scripts</span></span>

  - <span data-ttu-id="0dbc9-123">Reindirizzamento delle cartelle</span><span class="sxs-lookup"><span data-stu-id="0dbc9-123">Folder redirection</span></span>

  - <span data-ttu-id="0dbc9-124">Servizi di installazione remota</span><span class="sxs-lookup"><span data-stu-id="0dbc9-124">Remote installation services</span></span>

<span data-ttu-id="0dbc9-125">Per offrire all'amministratore un'interfaccia utente per la configurazione di queste impostazioni, i modelli amministrativi vengono forniti con le versioni del sistema operativo, i rilasci di Service Pack e alcune applicazioni, tra cui Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-125">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="0dbc9-126">Il file Communicator. adm è un modello amministrativo fornito con Lync Server 2013, viene installato nella directory% windir%\\inf\\ e fornisce un'interfaccia per le impostazioni dei criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-126">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="0dbc9-127">Ogni impostazione in Communicator. adm corrisponde a un'impostazione nel registro di sistema che influisce sul comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-127">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="0dbc9-128">È possibile accedere alle impostazioni da GPedit. dll, disponibile dalla console utenti e computer di Active Directory e dalla console Gestione criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-128">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="0dbc9-129">Impostazioni di sicurezza dei criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="0dbc9-129">Group Policy Security Settings</span></span>

<span data-ttu-id="0dbc9-130">Criteri di gruppo contiene le impostazioni di sicurezza per un GPO in configurazione computer/impostazioni di Windows/impostazioni di sicurezza quando si accede da GPedit. dll.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-130">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="0dbc9-131">È possibile importare modelli di sicurezza per configurare le impostazioni di sicurezza per l'oggetto Criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-131">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="0dbc9-132">La guida alla sicurezza di [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) windows Server 2008 e windows Server 2008 R2 Security Compliance Management Toolkit [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) contiene numerosi modelli di esempio che è possibile modificare per soddisfare le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-132">The Windows Server 2008 Security Guide at [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="0dbc9-133">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="0dbc9-133">Best Practices</span></span>

  - <span data-ttu-id="0dbc9-134">Indurire tutti i sistemi operativi e le applicazioni del server.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-134">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="0dbc9-135">Proteggere gli snapshot del server e migliorare la sicurezza di tutti i server virtuali.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-135">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="0dbc9-136">Usare criteri di gruppo per implementare il blocco della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0dbc9-136">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

