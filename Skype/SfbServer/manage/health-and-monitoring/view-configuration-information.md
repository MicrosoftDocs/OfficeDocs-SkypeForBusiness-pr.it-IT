---
title: Visualizzare le informazioni di configurazione di registrazione dettagli chiamata in Skype for Business Server
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
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Riepilogo: informazioni su come utilizzare registrazione dettagli chiamata (CDR) in Skype for Business Server.'
ms.openlocfilehash: 55e5e4e2f1b9d3d54ecb6a4a2614b2b1d206f2fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816636"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="df79a-103">Visualizzare le informazioni di configurazione di registrazione dettagli chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="df79a-103">View CDR configuration information in Skype for Business Server</span></span>
 
<span data-ttu-id="df79a-104">**Riepilogo:** Informazioni su come utilizzare registrazione dettagli chiamata (CDR) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="df79a-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="df79a-p101">La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo delle sessioni di messaggistica istantanea peer-to-peer, delle chiamate telefoniche VoIP (Voice over Internet Protocol) e delle conferenze telefoniche. Questi dati sull'utilizzo includono informazioni sui chiamanti, sugli utenti chiamati, sulla data della chiamata e sulla durata della conversazione.</span><span class="sxs-lookup"><span data-stu-id="df79a-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="df79a-107">Quando si installa Skype for Business Server, viene creata una singola raccolta globale di impostazioni di configurazione di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="df79a-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="df79a-108">Gli amministratori hanno inoltre la possibilità di creare raccolte di impostazioni personalizzate da applicare ai siti individuali.</span><span class="sxs-lookup"><span data-stu-id="df79a-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="df79a-109">È possibile visualizzare le impostazioni di configurazione di registrazione dettagli chiamata in uso nell'organizzazione utilizzando il pannello di controllo di Skype for Business Server o il cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="df79a-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="df79a-110">Per visualizzare le informazioni sulla configurazione di registrazione dettagli chiamata tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="df79a-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="df79a-111">Nel pannello di controllo di Skype for Business Server fare clic su **monitoraggio e archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="df79a-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="df79a-p103">Nella scheda **Registrazione dettagli chiamata** viene visualizzato un elenco delle impostazioni di configurazione per la registrazione dettagli chiamata; per ciascuna raccolta di impostazioni comparirà il **Nome** della raccolta, se la Registrazione dettagli chiamata è abilitata o meno (la proprietà **CDR** property), e se l'eliminazione è abilitata (la proprietà **Eliminazione CDR**). Per visualizzare informazioni dettagliate su una raccolta, fare doppio clic sulla raccolta o selezionare la raccolta appropriata, fare clic su **Modifica** e quindi su **Mostra dettagli**. Si noti che è possibile visualizzare le informazioni dettagliate per una raccolta singola di impostazioni di configurazione per la registrazione dettagli chiamata alla volta.</span><span class="sxs-lookup"><span data-stu-id="df79a-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="df79a-115">Visualizzazione delle informazioni di configurazione di registrazione dettagli chiamata tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df79a-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="df79a-116">È possibile visualizzare le impostazioni di configurazione di registrazione dettagli chiamata utilizzando Windows PowerShell e il cmdlet Get-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="df79a-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="df79a-117">È possibile eseguire questo cmdlet sia da Skype for Business Server Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df79a-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="df79a-118">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo del Blog ["Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="df79a-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="df79a-119">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="df79a-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="df79a-120">Visualizzare le informazioni di configurazione della registrazione dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="df79a-120">To view CDR configuration information</span></span>

- <span data-ttu-id="df79a-121">Per visualizzare informazioni su tutte le impostazioni di configurazione di registrazione dettagli chiamata, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="df79a-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="df79a-122">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="df79a-122">That will return information similar to this:</span></span>
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

<span data-ttu-id="df79a-123">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="df79a-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

