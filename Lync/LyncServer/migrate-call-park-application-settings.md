---
title: Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2789a8a83c8f3ee831fb91c85999d936ea54dd8b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="dab80-102">Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="dab80-102">Migrate Call Park application settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dab80-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="dab80-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="dab80-104">La migrazione dell'applicazione Parcheggio di chiamata da Lync Server 2010 a Lync Server 2013 include il provisioning del pool di Lync Server 2013 con qualsiasi file di musica di attesa personalizzato che è stato caricato in Lync Server 2010, il ripristino delle impostazioni del livello di servizio e la reimpostazione di tutte le orbite del parcheggio di chiamata nel pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dab80-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="dab80-105">Se nel pool di Lync Server 2010 sono stati configurati file di musica di attesa personalizzati, questi file devono essere copiati nel nuovo pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dab80-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="dab80-106">Inoltre, è consigliabile eseguire il backup di qualsiasi parcheggio di chiamata personalizzato file di musica di attesa da Lync Server 2010 a un'altra destinazione per mantenere una copia di backup separata di qualsiasi file di musica di attesa personalizzato che sono stati caricati per il parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dab80-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="dab80-107">I file di musica di attesa personalizzati per l'applicazione Parcheggio chiamata sono archiviati nell'archivio file del pool.</span><span class="sxs-lookup"><span data-stu-id="dab80-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="dab80-108">Per copiare i file audio da un archivio file del pool di Lync Server 2010 in un archivio file di Lync Server 2013, utilizzare il comando **xcopy** con i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="dab80-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="dab80-109">Quando tutti i file audio personalizzati sono stati copiati nell'archivio file di Lync Server 2013, è necessario configurare le impostazioni dell'applicazione Parcheggio di chiamata del pool di Lync Server 2013 e gli intervalli di orbit del parcheggio di chiamata associati al pool di Lync Server 2010 devono essere riassegnati al pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dab80-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="dab80-110">Le impostazioni di Parcheggio chiamata includono la soglia di timeout di pick-up, l'abilitazione o la disabilitazione della musica di attesa, il numero massimo di tentativi di pick-up chiamata e la richiesta di timeout.</span><span class="sxs-lookup"><span data-stu-id="dab80-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="dab80-111">È necessario gestire le impostazioni dell'applicazione Parcheggio di chiamata utilizzando Lync Server Management Shell per eseguire il cmdlet **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="dab80-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="dab80-112">Non è possibile gestire le impostazioni dell'applicazione Parcheggio di chiamata utilizzando il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dab80-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="dab80-113">**Riconfigurare le impostazioni del servizio Parcheggio chiamata**</span><span class="sxs-lookup"><span data-stu-id="dab80-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="dab80-114">Dal front end server Lync Server 2013 aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dab80-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="dab80-115">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="dab80-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dab80-116">Se le impostazioni dell'applicazione Parcheggio di chiamata di Lync Server 2013 sono identiche alle impostazioni legacy di Lync Server 2010, è possibile ignorare l'esecuzione di questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="dab80-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="dab80-117">Se le impostazioni dell'applicazione Parcheggio di chiamata sono diverse per gli ambienti Lync Server 2013 e Lync Server 2010, utilizzare il cmdlet riportato di seguito come modello per aggiornare tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="dab80-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="dab80-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-EnableMusicOnHold" " <LS2010 CPS value> -MaxCallPickupAttempts" " <LS2010 CPS pickup attempts> -OnTimeoutURI" <LS2010 CPS timeout URI> "```</span><span class="sxs-lookup"><span data-stu-id="dab80-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="dab80-119">Per riassegnare tutti gli intervalli di orbit del parcheggio di chiamata dal pool di Lync Server 2010 al pool Lync Server 2013, è possibile utilizzare il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dab80-119">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="dab80-120">**Riassegnare tutti gli intervalli di codici orbit di Parcheggio chiamata utilizzando il Pannello di controllo di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="dab80-120">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="dab80-121">Aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dab80-121">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="dab80-122">Nel riquadro sinistro, selezionare **Funzionalità vocali**.</span><span class="sxs-lookup"><span data-stu-id="dab80-122">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="dab80-123">Selezionare la scheda **Parcheggio chiamata**.</span><span class="sxs-lookup"><span data-stu-id="dab80-123">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="dab80-124">Per ogni intervallo di orbit del parcheggio di chiamata assegnato a un pool di Lync Server 2010, modificare l'impostazione **FQDN del server di destinazione** e selezionare il pool di lync Server 2013 che elaborerà le richieste del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dab80-124">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="dab80-125">Selezionare **Commit** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="dab80-125">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="dab80-126">**Riassegnare tutti gli intervalli di codici orbit di Parcheggio chiamata utilizzando Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="dab80-126">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="dab80-127">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dab80-127">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="dab80-128">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="dab80-128">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="dab80-129">Questo cmdlet elenca tutti gli intervalli di codici orbit di Parcheggio chiamata nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dab80-129">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="dab80-130">Tutte le orbite del parcheggio di chiamata con i parametri **CallParkServiceId** e **CallParkServerFqdn** impostati come pool di Lync Server 2010 devono essere riassegnate.</span><span class="sxs-lookup"><span data-stu-id="dab80-130">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="dab80-131">Per riassegnare gli intervalli di orbit del parcheggio di chiamata di Lync Server 2010 al pool di Lync Server 2013, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="dab80-131">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="dab80-132">Dopo aver riassegnato tutti gli intervalli di orbit del parcheggio di chiamata al pool di Lync Server 2013, il processo di migrazione per l'applicazione Parcheggio di chiamata verrà completato e il pool di Lync Server 2013 gestirà tutte le richieste future del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dab80-132">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

