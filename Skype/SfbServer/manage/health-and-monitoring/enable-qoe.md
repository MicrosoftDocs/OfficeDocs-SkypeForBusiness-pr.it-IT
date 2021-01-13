---
title: Abilitare la qualità dell'esperienza in Skype for Business Server
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
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: "Riepilogo: informazioni su come abilitare la qualità dell'esperienza (QoE) in Skype for Business Server."
ms.openlocfilehash: 67b752df3791d3ba0493a7e3575f25c58231ad26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816856"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="f2fef-103">Abilitare la qualità dell'esperienza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f2fef-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="f2fef-104">**Riepilogo:** informazioni su come abilitare la qualità dell'esperienza (QoE) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2fef-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="f2fef-105">La qualità percepita dagli utenti (QoE, Quality of Experience) registra dati numerici che indicano la qualità multimediale e le informazioni sui partecipanti, i nomi di dispositivi, i driver, gli indirizzi IP e i tipi di endpoint coinvolti nelle chiamate e nelle sessioni.</span><span class="sxs-lookup"><span data-stu-id="f2fef-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="f2fef-106">Per informazioni dettagliate, vedere [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f2fef-106">For details, see [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="f2fef-107">Utilizzare la procedura che segue per abilitare QoE per l'intera organizzazione o per ogni suo sito.</span><span class="sxs-lookup"><span data-stu-id="f2fef-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="f2fef-108">Per abilitare QoE, è innanzitutto necessario configurare il monitoraggio e un database back-end Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="f2fef-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="f2fef-109">Per informazioni dettagliate, vedere [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="f2fef-109">For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f2fef-110">Per abilitare QoE utilizzando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f2fef-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f2fef-111">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2fef-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="f2fef-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2fef-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f2fef-113">Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.</span><span class="sxs-lookup"><span data-stu-id="f2fef-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="f2fef-114">Nella pagina **Dati QoE** fare clic sulla raccolta appropriata nella tabella, su **Azione** e quindi su **Abilita QoE**.</span><span class="sxs-lookup"><span data-stu-id="f2fef-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f2fef-115">Abilitazione di QoE tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2fef-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f2fef-116">È possibile abilitare QoE utilizzando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="f2fef-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="f2fef-117">È possibile eseguire questo cmdlet sia da Skype for Business Server Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2fef-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f2fef-118">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo del Blog ["Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="f2fef-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f2fef-119">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2fef-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="f2fef-120">Per abilitare QoE per una singola posizione</span><span class="sxs-lookup"><span data-stu-id="f2fef-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="f2fef-121">Per abilitare QoE, impostare il parametro EnableQoE su True ($True).</span><span class="sxs-lookup"><span data-stu-id="f2fef-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="f2fef-122">Per disabilitare QoE per una singola posizione</span><span class="sxs-lookup"><span data-stu-id="f2fef-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="f2fef-p104">Per disabilitare QoE, impostare il parametro EnableQoE su False ($False). Questa operazione non comporta la disinstallazione del monitoraggio. Determina solo la sospensione della raccolta e dell'archiviazione di dati QoE.</span><span class="sxs-lookup"><span data-stu-id="f2fef-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="f2fef-126">Per utilizzare un singolo comando per abilitare QoE in più posizioni</span><span class="sxs-lookup"><span data-stu-id="f2fef-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="f2fef-127">Il comando seguente abilita QoE per tutte le impostazioni di configurazione QoE attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2fef-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="f2fef-128">Per informazioni dettagliate, vedere [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f2fef-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2fef-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2fef-129">See also</span></span>

[<span data-ttu-id="f2fef-130">Pianificazione del monitoraggio</span><span class="sxs-lookup"><span data-stu-id="f2fef-130">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="f2fef-131">Distribuzione del monitoraggio</span><span class="sxs-lookup"><span data-stu-id="f2fef-131">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

