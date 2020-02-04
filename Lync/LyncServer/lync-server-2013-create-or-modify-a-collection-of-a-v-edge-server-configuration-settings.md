---
title: Creare o modificare una raccolta di impostazioni di configurazione di un/V Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c4b45b34b5c52d0eb138fbc16c37e5aaee7262b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d3dcd-102">Creare o modificare una raccolta di impostazioni di configurazione di un/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3dcd-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3dcd-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d3dcd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d3dcd-104">Il servizio A/V Edge consente agli utenti interni (utenti che hanno effettuato l'accesso alla rete organizzativa) di condividere audio e video con utenti esterni (utenti che non hanno eseguito l'accesso alla rete organizzativa).</span><span class="sxs-lookup"><span data-stu-id="d3dcd-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="d3dcd-105">Il servizio A/V Edge viene gestito principalmente con le impostazioni di configurazione di Edge A/V, che possono essere configurate nell'ambito del sito o nell'ambito del servizio, ovvero possono essere configurate per un singolo server A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="d3dcd-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="d3dcd-106">Quando si installa Lync Server, viene creata una raccolta globale di impostazioni di configurazione di Edge A/V.</span><span class="sxs-lookup"><span data-stu-id="d3dcd-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="d3dcd-107">Oltre a questo, puoi usare Windows PowerShell e il cmdlet New-CsAVEdgeConfiguration per creare nuove impostazioni nell'ambito del sito o nell'ambito del servizio (ovvero, per un singolo A/V Edge Server).</span><span class="sxs-lookup"><span data-stu-id="d3dcd-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="d3dcd-108">Se crei nuove impostazioni, tieni presente che:</span><span class="sxs-lookup"><span data-stu-id="d3dcd-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="d3dcd-109">Le impostazioni configurate nell'ambito del servizio, ovvero su un singolo server, hanno la priorità su tutto.</span><span class="sxs-lookup"><span data-stu-id="d3dcd-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="d3dcd-110">Le impostazioni configurate nell'ambito del sito hanno la priorità sulle impostazioni configurate nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="d3dcd-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="d3dcd-111">Tuttavia, le impostazioni dell'ambito del servizio sostituiranno anche le impostazioni dell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="d3dcd-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="d3dcd-112">Le impostazioni dell'ambito globale verranno usate solo se non sono state configurate impostazioni di servizio nel singolo server e se non sono presenti impostazioni del sito per il sito in cui si trova il server.</span><span class="sxs-lookup"><span data-stu-id="d3dcd-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="d3dcd-113">È quindi possibile modificare le impostazioni usando il cmdlet Set-CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d3dcd-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="d3dcd-114">Per altre informazioni, vedere gli argomenti della Guida per i cmdlet [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) e [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="d3dcd-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="d3dcd-115">Per creare nuove impostazioni di configurazione a/V Edge nell'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="d3dcd-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="d3dcd-116">Il comando seguente crea una nuova raccolta di impostazioni di configurazione A/V Edge per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="d3dcd-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="d3dcd-117">Per creare impostazioni di configurazione personalizzate a/V Edge nell'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="d3dcd-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="d3dcd-118">Dato che non sono stati inclusi parametri aggiuntivi, queste nuove impostazioni utilizzeranno i valori predefiniti per il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="d3dcd-118">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service.</span></span> <span data-ttu-id="d3dcd-119">In alternativa, è possibile aggiungere altri parametri e valori di parametro per creare una raccolta personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d3dcd-119">Alternatively, you can add additional parameters and parameter values to create a custom collection.</span></span> <span data-ttu-id="d3dcd-120">Questo comando, ad esempio, imposta la proprietà MaxTokenLifetime su 4 ore (04 ore: 00 minuti: 00 secondi):</span><span class="sxs-lookup"><span data-stu-id="d3dcd-120">For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="d3dcd-121">Per creare impostazioni di configurazione personalizzate a/V Edge nell'ambito del servizio</span><span class="sxs-lookup"><span data-stu-id="d3dcd-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="d3dcd-122">Questo comando crea una raccolta simile applicata all'atl-edge-001.litwareinc.com A/V Edge Server:</span><span class="sxs-lookup"><span data-stu-id="d3dcd-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="d3dcd-123">Per modificare le impostazioni di configurazione di un/V Edge esistenti</span><span class="sxs-lookup"><span data-stu-id="d3dcd-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="d3dcd-124">In questo esempio, il cmdlet Set-CsAVEdgeConfiguration viene usato per modificare la durata del token massimo per il sito Redmond in 12 ore:</span><span class="sxs-lookup"><span data-stu-id="d3dcd-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d3dcd-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3dcd-125">See Also</span></span>


[<span data-ttu-id="d3dcd-126">Restituire le informazioni di configurazione A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3dcd-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="d3dcd-127">Eliminare una raccolta esistente di impostazioni di configurazione di un/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3dcd-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="d3dcd-128">Audio/video (A/V) Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3dcd-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="d3dcd-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d3dcd-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="d3dcd-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d3dcd-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

