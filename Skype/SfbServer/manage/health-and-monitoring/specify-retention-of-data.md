---
title: Specificare la conservazione dei dati CDR in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Riepilogo: informazioni su come gestire i dati di registrazione dei dettagli delle chiamate (CDR) per Skype for Business Server.'
ms.openlocfilehash: a775098a4c41bccca42fe1d95c5f1dbf0d22f2bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188675"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="f54ab-103">Specificare la conservazione dei dati CDR in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f54ab-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="f54ab-104">**Riepilogo:** Informazioni su come gestire i dati di registrazione dei dettagli delle chiamate (CDR) per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f54ab-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="f54ab-105">Per impostazione predefinita, i dati della registrazione dei dettagli delle chiamate (CDR) vengono eliminati dopo 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="f54ab-105">By default, call detail recording (CDR) data is purged after 60 days.</span></span> <span data-ttu-id="f54ab-106">È possibile usare le impostazioni nella pagina **registrazione dettagli chiamata** per mantenere i dati per un periodo di tempo più lungo o più breve.</span><span class="sxs-lookup"><span data-stu-id="f54ab-106">You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time.</span></span> <span data-ttu-id="f54ab-107">Se si disattiva CDR, anche i dati acquisiti prima dell'abilitazione di CDR saranno soggetti all'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="f54ab-107">If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f54ab-108">È necessario configurare CDR e la qualità dell'esperienza (QoE) per mantenere i dati per lo stesso numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="f54ab-108">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days.</span></span> <span data-ttu-id="f54ab-109">Ogni chiamata nei report dettagli chiamata (CDRs), disponibile dalla pagina Web monitoraggio report server, include informazioni CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="f54ab-109">Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information.</span></span> <span data-ttu-id="f54ab-110">Se la durata di eliminazione per CDR e QoE è diversa, alcune chiamate potrebbero includere solo dati CDR, mentre altre possono includere solo dati QoE.</span><span class="sxs-lookup"><span data-stu-id="f54ab-110">If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="f54ab-111">Usare le procedure seguenti per configurare le impostazioni di eliminazione dei dati CDR.</span><span class="sxs-lookup"><span data-stu-id="f54ab-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="f54ab-112">Per specificare la conservazione dei dati CDR</span><span class="sxs-lookup"><span data-stu-id="f54ab-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="f54ab-113">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="f54ab-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="f54ab-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f54ab-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f54ab-115">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **registrazione dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="f54ab-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="f54ab-116">Nella pagina **registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f54ab-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="f54ab-117">Per attivare l'eliminazione, selezionare **Abilita l'eliminazione di CDRS**.</span><span class="sxs-lookup"><span data-stu-id="f54ab-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="f54ab-118">In **Mantieni CDRS per la durata massima (giorni):** selezionare il numero massimo di giorni in cui le registrazioni dei dettagli delle chiamate devono essere mantenute.</span><span class="sxs-lookup"><span data-stu-id="f54ab-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="f54ab-119">In **Mantieni i dati del report sugli errori per la durata massima (giorni):** selezionare il numero massimo di giorni in cui devono essere mantenuti i report degli errori.</span><span class="sxs-lookup"><span data-stu-id="f54ab-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="f54ab-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f54ab-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f54ab-121">Specifica della conservazione CDR con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f54ab-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f54ab-122">È possibile creare impostazioni di conservazione CDR tramite Windows PowerShell e il cmdlet Set-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f54ab-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="f54ab-123">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f54ab-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f54ab-124">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="f54ab-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f54ab-125">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f54ab-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="f54ab-126">Per specificare la conservazione CDR per una posizione specifica</span><span class="sxs-lookup"><span data-stu-id="f54ab-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="f54ab-127">Questo comando consente l'eliminazione dei dati CDR per il sito Redmond e configura il sito per la gestione dei dati CDR e dei rapporti di errore per 20 giorni.</span><span class="sxs-lookup"><span data-stu-id="f54ab-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="f54ab-128">Per specificare la conservazione CDR per più posizioni</span><span class="sxs-lookup"><span data-stu-id="f54ab-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="f54ab-129">Questo comando configura la conservazione CDR per tutte le impostazioni di configurazione CDR in uso in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f54ab-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="f54ab-130">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f54ab-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f54ab-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f54ab-131">See also</span></span>

[<span data-ttu-id="f54ab-132">Registrazione dei dettagli delle chiamate (CDR) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f54ab-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)
