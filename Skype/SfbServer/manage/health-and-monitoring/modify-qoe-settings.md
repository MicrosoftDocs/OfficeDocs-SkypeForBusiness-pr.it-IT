---
title: Modificare le impostazioni di qualità dell'esperienza in Skype for Business Server
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
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Riepilogo: informazioni su come specificare la conservazione dei dati QoE in Skype for Business Server.'
ms.openlocfilehash: 18776e9b8eec9dcff6ced9f654d8153d7fa01777
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827796"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="9eb7a-103">Modificare le impostazioni di qualità dell'esperienza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9eb7a-103">Modify Quality of Experience settings in Skype for Business Server</span></span>

<span data-ttu-id="9eb7a-104">**Riepilogo:** Informazioni su come specificare la conservazione dei dati QoE in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>

<span data-ttu-id="9eb7a-p101">Per impostazione predefinita, i dati relativi alla QoE (Quality of Experience) vengono eliminati dopo 60 giorni. È possibile utilizzare le impostazioni nella pagina **Dati QoE** per conservare i dati per un periodo superiore o inferiore. Se si disabilita la funzionalità QoE, verranno eliminati anche i dati acquisiti prima dell'abilitazione di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

> [!NOTE]
> <span data-ttu-id="9eb7a-p102">È consigliabile configurare la registrazione dettagli chiamata (CDR, Call Detail Recording) e QoE in modo che mantengano i dati per lo stesso numero di giorni. Ogni chiamata inclusa nei rapporti Dettagli chiamata, disponibili dalla home page dei rapporti di monitoraggio, include informazioni di registrazione dettagli chiamata e QoE. Se il periodo che precede l'eliminazione è diverso, alcune chiamate potrebbero includere solo dati di registrazione dettagli chiamata e altre solo dati QoE.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>

<span data-ttu-id="9eb7a-111">Nella procedura seguente viene descritto come configurare le impostazioni per l'eliminazione dei dati QoE.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-111">The following procedure describes how to configure purge settings for QoE data.</span></span>

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9eb7a-112">Per specificare la conservazione dei dati QoE tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9eb7a-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9eb7a-p103">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-p103">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="9eb7a-115">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="9eb7a-116">Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="9eb7a-117">Nella pagina **Dati QoE** fare clic sul sito appropriato nella tabella, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5. <span data-ttu-id="9eb7a-118">Per abilitare l'eliminazione, selezionare **Abilita eliminazione dei dati QoE**.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6. <span data-ttu-id="9eb7a-119">In **Mantieni dati QoE per durata massima (giorni)** selezionare il numero massimo di giorni per cui mantenere i dati QoE.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7. <span data-ttu-id="9eb7a-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-120">Click **Commit**.</span></span>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9eb7a-121">Impostazione della conservazione QoE tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="9eb7a-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9eb7a-122">È possibile creare le impostazioni di conservazione QoE utilizzando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="9eb7a-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="9eb7a-123">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9eb7a-124">Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="9eb7a-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9eb7a-125">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-125">The process is the same in Skype for Business Server.</span></span>

### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="9eb7a-126">Per specificare il mantenimento dei dati QoE per una posizione specifica</span><span class="sxs-lookup"><span data-stu-id="9eb7a-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="9eb7a-127">Questo comando consente di abilitare l'eliminazione dei dati QoE per il sito Redmond e di configurare il sito per mantenere i dati QoE per 20 giorni.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="9eb7a-128">Per specificare il mantenimento dei dati QoE per più posizioni</span><span class="sxs-lookup"><span data-stu-id="9eb7a-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="9eb7a-129">Questo comando consente di configurare il mantenimento dei dati QoE per tutte le impostazioni di configurazione QoE in uso in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9eb7a-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

<span data-ttu-id="9eb7a-130">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9eb7a-130">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="9eb7a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9eb7a-131">See also</span></span>

[<span data-ttu-id="9eb7a-132">Distribuzione del monitoraggio</span><span class="sxs-lookup"><span data-stu-id="9eb7a-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
