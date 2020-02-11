---
title: Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee1afd2e53bd29571818b9194fe77d3d350386f1
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="2063e-102">Eseguire la migrazione delle impostazioni dell'applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="2063e-102">Migrate Call Park application settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2063e-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2063e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2063e-104">La migrazione dell'applicazione Call Park da Lync Server 2010 a Lync Server 2013 include il provisioning del pool Lync Server 2013 con qualsiasi musica personalizzata nei file di blocco caricati in Lync Server 2010, il ripristino delle impostazioni del livello di servizio e la nuova destinazione tutto il parcheggio delle chiamate orbita sul pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2063e-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="2063e-105">Se i file personalizzati per la musica in attesa sono stati configurati nel pool di Lync Server 2010, questi file devono essere copiati nel nuovo pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2063e-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="2063e-106">Inoltre, è consigliabile eseguire il backup di qualsiasi parcheggio di chiamata personalizzato su file musicali in blocco da Lync Server 2010 a un'altra destinazione per mantenere una copia di backup separata di tutti i file di musica in attesa personalizzati caricati per Call Park.</span><span class="sxs-lookup"><span data-stu-id="2063e-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="2063e-107">I file personalizzati per la musica in blocco per l'applicazione Parcheggio di chiamata sono archiviati nell'archivio di file del pool.</span><span class="sxs-lookup"><span data-stu-id="2063e-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="2063e-108">Per copiare i file audio da un archivio di file del pool di Lync Server 2010 in un archivio di file di Lync Server 2013, usare il comando **xcopy** con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="2063e-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="2063e-109">Quando tutti i file audio personalizzati sono stati copiati nell'archivio di file di Lync Server 2013, è necessario configurare le impostazioni dell'applicazione di parcheggio per le chiamate del pool di Lync Server 2013 e gli intervalli di orbita del parcheggio di chiamata associati al pool Lync Server 2010 devono essere riassegnati a pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2063e-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="2063e-110">Le impostazioni delle applicazioni di Call Park includono la soglia di timeout del prelievo, l'abilitazione o la disabilitazione della musica in attesa, i tentativi di ritiro massimo delle chiamate e la richiesta di timeout.</span><span class="sxs-lookup"><span data-stu-id="2063e-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="2063e-111">Per eseguire il cmdlet **Set-CsCpsConfiguration** , è necessario gestire le impostazioni delle applicazioni di Call Park tramite Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2063e-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="2063e-112">Non è possibile gestire le impostazioni delle applicazioni di Call Park tramite il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2063e-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="2063e-113">**Riconfigurare le impostazioni del servizio di parcheggio delle chiamate**</span><span class="sxs-lookup"><span data-stu-id="2063e-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="2063e-114">Dal server front-end di Lync Server 2013 aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2063e-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="2063e-115">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2063e-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2063e-116">Se le impostazioni delle applicazioni di parcheggio per le chiamate di Lync Server 2013 sono identiche alle impostazioni legacy di Lync Server 2010, è possibile ignorare l'eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="2063e-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="2063e-117">Se le impostazioni delle applicazioni di Call Park sono diverse per gli ambienti Lync Server 2013 e Lync Server 2010, usare il cmdlet seguente come modello per aggiornare tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="2063e-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="2063e-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold"<LS2010 CPS TimeSpan>"-EnableMusicOnHold"<LS2010 CPS value>"-MaxCallPickupAttempts"<LS2010 CPS pickup attempts>"-OnTimeoutURI"<LS2010 CPS timeout URI>"```</span><span class="sxs-lookup"><span data-stu-id="2063e-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="2063e-119">Per riassegnare tutti gli intervalli di orbit del parcheggio di chiamata dal pool Lync Server 2010 al pool Lync Server 2013, è possibile usare il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2063e-119">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="2063e-120">**Riassegnare tutti gli intervalli di orbit del parcheggio di chiamata tramite il pannello di controllo di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="2063e-120">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="2063e-121">Aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2063e-121">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="2063e-122">Nel riquadro sinistro selezionare **funzionalità vocali**.</span><span class="sxs-lookup"><span data-stu-id="2063e-122">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="2063e-123">Selezionare la scheda **parcheggio chiamate** .</span><span class="sxs-lookup"><span data-stu-id="2063e-123">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="2063e-124">Per ogni intervallo di orbit del parcheggio di chiamata assegnato a un pool di Lync Server 2010, modificare il **nome di dominio completo dell'impostazione del server di destinazione** e selezionare il pool di lync Server 2013 che elaborerà le richieste del parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="2063e-124">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="2063e-125">Selezionare **conferma** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2063e-125">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="2063e-126">**Riassegnare tutti gli intervalli di orbit del parcheggio di chiamata tramite Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="2063e-126">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="2063e-127">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2063e-127">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="2063e-128">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2063e-128">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="2063e-129">Questo cmdlet elenca tutti gli intervalli di orbit del parcheggio delle chiamate nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2063e-129">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="2063e-130">Tutte le orbite del parcheggio delle chiamate con i parametri **CallParkServiceId** e **CallParkServerFqdn** impostati come pool di Lync Server 2010 devono essere riassegnati.</span><span class="sxs-lookup"><span data-stu-id="2063e-130">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="2063e-131">Per riassegnare gli intervalli di Orbit Park di chiamata di Lync Server 2010 al pool Lync Server 2013, nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2063e-131">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="2063e-132">Dopo aver riassegnato tutti gli intervalli di orbit del parcheggio di chiamata al pool di Lync Server 2013, il processo di migrazione per l'applicazione di parcheggio di chiamata verrà completato e il pool di Lync Server 2013 gestirà tutte le richieste future di Call Park.</span><span class="sxs-lookup"><span data-stu-id="2063e-132">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

