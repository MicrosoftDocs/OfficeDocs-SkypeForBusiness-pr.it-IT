---
title: 'Lync Server 2013: esportazione e importazione della configurazione del routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3a65c0ab32f40c78c6c679f7be7b86a4ccca1e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="351bf-102">Esportazione e importazione della configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="351bf-102">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="351bf-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="351bf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="351bf-104">Se si desidera salvare la configurazione del routing vocale senza pubblicarla, eseguire la procedura seguente per utilizzare i comandi di esportazione e importazione della configurazione del pannello di controllo di Lync Server per salvare e recuperare uno snapshot della configurazione del routing vocale.</span><span class="sxs-lookup"><span data-stu-id="351bf-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="351bf-105">Quando si importa un file di configurazione per il routing vocale (con estensione vcfg), ma nel frattempo sono state apportate modifiche alla configurazione del routing vocale nel server, le pagine del gruppo di **routing vocale** nel pannello di controllo di Lync Server indicheranno che sono state apportate modifiche non salvate al routing vocale.</span><span class="sxs-lookup"><span data-stu-id="351bf-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="351bf-106">Tali modifiche costituiscono le differenze tra le due configurazioni di cui deve essere eseguita la riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="351bf-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="351bf-107">Se sono state apportate modifiche di cui non è stato eseguito il commit alle impostazioni di una pagina all'interno del gruppo <STRONG>Routing vocale</STRONG>, le modifiche vengono salvate nel file di configurazione vocale esportato ( con estensione vcfg).</span><span class="sxs-lookup"><span data-stu-id="351bf-107">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="351bf-108">In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante diverse sessioni del pannello di controllo di Lync Server prima di pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="351bf-108">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="351bf-109">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="351bf-109">In This Section</span></span>

  - [<span data-ttu-id="351bf-110">Esportare un file di configurazione di route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="351bf-110">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="351bf-111">Importare un file di configurazione di route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="351bf-111">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="351bf-112">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="351bf-112">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

