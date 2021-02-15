---
title: Esportare o importare un file di configurazione della route vocale in Skype for Business
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Riepilogo: informazioni su come esportare o importare un file di configurazione del routing vocale in Skype for Business Server utilizzando il Pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: df5ca58ebc7b92fea5236b957f4819ed3602d896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830356"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="3bfb7-103">Esportare o importare un file di configurazione della route vocale in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3bfb7-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="3bfb7-104">**Riepilogo:** Informazioni su come esportare o importare un file di configurazione del routing vocale in Skype for Business Server utilizzando il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="3bfb7-105">Se si desidera salvare la configurazione del routing vocale senza pubblicarla, eseguire la procedura seguente per salvare e recuperare uno snapshot della configurazione del routing vocale.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="3bfb7-106">Quando si importa un file di configurazione del routing vocale (con estensione vcfg), ma nel frattempo  sono state apportate modifiche alla configurazione del routing vocale sul server, le pagine del gruppo di routing vocale nel Pannello di controllo di Skype for Business Server indicheranno che sono state apportate modifiche di cui non è stato eseguito ilcommitted al routing vocale.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="3bfb7-107">Tali modifiche costituiscono le differenze tra le due configurazioni di cui deve essere eseguita la riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="3bfb7-108">Se sono state apportate modifiche non salvate alle impostazioni in qualsiasi pagina del gruppo, le modifiche vengono salvate nel file di configurazione vocale esportato (con estensione vcfg).</span><span class="sxs-lookup"><span data-stu-id="3bfb7-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="3bfb7-109">In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante più sessioni prima di pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="3bfb7-110">Per esportare una configurazione di routing vocale</span><span class="sxs-lookup"><span data-stu-id="3bfb7-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="3bfb7-111">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator,** **CsServerAdministrator** o **CsAdministrator.**</span><span class="sxs-lookup"><span data-stu-id="3bfb7-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="3bfb7-112">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3bfb7-113">Nella barra di spostamento sinistra fare clic su **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="3bfb7-114">Scegliere **Esporta configurazione** dal menu **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="3bfb7-115">Specificare un percorso e un nome di file e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="3bfb7-116">Per importare una configurazione di routing vocale</span><span class="sxs-lookup"><span data-stu-id="3bfb7-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="3bfb7-117">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator,** **CsServerAdministrator** o **CsAdministrator.**</span><span class="sxs-lookup"><span data-stu-id="3bfb7-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="3bfb7-118">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3bfb7-119">Sulla barra di spostamento sinistra fare clic su **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="3bfb7-120">Scegliere **Importa configurazione** dal menu **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="3bfb7-121">Trovare il file di configurazione che si desidera importare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="3bfb7-122">Fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3bfb7-123">Ogni volta che si importa un file di configurazione vocale, è necessario usare il comando **Salva tutto** per pubblicare la modifica di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="3bfb7-124">Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="3bfb7-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

