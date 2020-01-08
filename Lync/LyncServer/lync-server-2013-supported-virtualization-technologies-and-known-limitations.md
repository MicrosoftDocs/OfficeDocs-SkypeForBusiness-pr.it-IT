---
title: 'Lync Server 2013: Tecnologie di virtualizzazione supportate e limitazioni note'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="e3df1-102">Tecnologie di virtualizzazione supportate e limitazioni note in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3df1-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3df1-103">_**Argomento Ultima modifica:** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="e3df1-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="e3df1-104">Il plug-in Lync VDI consente le chiamate audio e video per le tecnologie di virtualizzazione supportate.</span><span class="sxs-lookup"><span data-stu-id="e3df1-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="e3df1-105">In questo modo si estende la funzionalità delineata per Microsoft Lync Server 2010 nella [virtualizzazione client in Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span><span class="sxs-lookup"><span data-stu-id="e3df1-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="e3df1-106">In conformità con le normative telefoniche standard, è incluso anche il supporto per E911.</span><span class="sxs-lookup"><span data-stu-id="e3df1-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="e3df1-107">Le sezioni seguenti descrivono le tecnologie di virtualizzazione supportate dal plug-in di Lync VDI e dalle limitazioni note delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e3df1-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="e3df1-108">Supporto per le tecnologie di virtualizzazione</span><span class="sxs-lookup"><span data-stu-id="e3df1-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="e3df1-109">Il plug-in Lync VDI supporta i servizi remoti desktop completi nello scenario desktop virtuale personale, ma non nello scenario di sessione Desktop remoto.</span><span class="sxs-lookup"><span data-stu-id="e3df1-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="e3df1-110">Questi scenari possono essere descritti come segue:</span><span class="sxs-lookup"><span data-stu-id="e3df1-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="e3df1-111">**Supportati: desktop virtuali personalizzati o VDI (Virtual Desktop Infrastructure).**    In questo scenario ogni utente accede a un desktop virtuale personalizzabile ed è in grado di salvare i file sul desktop che persistono in più sessioni.</span><span class="sxs-lookup"><span data-stu-id="e3df1-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="e3df1-112">I Servizi Desktop remoto Microsoft, VMware Horizon View e Citrix XenDesktop sono implementazioni testate per l'uso con Lync.</span><span class="sxs-lookup"><span data-stu-id="e3df1-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="e3df1-113">Per informazioni sugli ambienti VDI specifici del fornitore e sull'hardware client testati da Microsoft, vedere [infrastruttura qualificata per Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span><span class="sxs-lookup"><span data-stu-id="e3df1-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="e3df1-114">**Non supportata: sessioni desktop remoto.**    In questo scenario ogni utente accede a una sessione desktop virtuale generica che non può essere personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e3df1-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="e3df1-115">Le implementazioni di esempio includono sessione desktop remoto Microsoft e Citrix XenApp combinato con Citrix Receiver.</span><span class="sxs-lookup"><span data-stu-id="e3df1-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="e3df1-116">Il plug-in di Lync VDI non supporta altre tecnologie di virtualizzazione, come la virtualizzazione delle applicazioni, che consente l'uso di un'applicazione senza richiedere l'installazione dell'applicazione completa localmente.</span><span class="sxs-lookup"><span data-stu-id="e3df1-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="e3df1-117">Le implementazioni di esempio includono Citrix XenApp e Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="e3df1-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="e3df1-118">Lo streaming di applicazioni, la comunicazione remota applicazioni e le modalità miste di virtualizzazione (ad esempio, la comunicazione remota applicazioni in una comunicazione remota desktop completa) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="e3df1-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="e3df1-119">Per consentire l'estensibilità, il plug-in di Lync VDI è stato progettato per usare API indipendenti dalla piattaforma, denominate Dynamic Virtual Channels (DVCs).</span><span class="sxs-lookup"><span data-stu-id="e3df1-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="e3df1-120">Per gli scenari non esplicitamente supportati da Lync, fare riferimento alle istruzioni del supporto del provider di soluzioni VDI.</span><span class="sxs-lookup"><span data-stu-id="e3df1-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="e3df1-121">Limitazioni note delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="e3df1-121">Known Feature Limitations</span></span>

<span data-ttu-id="e3df1-122">Di seguito sono riportate le limitazioni note quando si usa Lync 2013 in un ambiente VDI:</span><span class="sxs-lookup"><span data-stu-id="e3df1-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="e3df1-123">È disponibile un supporto limitato per le funzionalità di delega delle chiamate e dell'agente di Response Group anonimato dell'.</span><span class="sxs-lookup"><span data-stu-id="e3df1-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="e3df1-124">Non è previsto supporto per le seguenti caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="e3df1-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="e3df1-125">Pagine di regolazione dispositivi audio e video integrati.</span><span class="sxs-lookup"><span data-stu-id="e3df1-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="e3df1-126">Video con visualizzazioni multiple.</span><span class="sxs-lookup"><span data-stu-id="e3df1-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="e3df1-127">Registrazione delle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="e3df1-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="e3df1-128">Servizi Desktop remoto (RDS).</span><span class="sxs-lookup"><span data-stu-id="e3df1-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="e3df1-129">Partecipare a riunioni in forma anonima, ovvero partecipare a riunioni Lync ospitate da un'organizzazione che non è stata associata alla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e3df1-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="e3df1-130">Usare il plug-in di Lync VDI insieme a un dispositivo Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="e3df1-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="e3df1-131">Continuità di chiamata in caso di problemi di rete.</span><span class="sxs-lookup"><span data-stu-id="e3df1-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="e3df1-132">Suonerie personalizzate e musica di attesa.</span><span class="sxs-lookup"><span data-stu-id="e3df1-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="e3df1-133">Il plug-in Lync VDI non è supportato in un ambiente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3df1-133">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

