---
title: Visualizzare le informazioni di configurazione CDR in Skype for Business Server
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
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Riepilogo: informazioni su come usare la registrazione dei dettagli delle chiamate (CDR) in Skype for Business Server.'
ms.openlocfilehash: f4a216f1c2d8892370b80eef42c19cf07c133312
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817595"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="70e07-103">Visualizzare le informazioni di configurazione CDR in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="70e07-103">View CDR configuration information in Skype for Business Server</span></span>
 
<span data-ttu-id="70e07-104">**Riepilogo:** Informazioni su come usare la registrazione dei dettagli delle chiamate (CDR) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="70e07-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="70e07-105">La registrazione dei dettagli delle chiamate (CDR) consente di tenere traccia dell'uso di elementi come sessioni di messaggistica istantanea peer-to-peer, chiamate telefoniche VoIP (Voice over Internet Protocol) e chiamate in conferenza.</span><span class="sxs-lookup"><span data-stu-id="70e07-105">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="70e07-106">Questo dati di utilizzo include informazioni su chi ha chiamato chi, quando ha chiamato, e per quanto tempo ha parlato.</span><span class="sxs-lookup"><span data-stu-id="70e07-106">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="70e07-107">Quando si installa Skype for Business Server, viene creata una singola raccolta globale di impostazioni di configurazione CDR.</span><span class="sxs-lookup"><span data-stu-id="70e07-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="70e07-108">Gli amministratori hanno anche la possibilità di creare raccolte di impostazioni personalizzate che possono essere applicate a singoli siti.</span><span class="sxs-lookup"><span data-stu-id="70e07-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="70e07-109">Per visualizzare le impostazioni di configurazione CDR in uso nell'organizzazione, è possibile usare il pannello di controllo di Skype for Business Server o il cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="70e07-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="70e07-110">Per visualizzare le informazioni di configurazione CDR tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="70e07-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="70e07-111">Nel pannello di controllo di Skype for Business Server fare clic su **monitoraggio e archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="70e07-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="70e07-112">Nella scheda **registrazione dettagli chiamata** verrà visualizzato un elenco di tutte le impostazioni di configurazione CDR. per ogni raccolta di impostazioni verrà visualizzato il **nome**della raccolta; indipendentemente dal fatto che CDR sia stato abilitato (la proprietà **CDR** ); e indipendentemente dal fatto che l'eliminazione sia stata abilitata (la proprietà **cancellazione CDR** ).</span><span class="sxs-lookup"><span data-stu-id="70e07-112">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property).</span></span> <span data-ttu-id="70e07-113">Per visualizzare informazioni dettagliate su una raccolta, fare doppio clic sulla raccolta oppure selezionare la raccolta appropriata, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="70e07-113">To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="70e07-114">Tieni presente che puoi visualizzare solo informazioni dettagliate per una singola raccolta di impostazioni di configurazione CDR alla volta.</span><span class="sxs-lookup"><span data-stu-id="70e07-114">Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="70e07-115">Visualizzazione delle informazioni di configurazione CDR tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="70e07-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="70e07-116">Per visualizzare le impostazioni di configurazione CDR, è possibile usare Windows PowerShell e il cmdlet Get-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="70e07-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="70e07-117">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70e07-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="70e07-118">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="70e07-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="70e07-119">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="70e07-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="70e07-120">Per visualizzare le informazioni sulla configurazione CDR</span><span class="sxs-lookup"><span data-stu-id="70e07-120">To view CDR configuration information</span></span>

- <span data-ttu-id="70e07-121">Per visualizzare informazioni su tutte le impostazioni di configurazione CDR, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="70e07-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="70e07-122">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="70e07-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="70e07-123">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="70e07-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

