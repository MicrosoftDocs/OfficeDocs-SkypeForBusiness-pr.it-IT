---
title: Abilitare la registrazione dei dettagli delle chiamate in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Riepilogo: informazioni su come abilitare i record di registrazione dettagli chiamata (CDR) in Skype for Business Server.'
ms.openlocfilehash: 64a6e7d8d0e633fb3ef4e440932226f1f6f9c11a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195689"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="43b89-103">Abilitare la registrazione dei dettagli delle chiamate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="43b89-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="43b89-104">**Riepilogo:** Informazioni su come abilitare i record di registrazione dei dettagli delle chiamate (CDR) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="43b89-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="43b89-105">Registrazione dettagli chiamata (CDR) registra l'uso e le informazioni di diagnostica sulle attività peer-to-peer, tra cui messaggistica istanza, chiamate VoIP (Voice over Internet Protocol), condivisione di applicazioni, trasferimento di file e riunioni.</span><span class="sxs-lookup"><span data-stu-id="43b89-105">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="43b89-106">I dati sull'utilizzo possono essere usati per calcolare il ritorno sugli investimenti (ROI) e i dati di diagnostica possono essere usati per risolvere le attività e le riunioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="43b89-106">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="43b89-107">Usare la procedura seguente per abilitare CDR per l'intera organizzazione o per ogni sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43b89-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="43b89-108">Per abilitare CDR è necessario configurare il monitoraggio e un database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="43b89-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="43b89-109">Per informazioni dettagliate, vedere [distribuzione del monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="43b89-109">For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="43b89-110">Per abilitare CDR con il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="43b89-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="43b89-111">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="43b89-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="43b89-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="43b89-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="43b89-113">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **registrazione dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="43b89-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="43b89-114">Nella pagina **registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **azione**e quindi su **Abilita CDR**.</span><span class="sxs-lookup"><span data-stu-id="43b89-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="43b89-115">CDR è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="43b89-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="43b89-116">Attivazione di CDR tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="43b89-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="43b89-117">È possibile abilitare CDR usando Windows PowerShell e il cmdlet **Set-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="43b89-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="43b89-118">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43b89-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="43b89-119">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="43b89-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="43b89-120">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="43b89-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="43b89-121">Per abilitare CDR per una singola posizione</span><span class="sxs-lookup"><span data-stu-id="43b89-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="43b89-122">Per disabilitare CDR, imposta il parametro EnableCDR su true ($True).</span><span class="sxs-lookup"><span data-stu-id="43b89-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="43b89-123">Per disabilitare CDR per una singola posizione</span><span class="sxs-lookup"><span data-stu-id="43b89-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="43b89-124">Per disabilitare CDR, imposta il parametro EnableCDR su false ($False).</span><span class="sxs-lookup"><span data-stu-id="43b89-124">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="43b89-125">La disattivazione di CDR non disinstalla il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="43b89-125">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="43b89-126">Sospende la raccolta e lo spazio di archiviazione dei dati CDR.</span><span class="sxs-lookup"><span data-stu-id="43b89-126">It pauses the collection and storage of CDR data.</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="43b89-127">Per usare un singolo comando per abilitare CDR in più posizioni</span><span class="sxs-lookup"><span data-stu-id="43b89-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="43b89-128">Questo comando consente a CDR di usare tutte le impostazioni di configurazione CDR attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43b89-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

<span data-ttu-id="43b89-129">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="43b89-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="43b89-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43b89-130">See also</span></span>

[<span data-ttu-id="43b89-131">Pianificazione del monitoraggio</span><span class="sxs-lookup"><span data-stu-id="43b89-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="43b89-132">Distribuzione del monitoraggio</span><span class="sxs-lookup"><span data-stu-id="43b89-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
