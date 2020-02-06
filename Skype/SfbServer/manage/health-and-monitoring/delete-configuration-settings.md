---
title: Eliminare una raccolta esistente di impostazioni di configurazione CDR in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Riepilogo: informazioni su come rimuovere le impostazioni di configurazione CDR in Skype for Business Server.'
ms.openlocfilehash: d9e990018d97f8e631f3a95718a76aa83d7d619e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818026"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="bbf85-103">Eliminare una raccolta esistente di impostazioni di configurazione CDR in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bbf85-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="bbf85-104">**Riepilogo:** Informazioni su come rimuovere le impostazioni di configurazione CDR in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bbf85-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="bbf85-105">La registrazione dei dettagli delle chiamate (CDR) consente di tenere traccia dell'uso di elementi come sessioni di messaggistica istantanea peer-to-peer, chiamate telefoniche VoIP (Voice over Internet Protocol) e chiamate in conferenza.</span><span class="sxs-lookup"><span data-stu-id="bbf85-105">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="bbf85-106">Questo dati di utilizzo include informazioni su chi ha chiamato chi, quando ha chiamato, e per quanto tempo ha parlato.</span><span class="sxs-lookup"><span data-stu-id="bbf85-106">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="bbf85-107">Quando si installa Skype for Business Server, viene creata una singola raccolta globale di impostazioni di configurazione CDR.</span><span class="sxs-lookup"><span data-stu-id="bbf85-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="bbf85-108">Gli amministratori hanno anche la possibilità di creare raccolte di impostazioni personalizzate che possono essere applicate a singoli siti.</span><span class="sxs-lookup"><span data-stu-id="bbf85-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="bbf85-109">In base alla progettazione, le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="bbf85-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="bbf85-110">Se si eliminano le impostazioni con ambito sito, il CDR verrà gestito in tale sito usando le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="bbf85-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="bbf85-111">Tieni presente che puoi anche "eliminare" le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="bbf85-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="bbf85-112">Tuttavia, le impostazioni globali non verranno effettivamente rimosse.</span><span class="sxs-lookup"><span data-stu-id="bbf85-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="bbf85-113">Tutte le proprietà della raccolta verranno invece reimpostate sui rispettivi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="bbf85-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="bbf85-114">Ad esempio, per impostazione predefinita, l'eliminazione è abilitata in una raccolta di impostazioni di configurazione CDR.</span><span class="sxs-lookup"><span data-stu-id="bbf85-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="bbf85-115">Supponiamo che tu modifichi la raccolta globale in modo che l'eliminazione sia disabilitata.</span><span class="sxs-lookup"><span data-stu-id="bbf85-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="bbf85-116">Se in seguito si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="bbf85-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="bbf85-117">In questo caso, ciò significa che l'eliminazione sarà ancora una volta abilitata.</span><span class="sxs-lookup"><span data-stu-id="bbf85-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="bbf85-118">È possibile rimuovere le impostazioni di configurazione CDR usando il pannello di controllo di Skype for Business Server o il cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="bbf85-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="bbf85-119">Per rimuovere le impostazioni di configurazione CDR con il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bbf85-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="bbf85-120">Nel pannello di controllo di Skype for Business Server fare clic su **monitoraggio e archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="bbf85-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="bbf85-121">Nella scheda **registrazione dettagli chiamata** selezionare la raccolta (o le raccolte) delle impostazioni CDR da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="bbf85-121">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed.</span></span> <span data-ttu-id="bbf85-122">Per selezionare più raccolte, fare clic sulla prima raccolta, tenere premuto il tasto CTRL e fare clic su altre raccolte.</span><span class="sxs-lookup"><span data-stu-id="bbf85-122">To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="bbf85-123">Fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="bbf85-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="bbf85-124">Nella finestra di dialogo Pannello di controllo di Skype for Business Server fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bbf85-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bbf85-125">Rimozione delle impostazioni di configurazione CDR con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbf85-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bbf85-126">Puoi eliminare le impostazioni di configurazione della registrazione dei dettagli delle chiamate usando Windows PowerShell e il cmdlet **Remove-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="bbf85-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="bbf85-127">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbf85-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bbf85-128">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="bbf85-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="bbf85-129">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bbf85-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="bbf85-130">Per rimuovere una raccolta specificata di impostazioni di configurazione CDR</span><span class="sxs-lookup"><span data-stu-id="bbf85-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="bbf85-131">Questo comando rimuove le impostazioni di configurazione CDR applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="bbf85-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="bbf85-132">Per rimuovere tutte le impostazioni di configurazione CDR applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="bbf85-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="bbf85-133">Questo comando rimuove tutte le impostazioni di configurazione CDR applicate all'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="bbf85-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="bbf85-134">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="bbf85-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bbf85-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbf85-135">See also</span></span>

[<span data-ttu-id="bbf85-136">Eliminare manualmente la registrazione dei dettagli delle chiamate e i database di qualità dell'esperienza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bbf85-136">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

