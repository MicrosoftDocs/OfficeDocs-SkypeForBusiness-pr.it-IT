---
title: Specificare la conservazione dei dati di registrazione dettagli chiamata in Skype for Business Server
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
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Riepilogo: informazioni su come gestire i dati di registrazione dettagli chiamata (CDR) per Skype for Business Server.'
ms.openlocfilehash: 01b4765a9fa98a898255c1374115e17c4966e797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814216"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="19dbf-103">Specificare la conservazione dei dati di registrazione dettagli chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="19dbf-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="19dbf-104">**Riepilogo:** Informazioni su come gestire i dati di registrazione dettagli chiamata (CDR) per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="19dbf-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="19dbf-p101">Per impostazione predefinita, i dati di registrazione dettagli chiamata vengono eliminati dopo 60 giorni. È possibile utilizzare le impostazioni nella pagina **Registrazione dettagli chiamata** per mantenere i dati per un periodo maggiore o inferiore. Se si disabilita registrazione dettagli chiamata, verranno eliminati anche i dati acquisiti prima dell'abilitazione di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="19dbf-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19dbf-p102">È consigliabile configurare registrazione dettagli chiamata e QoE (Quality of Experience) in modo che mantengano i dati per lo stesso numero di giorni. Ogni chiamata inclusa nei rapporti Dettagli chiamata, disponibili dalla pagina Web dei rapporti di Monitoring Server, include informazioni di registrazione dettagli chiamata e QoE. Se la durata prima dell'eliminazione è diversa, alcune chiamate potrebbero includere solo dati di registrazione dettagli chiamata e altre solo dati QoE.</span><span class="sxs-lookup"><span data-stu-id="19dbf-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="19dbf-111">Nelle procedure seguenti viene descritto come configurare le impostazioni per l'eliminazione dei dati di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="19dbf-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="19dbf-112">Per specificare il periodo di mantenimento dei dati di registrazione dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="19dbf-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="19dbf-113">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="19dbf-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="19dbf-114">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="19dbf-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="19dbf-115">Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Registrazione dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="19dbf-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="19dbf-116">Nella pagina **Registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="19dbf-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="19dbf-117">Per attivare l'eliminazione, selezionare **Abilita eliminazione registrazioni dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="19dbf-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="19dbf-118">In **Mantieni registrazioni dettagli chiamata per durata massima (giorni)** selezionare il numero massimo di giorni per cui mantenere le registrazioni dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="19dbf-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="19dbf-119">In **Mantieni dati delle segnalazioni errori per durata massima (giorni)** selezionare il numero massimo di giorni per cui mantenere le segnalazioni degli errori.</span><span class="sxs-lookup"><span data-stu-id="19dbf-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="19dbf-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="19dbf-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="19dbf-121">Impostazione della conservazione CDR tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="19dbf-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="19dbf-122">È possibile creare le impostazioni di mantenimento delle registrazioni dettagli chiamata utilizzando Windows PowerShell e il cmdlet Set-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="19dbf-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="19dbf-123">È possibile eseguire questo cmdlet sia da Skype for Business Server Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19dbf-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="19dbf-124">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo del Blog ["Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="19dbf-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="19dbf-125">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="19dbf-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="19dbf-126">Per specificare il mantenimento delle registrazioni dettagli chiamata per una posizione specifica</span><span class="sxs-lookup"><span data-stu-id="19dbf-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="19dbf-127">Questo comando consente di abilitare l'eliminazione dei dati delle registrazioni dettagli chiamata per il sito Redmond e di configurare il sito per mantenere sia tali dati che le segnalazioni di errore per 20 giorni.</span><span class="sxs-lookup"><span data-stu-id="19dbf-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="19dbf-128">Per specificare il mantenimento delle registrazioni dettagli chiamata per più posizioni</span><span class="sxs-lookup"><span data-stu-id="19dbf-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="19dbf-129">Questo comando consente di configurare il mantenimento delle registrazioni dettagli chiamata per tutte le impostazioni di configurazione di tali registrazioni in uso in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="19dbf-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="19dbf-130">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="19dbf-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="19dbf-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19dbf-131">See also</span></span>

[<span data-ttu-id="19dbf-132">Registrazione dettagli chiamata (CDR) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="19dbf-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)
