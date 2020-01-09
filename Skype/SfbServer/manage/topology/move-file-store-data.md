---
title: Trasferire i dati dell'archivio file in un nuovo archivio di file in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Se è necessario rimuovere il file server che sta attualmente agendo come archivio per la distribuzione di Skype for Business Server o se è necessario apportare altre modifiche che rendessero disponibile il file Store corrente, è prima di tutto necessario creare una nuova condivisione. È quindi necessario eseguire la procedura seguente:'
ms.openlocfilehash: 6ae09d2415b24a4337edbee3c66e8b9a8bd2009a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991511"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server"></a><span data-ttu-id="7cbbf-104">Trasferire i dati dell'archivio file in un nuovo archivio di file in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7cbbf-104">Move File Store Data to a New File Store in Skype for Business Server</span></span>

<span data-ttu-id="7cbbf-105">Se è necessario rimuovere il file server che sta attualmente agendo come archivio per la distribuzione di Skype for Business Server o se è necessario apportare altre modifiche che rendessero disponibile il file Store corrente, è prima di tutto necessario creare una nuova condivisione.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="7cbbf-106">È quindi necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="7cbbf-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="7cbbf-107">Arrestare i servizi di Skype for Business Server che usano l'archivio di file che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-107">Shut down the Skype for Business Server services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="7cbbf-108">Definire l'archivio di file in Generatore di topologia e pubblicare le modifiche per rendere disponibile il nuovo archivio di file alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="7cbbf-109">Trasferire i dati nel nuovo archivio file.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="7cbbf-110">Riavviare i server o i servizi.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="7cbbf-111">Facoltativamente, rimuovere la vecchia condivisione di file e la cartella di file.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="7cbbf-112">Per trasferire i dati dell'archivio file da un archivio file a un nuovo archivio file</span><span class="sxs-lookup"><span data-stu-id="7cbbf-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="7cbbf-113">Accedere a un computer come membro del gruppo RTCUniversersalServerAdmins o CsServerAdministrator in cui sono installati gli strumenti di amministrazione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server, Administrative Tools are installed.</span></span>

2.  <span data-ttu-id="7cbbf-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="7cbbf-115">Nella barra di spostamento sinistra fare clic su **topologia**e quindi su **stato**.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="7cbbf-116">Per ogni pool di Director, Director, server Standard Edition e pool Front end che usa l'archivio di file che si vuole rimuovere, selezionare il server o il pool, fare clic su **azione**e quindi su **Interrompi tutti i servizi**.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="7cbbf-117">Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="7cbbf-118">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Skype for Business Server**e quindi fare clic su **Generatore di topologia di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

7. <span data-ttu-id="7cbbf-119">Selezionare un server o un pool che usa il file Store ed eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7cbbf-119">Select a server or pool that uses the file store, and do the following:</span></span>

   <span data-ttu-id="7cbbf-120">un.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-120">a.</span></span> <span data-ttu-id="7cbbf-121">Fare clic con il pulsante destro del mouse sul server o sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-121">Right-click the server or pool, and then click **Edit Properties**.</span></span>

   <span data-ttu-id="7cbbf-122">b.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-122">b.</span></span> <span data-ttu-id="7cbbf-123">In **proprietà modifica**, in **associazioni**, in **Archivio file**fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-123">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

   <span data-ttu-id="7cbbf-124">c.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-124">c.</span></span> <span data-ttu-id="7cbbf-125">In **Definisci nuovo archivio file**, in **FQDN file server**, digitare il nome di dominio completo (FQDN) del file server.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-125">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="7cbbf-126">In **condivisione file**Digitare il nome della cartella per la nuova condivisione file e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-126">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7cbbf-127">Questo passaggio definisce un nuovo archivio di file da usare in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-127">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="7cbbf-128">Puoi definirla una sola volta, non per ogni server.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-128">You define it only once, not for each server.</span></span> <span data-ttu-id="7cbbf-129">Prima di pubblicare la topologia, è necessario creare la condivisione file definita nel file server definito.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-129">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="7cbbf-130">Per informazioni dettagliate, vedere [definire l'archivio di file per il front-end](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span><span class="sxs-lookup"><span data-stu-id="7cbbf-130">For details, see [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).</span></span>

8. <span data-ttu-id="7cbbf-131">Per ogni server o pool che usa l'archivio di file, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7cbbf-131">For each server or pool that uses the file store, do the following:</span></span>

   <span data-ttu-id="7cbbf-132">un.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-132">a.</span></span> <span data-ttu-id="7cbbf-133">Fare clic con il pulsante destro del mouse sul server o sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-133">Right-click the server or pool, and then click **Edit properties**.</span></span>

   <span data-ttu-id="7cbbf-134">b.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-134">b.</span></span> <span data-ttu-id="7cbbf-135">In **proprietà modifica**, in **associazioni**, in **Archivio file**selezionare la nuova condivisione file e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-135">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

9. <span data-ttu-id="7cbbf-136">Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Skype for Business Server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-136">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="7cbbf-137">Per informazioni dettagliate, vedere [procedure comuni per la rimozione di server e componenti Lync](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span><span class="sxs-lookup"><span data-stu-id="7cbbf-137">For details, see [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).</span></span>

10. <span data-ttu-id="7cbbf-138">Avviare un prompt dei comandi: fare clic sul pulsante **Start**, scegliere **Esegui**e quindi digitare cmd. exe.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-138">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

11. <span data-ttu-id="7cbbf-139">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7cbbf-139">At the command line, type the following:</span></span>

     ```console
     Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>

     ```

    > [!TIP]
    > <span data-ttu-id="7cbbf-140">L'opzione/S copia i file, le directory e le sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-140">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="7cbbf-141">L'opzione/XF ignora tutti i file denominati meeting. Active.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-141">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="7cbbf-142">Le versioni correnti di Robocopy. exe con l'opzione/MT aumentano notevolmente la velocità di copia usando più thread.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-142">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="7cbbf-143">Per l'opzione/LOG, usare un percorso di directory e un nome di file di log sotto forma di C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-143">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="7cbbf-144">Questa opzione consente di creare un file di log delle operazioni nella posizione denominata.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-144">This switch creates a log file of operations at the named location.</span></span>

12. <span data-ttu-id="7cbbf-145">Al termine della copia dei dati, nel pannello di controllo di Lync Server fare clic su **topologia**e quindi su **stato**.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-145">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

13. <span data-ttu-id="7cbbf-146">Per ogni server o pool in cui sono stati arrestati i servizi, selezionare il server o il pool, fare clic su **azione**e quindi su **Avvia tutti i servizi**.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-146">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

14. <span data-ttu-id="7cbbf-147">Rimuovere il vecchio archivio di file dalla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-147">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="7cbbf-148">Per informazioni dettagliate, vedere [rimuovere un archivio di file](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span><span class="sxs-lookup"><span data-stu-id="7cbbf-148">For details, see [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).</span></span>

15. <span data-ttu-id="7cbbf-149">Opzionale Accedere al computer che contiene l'archivio di file appena rimosso come membro del gruppo Administrators locale o del gruppo Domain Admins e quindi rimuovere la vecchia condivisione file e la directory.</span><span class="sxs-lookup"><span data-stu-id="7cbbf-149">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="7cbbf-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cbbf-150">See also</span></span>


[<span data-ttu-id="7cbbf-151">Riassegnare un server a un altro archivio di file</span><span class="sxs-lookup"><span data-stu-id="7cbbf-151">Reassign a Server to a Different File Store</span></span>](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[<span data-ttu-id="7cbbf-152">Rimuovere un archivio di file</span><span class="sxs-lookup"><span data-stu-id="7cbbf-152">Remove a file store</span></span>](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)

