---
title: Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Riepilogo: informazioni su come rivedere, pubblicare o annullare le modifiche alla configurazione del routing vocale in Skype for Business Server tramite il pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: 12cf80c2a14d3bad532aaf21a942536f44537300
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766959"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="c1e1c-103">Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for business</span><span class="sxs-lookup"><span data-stu-id="c1e1c-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="c1e1c-104">**Riepilogo:** Informazioni su come rivedere, pubblicare o annullare le modifiche alla configurazione del routing vocale in Skype for Business Server tramite il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="c1e1c-105">Dopo aver apportato le modifiche alle impostazioni di configurazione nelle pagine del gruppo **routing vocale** , eseguire questa procedura per rivedere, pubblicare o annullare le modifiche in sospeso.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c1e1c-106">Assicurarsi che solo un utente alla volta modifichi le impostazioni di configurazione del routing vocale.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c1e1c-107">Tutte le modifiche in sospeso devono essere pubblicate contemporaneamente eseguendo il comando **commit tutti** .</span><span class="sxs-lookup"><span data-stu-id="c1e1c-107">All pending changes must be published at the same time by running the **Commit all** command.</span></span> <span data-ttu-id="c1e1c-108">Non è possibile pubblicare in modo selettivo le modifiche in sospeso.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-108">You cannot selectively publish pending changes.</span></span> <span data-ttu-id="c1e1c-109">Prima di pubblicare le modifiche in sospeso, eseguire il comando **revisione delle modifiche non salvate** e annullare le modifiche di configurazione che non si desidera pubblicare.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-109">Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c1e1c-110">Se si esce dalle pagine del gruppo **routing vocale** prima di confermare le modifiche in sospeso, tutte le modifiche in sospeso andranno perse.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="c1e1c-111">È tuttavia possibile esportare la configurazione corrente (incluse le eventuali modifiche in sospeso) in un file di configurazione vocale e quindi importare e pubblicare la configurazione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="c1e1c-112">Per informazioni dettagliate, vedere [esportare o importare un file di configurazione della route vocale in Skype for business](voice-route-configuration-import-export.md).</span><span class="sxs-lookup"><span data-stu-id="c1e1c-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="c1e1c-113">Per rivedere, pubblicare o annullare le modifiche alla configurazione del routing vocale</span><span class="sxs-lookup"><span data-stu-id="c1e1c-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="c1e1c-114">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo di amministratore di **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="c1e1c-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="c1e1c-115">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c1e1c-116">Sulla barra di spostamento sinistra fare clic su **routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="c1e1c-117">Apportare le modifiche di configurazione desiderate alle impostazioni in ogni pagina del gruppo di **routing vocale** .</span><span class="sxs-lookup"><span data-stu-id="c1e1c-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="c1e1c-118">Per rivedere le modifiche in sospeso senza pubblicarle, selezionare **rivedere le modifiche non salvate** dal menu **conferma** .</span><span class="sxs-lookup"><span data-stu-id="c1e1c-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="c1e1c-119">Se si vuole annullare una delle modifiche in sospeso, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1e1c-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="c1e1c-120">Selezionare **Annulla tutte le modifiche non salvate** dal menu **conferma** .</span><span class="sxs-lookup"><span data-stu-id="c1e1c-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="c1e1c-121">Passare alla scheda della pagina di **routing vocale** contenente le modifiche in sospeso che si desidera annullare, selezionare l'elemento con le modifiche in sospeso, fare clic su **commit**e quindi su **Annulla modifiche selezionate**.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="c1e1c-122">Dopo aver esaminato tutte le modifiche in sospeso e annullato qualsiasi che non si vuole pubblicare, fare clic su **commit**e quindi su **commit tutti**.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="c1e1c-123">Nella finestra di dialogo **impostazioni di configurazione vocale non impegnata** , in cui viene visualizzato un elenco di tutte le modifiche in sospeso, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1e1c-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="c1e1c-124">Quando il pannello di controllo di Skype for Business Server ha eseguito il commit delle modifiche, viene visualizzato il messaggio di **configurazione del routing vocale pubblicato correttamente** .</span><span class="sxs-lookup"><span data-stu-id="c1e1c-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

