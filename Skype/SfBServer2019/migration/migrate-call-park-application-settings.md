---
title: Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: "La migrazione dell'applicazione Call Park include il provisioning del pool di Skype for Business Server 2019 con qualsiasi musica personalizzata su file in attesa caricati nell'installazione legacy, il ripristino delle impostazioni del livello di servizio e la destinazione di tutte le orbite di Call Park Pool di Skype for Business Server 2019. Se i file personalizzati per la musica in attesa sono stati configurati nel pool, questi file devono essere copiati nel nuovo pool di Skype for Business Server 2019. Inoltre, è consigliabile eseguire il backup di qualsiasi parcheggio di chiamata personalizzato per la musica in attesa di file da a un'altra destinazione per mantenere una copia di backup separata di qualsiasi file di musica in attesa personalizzato caricato per Call Park. I file personalizzati per la musica in blocco per l'applicazione Parcheggio di chiamata sono archiviati nell'archivio di file del pool. Per copiare i file audio da un file di pool in un archivio di file di Skype for Business Server 2019, usare il comando xcopy con i parametri seguenti:"
ms.openlocfilehash: 0435144fc647a08d8252f35d8449d1e7daa62d68
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991161"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="48570-107">Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="48570-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="48570-108">La migrazione dell'applicazione Call Park include il provisioning del pool di Skype for Business Server 2019 con tutti i file musicali personalizzati che sono stati caricati nell'installazione legacy, il ripristino delle impostazioni a livello di servizio e la destinazione di tutte le orbite di Call Park al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="48570-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="48570-109">Se i file personalizzati per la musica in attesa sono stati configurati nel pool, questi file devono essere copiati nel nuovo pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="48570-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="48570-110">Inoltre, è consigliabile eseguire il backup di qualsiasi parcheggio di chiamata personalizzato per la musica in attesa di file in un'altra destinazione per mantenere una copia di backup separata di tutti i file di musica in attesa personalizzati caricati per Call Park.</span><span class="sxs-lookup"><span data-stu-id="48570-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="48570-111">I file personalizzati per la musica in blocco per l'applicazione Parcheggio di chiamata sono archiviati nell'archivio di file del pool.</span><span class="sxs-lookup"><span data-stu-id="48570-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="48570-112">Per copiare i file audio da un file di pool in un archivio di file di Skype for Business Server 2019, usare il comando **xcopy** con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="48570-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="48570-113">Quando tutti i file audio personalizzati sono stati copiati nel file Store di Skype for Business Server 2019, è necessario configurare le impostazioni dell'applicazione di Call Park del pool di Skype for Business Server 2019 e gli intervalli di orbita del parcheggio di chiamata associati al pool legacy devono essere riassegnati al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="48570-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="48570-114">Le impostazioni delle applicazioni di Call Park includono la soglia di timeout del prelievo, l'abilitazione o la disabilitazione della musica in attesa, i tentativi di ritiro massimo delle chiamate e la richiesta di timeout.</span><span class="sxs-lookup"><span data-stu-id="48570-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="48570-115">Per eseguire il cmdlet **Set-CsCpsConfiguration** , è necessario gestire le impostazioni delle applicazioni di Call Park usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="48570-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="48570-116">Non è possibile gestire le impostazioni delle applicazioni di Call Park usando il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="48570-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="48570-117">Riconfigurare le impostazioni del servizio di parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="48570-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="48570-118">Dal server front-end di Skype for Business Server 2019 Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="48570-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="48570-119">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="48570-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="48570-120">Se le impostazioni delle applicazioni di Call Park di Skype for Business Server 2019 sono identiche alle impostazioni legacy, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="48570-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="48570-121">Se le impostazioni delle applicazioni di Call Park sono diverse per Skype for Business Server 2019 e per gli ambienti Legacy, usare il cmdlet seguente come modello per aggiornare tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="48570-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="48570-122">Per riassegnare tutti gli intervalli di orbit del parcheggio di chiamata dal pool legacy al pool di Skype for Business Server 2019, è possibile usare il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="48570-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="48570-123">Riassegnare tutti gli intervalli orbit di Call Park tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="48570-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="48570-124">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="48570-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="48570-125">Nel riquadro sinistro selezionare **funzionalità vocali**.</span><span class="sxs-lookup"><span data-stu-id="48570-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="48570-126">Selezionare la scheda **parcheggio chiamate** .</span><span class="sxs-lookup"><span data-stu-id="48570-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="48570-127">Per ogni intervallo di orbit del parcheggio di chiamata assegnato a un pool legacy, modificare l'impostazione **FQDN di server di destinazione** e selezionare il pool di Skype for Business Server 2019 in cui verranno elaborate le richieste di parcheggio delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="48570-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="48570-128">Selezionare **conferma** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="48570-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="48570-129">Riassegnare tutti gli intervalli orbit di Call Park con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="48570-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="48570-130">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="48570-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="48570-131">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="48570-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="48570-132">Questo cmdlet elenca tutti gli intervalli di orbit del parcheggio delle chiamate nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="48570-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="48570-133">Tutte le orbite del parcheggio delle chiamate con i parametri **CallParkServiceId** e **CallParkServerFqdn** impostati come pool legacy devono essere riassegnate.</span><span class="sxs-lookup"><span data-stu-id="48570-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="48570-134">Per riassegnare gli intervalli di orbit del parcheggio di chiamata legacy al pool di Skype for Business Server 2019, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="48570-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="48570-135">Dopo aver riassegnato tutti gli intervalli orbit di Call Park al pool di Skype for Business Server 2019, il processo di migrazione per l'applicazione di Call Park verrà completato e il pool di Skype for Business Server 2019 gestirà tutte le richieste future di Call Park.</span><span class="sxs-lookup"><span data-stu-id="48570-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


