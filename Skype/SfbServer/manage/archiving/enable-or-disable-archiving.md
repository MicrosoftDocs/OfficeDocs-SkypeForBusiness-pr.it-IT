---
title: Abilitare o disabilitare l'archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: "Riepilogo: informazioni su come abilitare o disabilitare l'archiviazione in Skype for Business Server."
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817596"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="17f3d-103">Abilitare o disabilitare l'archiviazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="17f3d-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="17f3d-104">**Riepilogo:** Informazioni su come abilitare o disabilitare l'archiviazione in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="17f3d-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="17f3d-105">Abilitare o disabilitare l'archiviazione tramite il Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="17f3d-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="17f3d-106">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="17f3d-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="17f3d-107">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="17f3d-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="17f3d-108">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="17f3d-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="17f3d-109">Selezionare la configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **Modifica**, su **Mostra dettagli** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="17f3d-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="17f3d-110">Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea, fare clic su **Archivia sessioni di messaggistica istantanea**.</span><span class="sxs-lookup"><span data-stu-id="17f3d-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="17f3d-111">Per abilitare l'archiviazione per le sessioni di messaggistica istantanea e le conferenze, fare clic su **Archivia sessioni di messaggistica istantanea e Web Conferencing**.</span><span class="sxs-lookup"><span data-stu-id="17f3d-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="17f3d-112">Per disabilitare l'archiviazione per la configurazione, fare clic **su Disabilita archiviazione.**</span><span class="sxs-lookup"><span data-stu-id="17f3d-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="17f3d-113">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="17f3d-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="17f3d-114">Abilitare o disabilitare l'archiviazione tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="17f3d-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="17f3d-115">È inoltre possibile abilitare o disabilitare l'archiviazione utilizzando il cmdlet **Set-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="17f3d-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="17f3d-116">Ad esempio, il comando seguente modifica tutte le impostazioni di configurazione dell'archiviazione in modo che solo le sessioni di messaggistica istantanea siano archiviate.</span><span class="sxs-lookup"><span data-stu-id="17f3d-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="17f3d-117">Il comando chiama il cmdlet **Get-CsArchivingConfiguration** senza alcun parametro per restituire tutte le impostazioni di configurazione dell'archiviazione attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="17f3d-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="17f3d-118">La raccolta viene quindi reindirizzata al cmdlet **Where-Object,** che seleziona solo le impostazioni in cui la proprietà EnableArchiving è uguale a (-eq) "ImAndWebConf".</span><span class="sxs-lookup"><span data-stu-id="17f3d-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="17f3d-119">La raccolta filtrata viene quindi reindirizzata al cmdlet **Set-CsArchivingConfiguration,** che accetta ogni elemento della raccolta e modifica il valore di EnableArchiving in "ImOnly":</span><span class="sxs-lookup"><span data-stu-id="17f3d-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
