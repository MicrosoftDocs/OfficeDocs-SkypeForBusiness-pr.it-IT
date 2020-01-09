---
title: Abilitare la qualità dell'esperienza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: "Riepilogo: informazioni su come abilitare la qualità dell'esperienza (QoE) in Skype for Business Server."
ms.openlocfilehash: 0a05266ed88b9d476ca787f1d32b91727e90475c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992936"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="80f2b-103">Abilitare la qualità dell'esperienza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="80f2b-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="80f2b-104">**Riepilogo:** informazioni su come abilitare la qualità dell'esperienza (QoE) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="80f2b-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="80f2b-105">La qualità dell'esperienza (QoE) registra i dati numerici che indicano la qualità del supporto e le informazioni sui partecipanti, i nomi di dispositivo, i driver, gli indirizzi IP e i tipi di endpoint coinvolti in chiamate e sessioni.</span><span class="sxs-lookup"><span data-stu-id="80f2b-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="80f2b-106">Per informazioni dettagliate, vedere [pianificazione del monitoraggio](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="80f2b-106">For details, see [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="80f2b-107">Usare la procedura seguente per abilitare QoE per l'intera organizzazione o per ogni sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="80f2b-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="80f2b-108">Per abilitare QoE, è prima necessario configurare il monitoraggio e un database back-end di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="80f2b-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="80f2b-109">Per informazioni dettagliate, vedere [distribuzione del monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="80f2b-109">For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="80f2b-110">Per abilitare QoE usando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="80f2b-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="80f2b-111">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="80f2b-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="80f2b-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="80f2b-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="80f2b-113">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.</span><span class="sxs-lookup"><span data-stu-id="80f2b-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="80f2b-114">Nella pagina **qualità di dati esperienza** fare clic sulla raccolta appropriata dalla tabella, fare clic su **azione**e quindi su **Abilita QoE**.</span><span class="sxs-lookup"><span data-stu-id="80f2b-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="80f2b-115">Abilitazione di QoE usando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="80f2b-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="80f2b-116">Puoi abilitare QoE usando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="80f2b-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="80f2b-117">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="80f2b-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="80f2b-118">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="80f2b-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="80f2b-119">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="80f2b-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="80f2b-120">Per abilitare QoE per una singola posizione</span><span class="sxs-lookup"><span data-stu-id="80f2b-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="80f2b-121">Per abilitare QoE, imposta il parametro EnableQoE su true ($True).</span><span class="sxs-lookup"><span data-stu-id="80f2b-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="80f2b-122">Per disabilitare QoE per una singola posizione</span><span class="sxs-lookup"><span data-stu-id="80f2b-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="80f2b-123">Per disabilitare QoE, imposta il parametro EnableQoE su false ($False).</span><span class="sxs-lookup"><span data-stu-id="80f2b-123">To disable QoE, set the EnableQoE parameter to False ($False).</span></span> <span data-ttu-id="80f2b-124">Questo non disinstalla il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="80f2b-124">This does not uninstall monitoring.</span></span> <span data-ttu-id="80f2b-125">Sospende la raccolta e lo spazio di archiviazione dei dati QoE.</span><span class="sxs-lookup"><span data-stu-id="80f2b-125">It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="80f2b-126">Per usare un singolo comando per abilitare QoE in più posizioni</span><span class="sxs-lookup"><span data-stu-id="80f2b-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="80f2b-127">Questo comando abilita QoE per tutte le impostazioni di configurazione QoE attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="80f2b-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="80f2b-128">Per informazioni dettagliate, vedere [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="80f2b-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="80f2b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80f2b-129">See also</span></span>

[<span data-ttu-id="80f2b-130">Pianificazione del monitoraggio</span><span class="sxs-lookup"><span data-stu-id="80f2b-130">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="80f2b-131">Distribuzione del monitoraggio</span><span class="sxs-lookup"><span data-stu-id="80f2b-131">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

