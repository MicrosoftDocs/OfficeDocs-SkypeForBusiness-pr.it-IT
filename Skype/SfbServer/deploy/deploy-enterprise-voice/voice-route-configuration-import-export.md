---
title: Esportare o importare un file di configurazione della route vocale in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Riepilogo: informazioni su come esportare o importare un file di configurazione del routing vocale in Skype for Business Server tramite il pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: ec5a3d0c7f14d85a7b64eaad1edc73ebe4e24cd2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240170"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="1775c-103">Esportare o importare un file di configurazione della route vocale in Skype for business</span><span class="sxs-lookup"><span data-stu-id="1775c-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="1775c-104">**Riepilogo:** Informazioni su come esportare o importare un file di configurazione del routing vocale in Skype for Business Server tramite il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1775c-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="1775c-105">Se si vuole salvare la configurazione del routing vocale senza pubblicarla, seguire questa procedura per salvare e recuperare uno snapshot della configurazione del routing vocale.</span><span class="sxs-lookup"><span data-stu-id="1775c-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="1775c-106">Quando si importa un file di configurazione del routing vocale (con estensione vcfg), ma nel frattempo sono state apportate modifiche alla configurazione del routing vocale nel server, le pagine del gruppo **routing vocale** nel pannello di controllo di Skype for Business Server indicheranno che le modifiche apportate al routing vocale non vengono salvate.</span><span class="sxs-lookup"><span data-stu-id="1775c-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="1775c-107">Le modifiche non salvate sono le differenze tra le due configurazioni che richiedono la riconciliazione.</span><span class="sxs-lookup"><span data-stu-id="1775c-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="1775c-108">Se sono state apportate modifiche non salvate alle impostazioni di una pagina all'interno del gruppo, le modifiche vengono salvate nel file di configurazione vocale esportato (. vcfg).</span><span class="sxs-lookup"><span data-stu-id="1775c-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="1775c-109">In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante più sessioni prima di pubblicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1775c-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="1775c-110">Per esportare una configurazione di routing vocale</span><span class="sxs-lookup"><span data-stu-id="1775c-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="1775c-111">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo di amministratore di **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="1775c-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="1775c-112">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1775c-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1775c-113">Sulla barra di spostamento sinistra fare clic su **routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="1775c-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="1775c-114">Nel menu **azioni** fare clic su **Esporta configurazione**.</span><span class="sxs-lookup"><span data-stu-id="1775c-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="1775c-115">Specificare un percorso e un nome file e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1775c-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="1775c-116">Per importare una configurazione di routing vocale</span><span class="sxs-lookup"><span data-stu-id="1775c-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="1775c-117">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo di amministratore di **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="1775c-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="1775c-118">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1775c-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1775c-119">Sulla barra di spostamento sinistra fare clic su **routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="1775c-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="1775c-120">Nel menu **azioni** fare clic su **Importa configurazione**.</span><span class="sxs-lookup"><span data-stu-id="1775c-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="1775c-121">Individuare il file di configurazione da importare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="1775c-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="1775c-122">Fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="1775c-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1775c-123">Ogni volta che si importa un file di configurazione vocale, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="1775c-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="1775c-124">Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="1775c-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

