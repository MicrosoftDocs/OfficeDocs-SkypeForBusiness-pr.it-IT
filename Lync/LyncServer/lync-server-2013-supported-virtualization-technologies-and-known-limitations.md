---
title: 'Lync Server 2013: tecnologie di virtualizzazione supportate e limitazioni note'
description: 'Lync Server 2013: tecnologie di virtualizzazione supportate e limitazioni note.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745fa535462d29342f4c0a58674ee6487db42a6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544612"
---
# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="8ff42-103">Tecnologie di virtualizzazione supportate e limitazioni note in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ff42-103">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ff42-104">_**Ultimo argomento modificato:** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="8ff42-104">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="8ff42-105">Il plug-in VDI di Lync consente la chiamata audio e video per le tecnologie di virtualizzazione supportate.</span><span class="sxs-lookup"><span data-stu-id="8ff42-105">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="8ff42-106">In questo articolo viene estesa la funzionalità delineata per Microsoft Lync Server 2010 nella [virtualizzazione client in Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span><span class="sxs-lookup"><span data-stu-id="8ff42-106">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="8ff42-107">In conformità con le normative telefoniche standard, è incluso anche il supporto per E911.</span><span class="sxs-lookup"><span data-stu-id="8ff42-107">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="8ff42-108">Nelle sezioni seguenti vengono descritte le tecnologie di virtualizzazione supportate dal plug-in VDI di Lync e le limitazioni note delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8ff42-108">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="8ff42-109">Supporto per le tecnologie di virtualizzazione</span><span class="sxs-lookup"><span data-stu-id="8ff42-109">Support for Virtualization Technologies</span></span>

<span data-ttu-id="8ff42-110">Il plug-in VDI di Lync supporta le funzionalità remote desktop complete nello scenario di desktop virtuale personale, ma non nello scenario di sessione Desktop remoto.</span><span class="sxs-lookup"><span data-stu-id="8ff42-110">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="8ff42-111">Questi scenari possono essere descritti nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="8ff42-111">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="8ff42-112">**Supportato: desktop virtuali personalizzati o VDI (Virtual Desktop Infrastructure).**     In questo scenario, ogni utente esegue l'accesso a un desktop virtuale personalizzabile ed è in grado di salvare i file sul desktop che persistono tra le sessioni.</span><span class="sxs-lookup"><span data-stu-id="8ff42-112">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="8ff42-113">Servizi Desktop remoto Microsoft, VMware Horizon View e Citrix XenDesktop sono implementazioni che sono state testate per l'utilizzo con Lync.</span><span class="sxs-lookup"><span data-stu-id="8ff42-113">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="8ff42-114">Per informazioni sugli ambienti VDI specifici del fornitore e sull'hardware client che sono stati testati da Microsoft, vedere [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span><span class="sxs-lookup"><span data-stu-id="8ff42-114">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="8ff42-115">**Non supportata: sessioni di desktop remoto.**     In questo scenario, ogni utente esegue l'accesso a una sessione desktop virtuale generica che non può essere personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8ff42-115">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="8ff42-116">Le implementazioni di esempio includono Microsoft Remote Desktop Sessions (RDSH) e Citrix XenApp in combinazione con Citrix Receiver.</span><span class="sxs-lookup"><span data-stu-id="8ff42-116">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="8ff42-117">Il plug-in VDI di Lync non supporta altre tecnologie di virtualizzazione, ad esempio la virtualizzazione dell'applicazione, che consente l'utilizzo di un'applicazione senza richiedere l'installazione dell'applicazione completa localmente.</span><span class="sxs-lookup"><span data-stu-id="8ff42-117">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="8ff42-118">Le implementazioni di esempio includono Citrix XenApp e Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="8ff42-118">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="8ff42-119">Le modalità di flusso applicazioni, comunicazione remota applicazioni e virtualizzazione mista, ad esempio la comunicazione remota applicazioni in Desktop remoto completo, non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="8ff42-119">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="8ff42-120">Per consentire l'estensibilità, il plug-in VDI di Lync è stato creato per l'utilizzo di API indipendenti dalla piattaforma denominate Dynamic Virtual Channels (dinamici).</span><span class="sxs-lookup"><span data-stu-id="8ff42-120">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="8ff42-121">Per gli scenari non supportati in modo esplicito da Lync, fare riferimento alle istruzioni di supporto del provider di soluzioni VDI.</span><span class="sxs-lookup"><span data-stu-id="8ff42-121">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="8ff42-122">Limitazioni note delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="8ff42-122">Known Feature Limitations</span></span>

<span data-ttu-id="8ff42-123">Quando si utilizza Lync 2013 in un ambiente VDI, sono note le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ff42-123">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="8ff42-124">È disponibile un supporto limitato per le funzionalità di delega chiamata e agente di Response Group Anonymization.</span><span class="sxs-lookup"><span data-stu-id="8ff42-124">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="8ff42-125">Non è previsto supporto per le seguenti caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="8ff42-125">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="8ff42-126">Pagine di regolazione dispositivi audio e video integrati.</span><span class="sxs-lookup"><span data-stu-id="8ff42-126">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="8ff42-127">Video con più visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8ff42-127">Multiple-view video.</span></span>
    
      - <span data-ttu-id="8ff42-128">Registrazione delle conversazioni.</span><span class="sxs-lookup"><span data-stu-id="8ff42-128">Recording of conversations.</span></span>
    
      - <span data-ttu-id="8ff42-129">Servizi Desktop remoto (RDS).</span><span class="sxs-lookup"><span data-stu-id="8ff42-129">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="8ff42-130">Partecipare a riunioni in forma anonima, ovvero partecipare a riunioni di Lync ospitate da un'organizzazione non federata con la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8ff42-130">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="8ff42-131">Utilizzo del plug-in VDI di Lync insieme a un dispositivo Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="8ff42-131">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="8ff42-132">Continuità di chiamata in caso di problemi di rete.</span><span class="sxs-lookup"><span data-stu-id="8ff42-132">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="8ff42-133">Suonerie personalizzate e funzionalità di musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="8ff42-133">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="8ff42-134">Il plug-in VDI di Lync non è supportato in un ambiente Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="8ff42-134">The Lync VDI plug-in is not supported in a Microsoft 365 or Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

