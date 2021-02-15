---
title: Pubblicare modifiche in sospeso nella configurazione del routing vocale in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Riepilogo: informazioni su come rivedere, pubblicare o annullare le modifiche alla configurazione del routing vocale in Skype for Business Server utilizzando il Pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: 6b75b6a1135cf9abde9551112fc9c29579862a8b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830396"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="bb492-103">Pubblicare modifiche in sospeso nella configurazione del routing vocale in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bb492-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="bb492-104">**Riepilogo:** Informazioni su come rivedere, pubblicare o annullare le modifiche alla configurazione del routing vocale in Skype for Business Server utilizzando il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bb492-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="bb492-105">Dopo aver apportato modifiche alle impostazioni di configurazione nelle pagine del gruppo **Routing vocale**, eseguire questa procedura per esaminare, pubblicare o annullare le modifiche in sospeso.</span><span class="sxs-lookup"><span data-stu-id="bb492-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bb492-106">Verificare che un solo utente alla volta modifichi le impostazioni di configurazione di Routing vocale.</span><span class="sxs-lookup"><span data-stu-id="bb492-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bb492-p101">Tutte le modifiche in sospeso devono essere pubblicate contemporaneamente eseguendo il comando **Salva tutto**. Non è possibile pubblicare selettivamente le modifiche in sospeso. Prima di pubblicare le modifiche in sospeso, eseguire il comando **Rivedi modifiche di cui non è stato eseguito il commit** e annullare qualsiasi modifica di configurazione che non si desidera pubblicare.</span><span class="sxs-lookup"><span data-stu-id="bb492-p101">All pending changes must be published at the same time by running the **Commit all** command. You cannot selectively publish pending changes. Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb492-110">Se si esce dalle pagine del gruppo **Routing vocale** prima di eseguire il commit delle modifiche in sospeso, tutte le modifiche in sospeso andranno perse.</span><span class="sxs-lookup"><span data-stu-id="bb492-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="bb492-111">Tuttavia, è possibile esportare la configurazione corrente (incluse le modifiche in sospeso) in un file di configurazione vocale e quindi importare e pubblicare la configurazione aggiornata.</span><span class="sxs-lookup"><span data-stu-id="bb492-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="bb492-112">Per informazioni dettagliate, vedere [Esportare o importare un file di](voice-route-configuration-import-export.md)configurazione della route vocale in Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="bb492-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="bb492-113">Per rivedere, pubblicare o annullare le modifiche di configurazione del routing vocale</span><span class="sxs-lookup"><span data-stu-id="bb492-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="bb492-114">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator,** **CsServerAdministrator** o **CsAdministrator.**</span><span class="sxs-lookup"><span data-stu-id="bb492-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="bb492-115">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bb492-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="bb492-116">Sulla barra di spostamento sinistra fare clic su **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="bb492-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="bb492-117">Apportare le modifiche della configurazione desiderate alle impostazioni in ogni pagina del gruppo **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="bb492-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="bb492-118">Per rivedere le modifiche in sospeso senza pubblicarle, scegliere **Rivedi modifiche di cui non è stato eseguito il commit** dal menu **Commit**.</span><span class="sxs-lookup"><span data-stu-id="bb492-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="bb492-119">Se si desidera annullare qualsiasi modifica in sospeso, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb492-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="bb492-120">Scegliere **Annulla tutte le modifiche di cui non è stato eseguito il commit** dal menu **Commit**.</span><span class="sxs-lookup"><span data-stu-id="bb492-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="bb492-121">Spostarsi sulla scheda della pagina **Routing vocale** che include le modifiche in sospeso che si desidera annullare, selezionare l'elemento con le modifiche in sospeso, fare clic su **Commit** e quindi su **Annulla modifiche selezionate**.</span><span class="sxs-lookup"><span data-stu-id="bb492-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="bb492-122">Dopo aver rivisto tutte le modifiche in sospeso e annullato ogni modifica che non si desidera pubblicare, fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="bb492-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="bb492-123">Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** in cui è visualizzato un elenco delle modifiche in sospeso fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb492-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="bb492-124">Quando il Pannello di controllo di Skype for Business Server ha eseguito il commit delle modifiche, viene visualizzato il messaggio **Configurazione routing vocale** pubblicato correttamente.</span><span class="sxs-lookup"><span data-stu-id="bb492-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

