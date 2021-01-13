---
title: Configurare le opzioni di archiviazione per gestire gli errori in Skype for Business Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: "Riepilogo: informazioni su come bloccare le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Skype for Business Server che impediva l'archiviazione."
ms.openlocfilehash: 9a39c5f54fbdd4a738f4e67e7f70ff199a204672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817676"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="93ac5-103">Configurare le opzioni di archiviazione per gestire gli errori in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="93ac5-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="93ac5-104">**Riepilogo:** Informazioni su come bloccare le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Skype for Business Server che impediva l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="93ac5-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="93ac5-105">Se l'archiviazione è un requisito per la propria organizzazione, è possibile bloccare le sessioni di messaggistica istantanea e di conferenza nel caso di un errore di Skype for Business Server che impediva l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="93ac5-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="93ac5-106">A volte viene chiamata modalità critica.</span><span class="sxs-lookup"><span data-stu-id="93ac5-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="93ac5-107">Ad esempio, se si verifica un problema con un servizio di archiviazione, la messaggistica istantanea verrebbe bloccata per gli utenti le cui comunicazioni sono abilitate per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="93ac5-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="93ac5-108">Sia la funzionalità di messaggistica immediata che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori.</span><span class="sxs-lookup"><span data-stu-id="93ac5-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="93ac5-109">Configurazione della modalità critica tramite il pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="93ac5-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="93ac5-110">Per specificare se le sessioni di comunicazione devono essere consentite in caso di errori che impediscono l'archiviazione:</span><span class="sxs-lookup"><span data-stu-id="93ac5-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="93ac5-111">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="93ac5-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="93ac5-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="93ac5-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="93ac5-113">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="93ac5-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="93ac5-114">Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="93ac5-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="93ac5-115">Per impostare la modalità di funzionamento dell'archiviazione quando si verifica un errore, selezionare o deselezionare la casella di controllo **blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce** .</span><span class="sxs-lookup"><span data-stu-id="93ac5-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="93ac5-116">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="93ac5-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="93ac5-117">Configurare la modalità critica tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="93ac5-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="93ac5-118">È inoltre possibile specificare se le sessioni di comunicazione devono essere consentite in caso di errori che impediscono l'archiviazione utilizzando il cmdlet **Set-CsArchivingConfiguration** con il parametro BlockOnArchiveFailure.</span><span class="sxs-lookup"><span data-stu-id="93ac5-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="93ac5-119">Ad esempio, il comando seguente disattiva le comunicazioni nel caso di un errore di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="93ac5-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="93ac5-120">Il comando seguente consente di abilitare le comunicazioni nel caso di un errore di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="93ac5-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="93ac5-121">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="93ac5-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

