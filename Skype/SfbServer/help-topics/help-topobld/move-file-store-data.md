---
title: Spostare i dati dell'archivio file in un nuovo archivio file in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: "Se è necessario rimuovere il file server che attualmente funge da archivio file per la distribuzione di Skype for Business Server 2015 o se è necessario apportare altre modifiche che renderebbero l'archivio file corrente non disponibile, è innanzitutto necessario creare una nuova condivisione. È quindi necessario eseguire la procedura seguente:"
ms.openlocfilehash: 2d65e517b10a76013fbeb332b183b5b816e99083
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119645"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a><span data-ttu-id="1708b-104">Spostare i dati dell'archivio file in un nuovo archivio file in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1708b-104">Move File Store Data to a New File Store in Skype for Business Server 2015</span></span>

<span data-ttu-id="1708b-105">Se è necessario rimuovere il file server che attualmente funge da archivio file per la distribuzione di Skype for Business Server 2015 o se è necessario apportare altre modifiche che renderebbero l'archivio file corrente non disponibile, è innanzitutto necessario creare una nuova condivisione.</span><span class="sxs-lookup"><span data-stu-id="1708b-105">If you need to remove the file server that is currently acting as the file store for your Skype for Business Server 2015 deployment, or if you need to make other changes that would make the current file store unavailable, you first need to create a new share.</span></span> <span data-ttu-id="1708b-106">È quindi necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="1708b-106">Then you need to perform the following steps:</span></span>

1. <span data-ttu-id="1708b-107">Arrestare i servizi di Skype for Business Server 2015 che utilizzano l'archivio file che si intende rimuovere.</span><span class="sxs-lookup"><span data-stu-id="1708b-107">Shut down the Skype for Business Server 2015 services that use the file store that you plan to remove.</span></span>

2. <span data-ttu-id="1708b-108">Definire l'archivio file in Generatore di topologie e pubblicare le modifiche per rendere disponibile il nuovo archivio file per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1708b-108">Define the file store in Topology Builder and publish the changes to make the new file store available to your deployment.</span></span>

3. <span data-ttu-id="1708b-109">Spostare i dati nel nuovo archivio file.</span><span class="sxs-lookup"><span data-stu-id="1708b-109">Move the data to the new file store.</span></span>

4. <span data-ttu-id="1708b-110">Riavviare i server o i servizi.</span><span class="sxs-lookup"><span data-stu-id="1708b-110">Restart the servers or services.</span></span>

5. <span data-ttu-id="1708b-111">Facoltativamente, rimuovere la condivisione file e la cartella di file precedente.</span><span class="sxs-lookup"><span data-stu-id="1708b-111">Optionally, remove the old file share and file folder.</span></span>

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a><span data-ttu-id="1708b-112">Per spostare i dati dell'archivio file in un nuovo archivio</span><span class="sxs-lookup"><span data-stu-id="1708b-112">To move file store data from one file store to a new file store</span></span>

1. <span data-ttu-id="1708b-113">Accedere a un computer come membro del gruppo RTCUniversersalServerAdmins o CsServerAdministrator in cui è installato Skype for Business Server 2015, Strumenti di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1708b-113">Log on to a computer as a member of the RTCUniversersalServerAdmins or CsServerAdministrator group where the Skype for Business Server 2015, Administrative Tools are installed.</span></span>

2. <span data-ttu-id="1708b-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1708b-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1708b-115">Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.</span><span class="sxs-lookup"><span data-stu-id="1708b-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>

4. <span data-ttu-id="1708b-116">Per ogni pool di server Director, Director, server Standard Edition e pool Front End che utilizza l'archivio file che si intende rimuovere, selezionare il server o il pool, fare clic su Azione e quindi su Arresta **tutti i servizi.**</span><span class="sxs-lookup"><span data-stu-id="1708b-116">For each Director pool, Director, Standard Edition server, and Front End pool that uses the file store that you plan to remove, select the server or pool, click **Action**, and then click **Stop all services**.</span></span>

5. <span data-ttu-id="1708b-117">Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1708b-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

6. <span data-ttu-id="1708b-118">Avviare Generatore di topologie: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server 2015** e quindi Generatore di topologie di **Skype for Business Server 2015.**</span><span class="sxs-lookup"><span data-stu-id="1708b-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>

7. <span data-ttu-id="1708b-119">Selezionare un server o un pool che utilizza l'archivio file ed eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1708b-119">Select a server or pool that uses the file store, and do the following:</span></span>

8. <span data-ttu-id="1708b-120">Fare clic con il pulsante destro del mouse sul server o sul pool e **quindi scegliere Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1708b-120">Right-click the server or pool, and then click **Edit Properties**.</span></span>

9. <span data-ttu-id="1708b-121">In **Modifica proprietà,** in **Associazioni,** in **Archivio file** fare clic su **Nuovo.**</span><span class="sxs-lookup"><span data-stu-id="1708b-121">In **Edit properties**, under **Associations**, under **File store**, click **New**.</span></span>

10. <span data-ttu-id="1708b-122">In **Definisci nuovo archivio file** digitare il nome di dominio completo (FQDN) del file server in **FQDN** file server.</span><span class="sxs-lookup"><span data-stu-id="1708b-122">In **Define New File Store**, under **File server FQDN**, type the fully qualified domain name (FQDN) of the file server.</span></span> <span data-ttu-id="1708b-123">In **Condivisione file** digitare il nome della cartella per la nuova condivisione file e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="1708b-123">Under **File share**, type the folder name for the new file share, and then click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="1708b-124">In questo passaggio viene definito un nuovo archivio file da utilizzare in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="1708b-124">This step defines a new file store for use in Topology Builder.</span></span> <span data-ttu-id="1708b-125">È possibile definirlo una sola volta, non per ogni server.</span><span class="sxs-lookup"><span data-stu-id="1708b-125">You define it only once, not for each server.</span></span> <span data-ttu-id="1708b-126">Prima di pubblicare la topologia è necessario creare l'archivio file definito nel file server definito.</span><span class="sxs-lookup"><span data-stu-id="1708b-126">Before you publish the topology, you must create the defined file share on the defined file server.</span></span> <span data-ttu-id="1708b-127">Per informazioni dettagliate, vedere [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).</span><span class="sxs-lookup"><span data-stu-id="1708b-127">For details, see [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).</span></span>

11. <span data-ttu-id="1708b-128">Per ogni server o pool che utilizza l'archivio file, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1708b-128">For each server or pool that uses the file store, do the following:</span></span>

12. <span data-ttu-id="1708b-129">Fare clic con il pulsante destro del mouse sul server o sul pool e **quindi scegliere Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1708b-129">Right-click the server or pool, and then click **Edit properties**.</span></span>

13. <span data-ttu-id="1708b-130">In **Modifica proprietà,** in **Associazioni,** in **Archivio file,** selezionare la nuova condivisione file e quindi fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="1708b-130">In **Edit Properties**, under **Associations**, in **File store**, select the new file share, and then click **OK**.</span></span>

14. <span data-ttu-id="1708b-131">Pubblicare la topologia, controllare lo stato della replica ed eseguire la Distribuzione guidata di Skype for Business Server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="1708b-131">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> <span data-ttu-id="1708b-132">Per informazioni dettagliate, vedere [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).</span><span class="sxs-lookup"><span data-stu-id="1708b-132">For details, see [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).</span></span>

15. <span data-ttu-id="1708b-133">Avviare un prompt dei comandi: fare clic sul **pulsante Start,** scegliere **Esegui** e quindi digitare cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="1708b-133">Start a command prompt: Click **Start**, click **Run**, and then type cmd.exe.</span></span>

16. <span data-ttu-id="1708b-134">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1708b-134">At the command line, type the following:</span></span>

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > <span data-ttu-id="1708b-135">L'opzione /S consente di copiare file, directory e sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="1708b-135">The /S switch copies over files, directories and subdirectories.</span></span> <span data-ttu-id="1708b-136">L'opzione /XF ignora tutti i file denominati Meeting.Active.</span><span class="sxs-lookup"><span data-stu-id="1708b-136">The /XF switch skips any files that are named Meeting.Active.</span></span> <span data-ttu-id="1708b-137">Le versioni correnti di robocopy.exe con il parametro /MT offrono una velocità di copia notevolmente superiore grazie all'utilizzo di più thread.</span><span class="sxs-lookup"><span data-stu-id="1708b-137">Current versions of the robocopy.exe with the /MT switch greatly increase copy speed by using multiple threads.</span></span> <span data-ttu-id="1708b-138">Per l'opzione /LOG, utilizzare un percorso di directory e un nome di file di registro sotto forma di C:\Logfiles\log.txt.</span><span class="sxs-lookup"><span data-stu-id="1708b-138">For the /LOG switch, use a directory path and log file name in the form of C:\Logfiles\log.txt.</span></span> <span data-ttu-id="1708b-139">Questa opzione consente di creare un file di registro delle operazioni nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="1708b-139">This switch creates a log file of operations at the named location.</span></span>

17. <span data-ttu-id="1708b-140">Al termine della copia dei dati, nel Pannello di controllo di Lync Server fare clic su **Topologia** e quindi su **Stato.**</span><span class="sxs-lookup"><span data-stu-id="1708b-140">When the data copy is complete, in Lync Server Control Panel, click **Topology**, and then click **Status**.</span></span>

18. <span data-ttu-id="1708b-141">Per ogni server o pool in cui sono stati arrestati i servizi, selezionare il server o il pool, fare clic su **Azione** e quindi su **Avvia tutti i servizi.**</span><span class="sxs-lookup"><span data-stu-id="1708b-141">For each server or pool where you stopped services, select the server or pool, click **Action**, and then click **Start all services**.</span></span>

19. <span data-ttu-id="1708b-142">Rimuovere il vecchio archivio file dalla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="1708b-142">Remove the old file store from the topology and then publish the topology.</span></span> <span data-ttu-id="1708b-143">Per informazioni dettagliate, vedere [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).</span><span class="sxs-lookup"><span data-stu-id="1708b-143">For details, see [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).</span></span>

20. <span data-ttu-id="1708b-144">(Facoltativo) Accedere al computer che contiene l'archivio file appena rimosso come membro del gruppo Administrators locale o del gruppo Domain Admins, quindi rimuovere la vecchia condivisione file e la vecchia directory.</span><span class="sxs-lookup"><span data-stu-id="1708b-144">(Optional) Log on to the computer that contains the file store that you just removed as a member of the local Administrators group or the Domain Admins group, and then remove the old file share and directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="1708b-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1708b-145">See also</span></span>

<span data-ttu-id="1708b-146">[Riassegnare un server a un archivio file diverso](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="1708b-146">[Reassign a Server to a Different File Store](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))</span></span>

<span data-ttu-id="1708b-147">[Rimuovere un archivio file](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span><span class="sxs-lookup"><span data-stu-id="1708b-147">[Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))</span></span>