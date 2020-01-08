---
title: 'Lync Server 2013: esportare un file di configurazione della route vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d61bb4dfda9aa91191515f60b0a26b2665f31421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="a9d25-102">Esportare un file di configurazione della route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9d25-102">Export a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9d25-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a9d25-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a9d25-104">Se si vuole salvare la configurazione del routing vocale senza pubblicarla, seguire questa procedura per usare i comandi di esportazione e importazione della configurazione del pannello di controllo di Lync Server per salvare e recuperare uno snapshot della configurazione del routing vocale.</span><span class="sxs-lookup"><span data-stu-id="a9d25-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="a9d25-105">Quando si importa un file di configurazione del routing vocale (con estensione vcfg), ma nel frattempo sono state apportate modifiche alla configurazione del routing vocale nel server, le pagine del gruppo **routing vocale** nel pannello di controllo di Lync Server indicheranno che non sono state salvate modifiche al routing vocale.</span><span class="sxs-lookup"><span data-stu-id="a9d25-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="a9d25-106">Le modifiche non salvate sono le differenze tra le due configurazioni che richiedono la riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="a9d25-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="a9d25-107">Se sono state apportate modifiche non salvate alle impostazioni di una pagina all'interno del gruppo, le modifiche vengono salvate nel file di configurazione vocale esportato (. vcfg).</span><span class="sxs-lookup"><span data-stu-id="a9d25-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="a9d25-108">In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante più sessioni prima di pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="a9d25-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="a9d25-109">Per esportare una configurazione di routing vocale</span><span class="sxs-lookup"><span data-stu-id="a9d25-109">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="a9d25-110">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a9d25-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a9d25-111">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a9d25-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a9d25-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a9d25-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a9d25-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a9d25-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a9d25-114">Sulla barra di spostamento sinistra fare clic su **routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="a9d25-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="a9d25-115">Nel menu **azioni** fare clic su **Esporta configurazione**.</span><span class="sxs-lookup"><span data-stu-id="a9d25-115">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="a9d25-116">Specificare un percorso e un nome file e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a9d25-116">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a9d25-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9d25-117">See Also</span></span>


[<span data-ttu-id="a9d25-118">Importare un file di configurazione di route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9d25-118">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

