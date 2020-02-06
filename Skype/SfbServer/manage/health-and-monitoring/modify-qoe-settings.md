---
title: Modificare le impostazioni di qualità delle esperienze in Skype for Business Server
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
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Riepilogo: informazioni su come specificare la conservazione dei dati QoE in Skype for Business Server.'
ms.openlocfilehash: a7f8173518d12daffb23658f5b81fa35b39d13da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817845"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="dd0ab-103">Modificare le impostazioni di qualità delle esperienze in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd0ab-103">Modify Quality of Experience settings in Skype for Business Server</span></span>

<span data-ttu-id="dd0ab-104">**Riepilogo:** Informazioni su come specificare la conservazione dei dati QoE in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>

<span data-ttu-id="dd0ab-105">Per impostazione predefinita, i dati di qualità dell'esperienza (QoE) vengono eliminati dopo 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-105">By default, Quality of Experience (QoE) data is purged after 60 days.</span></span> <span data-ttu-id="dd0ab-106">Per mantenere i dati per un periodo di tempo più lungo o più breve, è possibile usare le impostazioni nella pagina di **dati qualità della prova** .</span><span class="sxs-lookup"><span data-stu-id="dd0ab-106">You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time.</span></span> <span data-ttu-id="dd0ab-107">Se si disattiva QoE, anche i dati acquisiti prima dell'abilitazione di QoE saranno soggetti all'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-107">If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

> [!NOTE]
> <span data-ttu-id="dd0ab-108">Devi configurare la registrazione dei dettagli delle chiamate (CDR) e QoE per mantenere i dati per lo stesso numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-108">You should configure call detail recording (CDR) and QoE to retain data for the same number of days.</span></span> <span data-ttu-id="dd0ab-109">Ogni chiamata nei report dettagli chiamata (CDRs), disponibile nella Home page dei report di monitoraggio, include informazioni CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-109">Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information.</span></span> <span data-ttu-id="dd0ab-110">Se la durata di eliminazione per CDR e QoE è diversa, alcune chiamate possono includere solo dati CDR, mentre altre possono includere solo dati QoE.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-110">If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>

<span data-ttu-id="dd0ab-111">La procedura seguente descrive come configurare le impostazioni di eliminazione dei dati QoE.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-111">The following procedure describes how to configure purge settings for QoE data.</span></span>

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="dd0ab-112">Per specificare la conservazione dei dati QoE usando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd0ab-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="dd0ab-113">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="dd0ab-114">Per informazioni dettagliate, vedere **delegare le autorizzazioni di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-114">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="dd0ab-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="dd0ab-116">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="dd0ab-117">Nella pagina **qualità di dati esperienza** fare clic sul sito appropriato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5. <span data-ttu-id="dd0ab-118">Per attivare l'eliminazione, selezionare **Abilita l'eliminazione di QoE**.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6. <span data-ttu-id="dd0ab-119">In **Mantieni QoE per la durata massima (giorni)** selezionare il numero massimo di giorni in cui devono essere conservati i dati QoE.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7. <span data-ttu-id="dd0ab-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-120">Click **Commit**.</span></span>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dd0ab-121">Specifica della conservazione QoE usando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd0ab-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dd0ab-122">È possibile creare impostazioni di conservazione QoE usando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="dd0ab-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="dd0ab-123">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dd0ab-124">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="dd0ab-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="dd0ab-125">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-125">The process is the same in Skype for Business Server.</span></span>

### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="dd0ab-126">Per specificare la conservazione QoE per una posizione specifica</span><span class="sxs-lookup"><span data-stu-id="dd0ab-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="dd0ab-127">Questo comando consente l'eliminazione dei dati QoE per il sito Redmond e configura il sito per la gestione dei dati QoE per 20 giorni.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="dd0ab-128">Per specificare la conservazione QoE per più posizioni</span><span class="sxs-lookup"><span data-stu-id="dd0ab-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="dd0ab-129">Questo comando configura la conservazione QoE per tutte le impostazioni di configurazione QoE in uso in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd0ab-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

<span data-ttu-id="dd0ab-130">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="dd0ab-130">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd0ab-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd0ab-131">See also</span></span>

[<span data-ttu-id="dd0ab-132">Distribuzione del monitoraggio</span><span class="sxs-lookup"><span data-stu-id="dd0ab-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
