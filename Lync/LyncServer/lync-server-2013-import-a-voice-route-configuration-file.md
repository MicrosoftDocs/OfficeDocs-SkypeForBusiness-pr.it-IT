---
title: 'Lync Server 2013: importazione di un file di configurazione di route vocali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ce270b4321c484b40a20271ad21c2701c749d6a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="3b8cd-102">Importare un file di configurazione di route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b8cd-102">Import a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b8cd-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3b8cd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3b8cd-104">Se si desidera salvare la configurazione del routing vocale senza pubblicarla, eseguire la procedura seguente per utilizzare i comandi di esportazione e importazione della configurazione del pannello di controllo di Lync Server per salvare e recuperare uno snapshot della configurazione del routing vocale.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="3b8cd-105">Quando si importa un file di configurazione per il routing vocale (con estensione vcfg), ma nel frattempo sono state apportate modifiche alla configurazione del routing vocale nel server, le pagine del gruppo di **routing vocale** nel pannello di controllo di Lync Server indicheranno che sono state apportate modifiche non salvate al routing vocale.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="3b8cd-106">Tali modifiche costituiscono le differenze tra le due configurazioni di cui deve essere eseguita la riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="3b8cd-107">Se sono state apportate modifiche non salvate alle impostazioni in una pagina all'interno del gruppo, le modifiche vengono salvate nel file di configurazione vocale esportato (con estensione vcfg).</span><span class="sxs-lookup"><span data-stu-id="3b8cd-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="3b8cd-108">In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante più sessioni prima di pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="3b8cd-109">Per importare una configurazione di routing vocale</span><span class="sxs-lookup"><span data-stu-id="3b8cd-109">To import a voice routing configuration</span></span>

1.  <span data-ttu-id="3b8cd-110">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3b8cd-111">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3b8cd-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3b8cd-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3b8cd-113">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3b8cd-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3b8cd-114">Sulla barra di spostamento sinistra fare clic su **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="3b8cd-115">Scegliere **Importa configurazione** dal menu **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-115">On the **Actions** menu, click **Import configuration**.</span></span>

5.  <span data-ttu-id="3b8cd-116">Trovare il file di configurazione che si desidera importare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-116">Find the configuration file you want to import and then click **Open**.</span></span>

6.  <span data-ttu-id="3b8cd-117">Fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-117">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3b8cd-118">Ogni volta che si importa un file di configurazione vocale, è necessario usare il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-118">Whenever you import a voice configuration file, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="3b8cd-119">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="3b8cd-119">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b8cd-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b8cd-120">See Also</span></span>


[<span data-ttu-id="3b8cd-121">Esportare un file di configurazione di route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b8cd-121">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)  
[<span data-ttu-id="3b8cd-122">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b8cd-122">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

