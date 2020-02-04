---
title: 'Lync Server 2013: pubblicare le modifiche in sospeso nella configurazione del routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aac5c30cb73ef428d0571a1a0fe6853dbf70db4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="c02ae-102">Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c02ae-102">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c02ae-103">_**Argomento Ultima modifica:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="c02ae-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="c02ae-104">Dopo aver apportato le modifiche alle impostazioni di configurazione nelle pagine del gruppo **routing vocale** , eseguire questa procedura per rivedere, pubblicare o annullare le modifiche in sospeso.</span><span class="sxs-lookup"><span data-stu-id="c02ae-104">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c02ae-105">Assicurarsi che solo un utente alla volta modifichi le impostazioni di configurazione del routing vocale.</span><span class="sxs-lookup"><span data-stu-id="c02ae-105">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="c02ae-106">Tutte le modifiche in sospeso devono essere pubblicate contemporaneamente eseguendo il comando <STRONG>commit tutti</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c02ae-106">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command.</span></span> <span data-ttu-id="c02ae-107">Non è possibile pubblicare in modo selettivo le modifiche in sospeso.</span><span class="sxs-lookup"><span data-stu-id="c02ae-107">You cannot selectively publish pending changes.</span></span> <span data-ttu-id="c02ae-108">Prima di pubblicare le modifiche in sospeso, eseguire il comando <STRONG>revisione delle modifiche non salvate</STRONG> e annullare le modifiche di configurazione che non si desidera pubblicare.</span><span class="sxs-lookup"><span data-stu-id="c02ae-108">Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="c02ae-109">Se si esce dalle pagine del gruppo <STRONG>routing vocale</STRONG> prima di confermare le modifiche in sospeso, tutte le modifiche in sospeso andranno perse.</span><span class="sxs-lookup"><span data-stu-id="c02ae-109">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="c02ae-110">È tuttavia possibile esportare la configurazione corrente (incluse le eventuali modifiche in sospeso) in un file di configurazione vocale e quindi importare e pubblicare la configurazione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="c02ae-110">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="c02ae-111">Per informazioni dettagliate, vedere <A href="lync-server-2013-export-a-voice-route-configuration-file.md">esportare un file di configurazione della route vocale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c02ae-111">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="c02ae-112">Per rivedere, pubblicare o annullare le modifiche alla configurazione del routing vocale</span><span class="sxs-lookup"><span data-stu-id="c02ae-112">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="c02ae-113">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c02ae-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c02ae-114">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c02ae-114">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c02ae-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c02ae-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c02ae-116">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c02ae-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c02ae-117">Sulla barra di spostamento sinistra fare clic su **routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="c02ae-117">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="c02ae-118">Apportare le modifiche di configurazione desiderate alle impostazioni in ogni pagina del gruppo di **routing vocale** .</span><span class="sxs-lookup"><span data-stu-id="c02ae-118">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="c02ae-119">Per rivedere le modifiche in sospeso senza pubblicarle, selezionare **rivedere le modifiche non salvate** dal menu **conferma** .</span><span class="sxs-lookup"><span data-stu-id="c02ae-119">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="c02ae-120">Se si vuole annullare una delle modifiche in sospeso, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c02ae-120">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="c02ae-121">Selezionare **Annulla tutte le modifiche non salvate** dal menu **conferma** .</span><span class="sxs-lookup"><span data-stu-id="c02ae-121">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="c02ae-122">Passare alla scheda della pagina di **routing vocale** contenente le modifiche in sospeso che si desidera annullare, selezionare l'elemento con le modifiche in sospeso, fare clic su **commit**e quindi su **Annulla modifiche selezionate**.</span><span class="sxs-lookup"><span data-stu-id="c02ae-122">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="c02ae-123">Dopo aver esaminato tutte le modifiche in sospeso e annullato qualsiasi che non si vuole pubblicare, fare clic su **commit**e quindi su **commit tutti**.</span><span class="sxs-lookup"><span data-stu-id="c02ae-123">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="c02ae-124">Nella finestra di dialogo **impostazioni di configurazione vocale non impegnata** , in cui viene visualizzato un elenco di tutte le modifiche in sospeso, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c02ae-124">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="c02ae-125">Quando il pannello di controllo di Lync Server ha eseguito il commit delle modifiche, viene visualizzato il messaggio di **configurazione del routing vocale pubblicato correttamente** .</span><span class="sxs-lookup"><span data-stu-id="c02ae-125">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

