---
title: 'Lync Server 2013: Esportazione e importazione della configurazione di route vocali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cb02759cb4fa7cf9c979ef06b594f78a6b253c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="5d110-102">Esportazione e importazione della configurazione di route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d110-102">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d110-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5d110-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5d110-104">Se si vuole salvare la configurazione del routing vocale senza pubblicarla, seguire questa procedura per usare i comandi di esportazione e importazione della configurazione del pannello di controllo di Lync Server per salvare e recuperare uno snapshot della configurazione del routing vocale.</span><span class="sxs-lookup"><span data-stu-id="5d110-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="5d110-105">Quando si importa un file di configurazione del routing vocale (con estensione vcfg), ma nel frattempo sono state apportate modifiche alla configurazione del routing vocale nel server, le pagine del gruppo **routing vocale** nel pannello di controllo di Lync Server indicheranno che non sono state salvate modifiche al routing vocale.</span><span class="sxs-lookup"><span data-stu-id="5d110-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="5d110-106">Le modifiche non salvate sono le differenze tra le due configurazioni che richiedono la riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="5d110-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5d110-107">Se sono state apportate modifiche non salvate alle impostazioni di una pagina all'interno del gruppo di <STRONG>routing vocale</STRONG> , le modifiche vengono salvate nel file di configurazione vocale esportato (. vcfg).</span><span class="sxs-lookup"><span data-stu-id="5d110-107">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="5d110-108">In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante più sessioni del pannello di controllo di Lync Server prima di pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="5d110-108">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5d110-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5d110-109">In This Section</span></span>

  - [<span data-ttu-id="5d110-110">Esportare un file di configurazione della route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d110-110">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="5d110-111">Importare un file di configurazione di route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d110-111">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="5d110-112">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5d110-112">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

