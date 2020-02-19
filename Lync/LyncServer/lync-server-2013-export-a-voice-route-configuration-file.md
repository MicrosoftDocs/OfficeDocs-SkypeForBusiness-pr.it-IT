---
title: 'Lync Server 2013: esportare un file di configurazione di route vocali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9cc4eb13c8605d20d87d851009e066c48439fe8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="cf7f5-102">Esportare un file di configurazione di route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf7f5-102">Export a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf7f5-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cf7f5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cf7f5-104">Se si desidera salvare la configurazione del routing vocale senza pubblicarla, eseguire la procedura seguente per utilizzare i comandi di esportazione e importazione della configurazione del pannello di controllo di Lync Server per salvare e recuperare uno snapshot della configurazione del routing vocale.</span><span class="sxs-lookup"><span data-stu-id="cf7f5-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="cf7f5-105">Quando si importa un file di configurazione per il routing vocale (con estensione vcfg), ma nel frattempo sono state apportate modifiche alla configurazione del routing vocale nel server, le pagine del gruppo di **routing vocale** nel pannello di controllo di Lync Server indicheranno che sono state apportate modifiche non salvate al routing vocale.</span><span class="sxs-lookup"><span data-stu-id="cf7f5-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="cf7f5-106">Tali modifiche costituiscono le differenze tra le due configurazioni di cui deve essere eseguita la riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="cf7f5-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="cf7f5-107">Se sono state apportate modifiche non salvate alle impostazioni in una pagina all'interno del gruppo, le modifiche vengono salvate nel file di configurazione vocale esportato (con estensione vcfg).</span><span class="sxs-lookup"><span data-stu-id="cf7f5-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="cf7f5-108">In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante più sessioni prima di pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="cf7f5-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="cf7f5-109">Per esportare una configurazione di routing vocale</span><span class="sxs-lookup"><span data-stu-id="cf7f5-109">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="cf7f5-110">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cf7f5-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="cf7f5-111">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cf7f5-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="cf7f5-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf7f5-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cf7f5-113">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cf7f5-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cf7f5-114">Nella barra di spostamento sinistra fare clic su **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="cf7f5-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="cf7f5-115">Scegliere **Esporta configurazione** dal menu **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="cf7f5-115">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="cf7f5-116">Specificare un percorso e un nome di file e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cf7f5-116">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cf7f5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf7f5-117">See Also</span></span>


[<span data-ttu-id="cf7f5-118">Importare un file di configurazione di route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf7f5-118">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

