---
title: Abilitare la registrazione dettagli chiamata in Skype for Business Server
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Riepilogo: informazioni su come abilitare i record di registrazione dettagli chiamata (CDR) in Skype for Business Server.'
ms.openlocfilehash: 48d21be6d377df24e859c3ffa6bb8b7858076d29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816886"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="f7151-103">Abilitare la registrazione dettagli chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f7151-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="f7151-104">**Riepilogo:** Informazioni su come abilitare i record di registrazione dettagli chiamata (CDR) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f7151-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="f7151-p101">La funzionalità di registrazione dettagli chiamata (CDR) registra le informazioni di utilizzo e di diagnostica per le attività peer-to-peer, tra cui la messaggistica istantanea, le chiamate VoIP (Voice over Internet Protocol), la condivisione applicazioni, il trasferimento file e le riunioni. I dati di utilizzo possono essere utilizzati per calcolare il rendimento dell'investimento, mentre i dati di diagnostica possono aiutare a risolvere problemi relativi alle attività peer-to-peer e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="f7151-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="f7151-107">Utilizzare la procedura seguente per abilitare la registrazione dettagli chiamata per l'intera organizzazione o per ogni sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f7151-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="f7151-108">Per abilitare la registrazione dettagli chiamata, è necessario configurare il monitoraggio e un database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="f7151-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="f7151-109">Per informazioni dettagliate, vedere [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="f7151-109">For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="f7151-110">Per abilitare CDR con il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f7151-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f7151-111">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f7151-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="f7151-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f7151-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f7151-113">Nella barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Registrazione dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="f7151-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="f7151-114">Nella pagina **Registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, su **Azione** e quindi su **Abilita registrazione dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="f7151-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f7151-115">La funzionalità di registrazione dettagli chiamata è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f7151-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f7151-116">Abilitazione di CDR tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7151-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f7151-117">È possibile abilitare la funzionalità registrazione dettagli chiamata utilizzando Windows PowerShell e il cmdlet **Set-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="f7151-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="f7151-118">È possibile eseguire questo cmdlet sia da Skype for Business Server Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f7151-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f7151-119">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo del Blog ["Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="f7151-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f7151-120">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f7151-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="f7151-121">Per abilitare la funzionalità CR per una sola postazione</span><span class="sxs-lookup"><span data-stu-id="f7151-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="f7151-122">Per abilitare la funzionalità di registrazione dettaglia chiamata, impostare il parametro EnableCDR su True ($True).</span><span class="sxs-lookup"><span data-stu-id="f7151-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="f7151-123">Per disabilitare la funzionalità CDR per una sola postazione</span><span class="sxs-lookup"><span data-stu-id="f7151-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="f7151-124">Per disabilitare la funzionalità di registrazione dettaglia chiamata, impostare il parametro EnableCDR su False ($False).</span><span class="sxs-lookup"><span data-stu-id="f7151-124">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="f7151-125">La disattivazione di CDR non disinstalla il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="f7151-125">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="f7151-126">Interrompe la raccolta e l'archiviazione dei dati di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="f7151-126">It pauses the collection and storage of CDR data.</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="f7151-127">Per abilitare la funzionalità CDR in più postazioni con un solo comando</span><span class="sxs-lookup"><span data-stu-id="f7151-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="f7151-128">Questo comando abilita la funzionalità CDR per tutte le impostazioni di configurazione CDR attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f7151-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="f7151-129">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f7151-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7151-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7151-130">See also</span></span>

[<span data-ttu-id="f7151-131">Pianificazione del monitoraggio</span><span class="sxs-lookup"><span data-stu-id="f7151-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="f7151-132">Distribuzione del monitoraggio</span><span class="sxs-lookup"><span data-stu-id="f7151-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
