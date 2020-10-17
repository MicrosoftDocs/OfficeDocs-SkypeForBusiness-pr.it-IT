---
title: 'Lync Server 2013: pubblicare le modifiche in sospeso alla configurazione del routing vocale'
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
ms.openlocfilehash: 3202bb936f7165047b968b979b49b036be574140
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512383"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="d614e-102">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d614e-102">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d614e-103">_**Ultimo argomento modificato:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="d614e-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="d614e-104">Dopo aver apportato modifiche alle impostazioni di configurazione nelle pagine del gruppo **Routing vocale**, eseguire questa procedura per esaminare, pubblicare o annullare le modifiche in sospeso.</span><span class="sxs-lookup"><span data-stu-id="d614e-104">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d614e-105">Verificare che un solo utente alla volta modifichi le impostazioni di configurazione di Routing vocale.</span><span class="sxs-lookup"><span data-stu-id="d614e-105">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="d614e-p101">Tutte le modifiche in sospeso devono essere pubblicate contemporaneamente eseguendo il comando <STRONG>Salva tutto</STRONG>. Non è possibile pubblicare selettivamente le modifiche in sospeso. Prima di pubblicare le modifiche in sospeso, eseguire il comando <STRONG>Rivedi modifiche di cui non è stato eseguito il commit</STRONG> e annullare qualsiasi modifica di configurazione che non si desidera pubblicare.</span><span class="sxs-lookup"><span data-stu-id="d614e-p101">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command. You cannot selectively publish pending changes. Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="d614e-109">Se si esce dalle pagine del gruppo <STRONG>Routing vocale</STRONG> prima di eseguire il commit delle modifiche in sospeso, tutte le modifiche in sospeso andranno perse.</span><span class="sxs-lookup"><span data-stu-id="d614e-109">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="d614e-110">Tuttavia, è possibile esportare la configurazione corrente (incluse le modifiche in sospeso) in un file di configurazione vocale e quindi importare e pubblicare la configurazione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="d614e-110">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="d614e-111">Per ulteriori informazioni, vedere <A href="lync-server-2013-export-a-voice-route-configuration-file.md">esportare un file di configurazione di route vocali in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d614e-111">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="d614e-112">Per rivedere, pubblicare o annullare le modifiche di configurazione del routing vocale</span><span class="sxs-lookup"><span data-stu-id="d614e-112">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="d614e-113">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d614e-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="d614e-114">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d614e-114">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d614e-115">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d614e-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d614e-116">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d614e-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d614e-117">Sulla barra di spostamento sinistra fare clic su **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="d614e-117">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="d614e-118">Apportare le modifiche della configurazione desiderate alle impostazioni in ogni pagina del gruppo **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="d614e-118">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="d614e-119">Per rivedere le modifiche in sospeso senza pubblicarle, scegliere **Rivedi modifiche di cui non è stato eseguito il commit** dal menu **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d614e-119">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="d614e-120">Se si desidera annullare qualsiasi modifica in sospeso, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d614e-120">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="d614e-121">Scegliere **Annulla tutte le modifiche di cui non è stato eseguito il commit** dal menu **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d614e-121">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="d614e-122">Spostarsi sulla scheda della pagina **Routing vocale** che include le modifiche in sospeso che si desidera annullare, selezionare l'elemento con le modifiche in sospeso, fare clic su **Commit** e quindi su **Annulla modifiche selezionate**.</span><span class="sxs-lookup"><span data-stu-id="d614e-122">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="d614e-123">Dopo aver rivisto tutte le modifiche in sospeso e annullato ogni modifica che non si desidera pubblicare, fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="d614e-123">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="d614e-124">Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** in cui è visualizzato un elenco delle modifiche in sospeso fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d614e-124">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="d614e-125">Quando il pannello di controllo di Lync Server ha eseguito il commit delle modifiche, viene visualizzato il messaggio di **configurazione del routing vocale pubblicato correttamente** .</span><span class="sxs-lookup"><span data-stu-id="d614e-125">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

