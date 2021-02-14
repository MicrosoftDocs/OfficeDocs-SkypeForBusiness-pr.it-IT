---
title: Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: "La migrazione dell'applicazione Parcheggio di chiamata include il provisioning del pool di Skype for Business Server 2019 con tutti i file di musica di attesa personalizzati caricati nell'installazione legacy, il ripristino delle impostazioni del livello di servizio e il retargeting di tutti i orbit del parcheggio di chiamata al pool di Skype for Business Server 2019. Se nel pool sono stati configurati file di musica di attesa personalizzati, questi file devono essere copiati nel nuovo pool di Skype for Business Server 2019. È inoltre consigliabile eseguire il backup di tutti i file di musica di attesa personalizzati di Parcheggio di chiamata da un'altra destinazione per conservare una copia di backup separata di tutti i file di musica di attesa personalizzati caricati per il parcheggio di chiamata. I file di musica di attesa personalizzati per l'applicazione Parcheggio chiamata sono archiviati nell'archivio file del pool. Per copiare i file audio da un archivio file del pool a un archivio file di Skype for Business Server 2019, utilizzare il comando Xcopy con i parametri seguenti:"
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752818"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="6545a-107">Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="6545a-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="6545a-108">La migrazione dell'applicazione Parcheggio di chiamata include il provisioning del pool di Skype for Business Server 2019 con tutti i file di musica di attesa personalizzati caricati nell'installazione legacy, il ripristino delle impostazioni a livello di servizio e la nuova destinazione di tutti i orbit del parcheggio di chiamata nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6545a-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6545a-109">Se nel pool sono stati configurati file di musica di attesa personalizzati, questi file devono essere copiati nel nuovo pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6545a-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="6545a-110">È inoltre consigliabile eseguire il backup dei file di musica di attesa personalizzati di Parcheggio di chiamata in un'altra destinazione per conservare una copia di backup separata di tutti i file di musica di attesa personalizzati caricati per il parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6545a-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="6545a-111">I file di musica di attesa personalizzati per l'applicazione Parcheggio chiamata sono archiviati nell'archivio file del pool.</span><span class="sxs-lookup"><span data-stu-id="6545a-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="6545a-112">Per copiare i file audio da un archivio file del pool a un archivio file di Skype for Business Server 2019, utilizzare il **comando Xcopy** con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6545a-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="6545a-113">Quando tutti i file audio personalizzati sono stati copiati nell'archivio file di Skype for Business Server 2019, è necessario configurare le impostazioni dell'applicazione Parcheggio di chiamata del pool di Skype for Business Server 2019 e gli intervalli di orbit del parcheggio di chiamata associati al pool legacy devono essere riassegnati al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6545a-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="6545a-114">Le impostazioni dell'applicazione Parcheggio di chiamata includono la soglia di timeout di prelievo, l'abilitazione o la disabilitazione della musica di attesa, il numero massimo di tentativi di prelievo delle chiamate e la richiesta di timeout.</span><span class="sxs-lookup"><span data-stu-id="6545a-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="6545a-115">È necessario gestire le impostazioni dell'applicazione Parcheggio di chiamata utilizzando Skype for Business Server Management Shell per eseguire il cmdlet **Set-CsCpsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="6545a-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="6545a-116">Non è possibile gestire le impostazioni dell'applicazione Parcheggio di chiamata utilizzando il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6545a-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="6545a-117">Riconfigurare le impostazioni del servizio Parcheggio chiamata</span><span class="sxs-lookup"><span data-stu-id="6545a-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="6545a-118">Dal Front End Server di Skype for Business Server 2019, aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6545a-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="6545a-119">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6545a-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="6545a-120">Se le impostazioni dell'applicazione Parcheggio di chiamata di Skype for Business Server 2019 sono identiche alle impostazioni legacy, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="6545a-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="6545a-121">Se le impostazioni dell'applicazione Parcheggio di chiamata sono diverse per Skype for Business Server 2019 e gli ambienti legacy, utilizzare il cmdlet seguente come modello per aggiornare tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="6545a-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="6545a-122">Per riassegnare tutti gli intervalli di orbit del parcheggio di chiamata dal pool legacy al pool di Skype for Business Server 2019, è possibile utilizzare il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6545a-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6545a-123">Riassegnare tutti gli intervalli orbit del parcheggio di chiamata utilizzando il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6545a-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6545a-124">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6545a-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="6545a-125">Nel riquadro sinistro, selezionare **Funzionalità vocali**.</span><span class="sxs-lookup"><span data-stu-id="6545a-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="6545a-126">Selezionare la scheda **Parcheggio chiamata**.</span><span class="sxs-lookup"><span data-stu-id="6545a-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="6545a-127">Per ogni intervallo di orbit del parcheggio di chiamata assegnato a un pool legacy, modificare **l'FQDN** dell'impostazione del server di destinazione e selezionare il pool di Skype for Business Server 2019 che eelaborare le richieste di parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6545a-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="6545a-128">Selezionare **Commit** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6545a-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6545a-129">Riassegnare tutti gli intervalli orbit del parcheggio di chiamata tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="6545a-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="6545a-130">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6545a-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="6545a-131">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6545a-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="6545a-132">Questo cmdlet elenca tutti gli intervalli di codici orbit di Parcheggio chiamata nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6545a-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="6545a-133">Tutti i orbit del parcheggio di chiamata con i parametri **CallParkServiceId** e **CallParkServerFqdn** impostati come pool legacy devono essere riassegnati.</span><span class="sxs-lookup"><span data-stu-id="6545a-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="6545a-134">Per riassegnare gli intervalli di orbit del parcheggio di chiamata legacy al pool di Skype for Business Server 2019, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6545a-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="6545a-135">Dopo la riassegnazione di tutti gli intervalli di orbit del parcheggio di chiamata al pool di Skype for Business Server 2019, il processo di migrazione per l'applicazione Parcheggio di chiamata verrà completato e il pool di Skype for Business Server 2019 gestirà tutte le richieste future di parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6545a-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


