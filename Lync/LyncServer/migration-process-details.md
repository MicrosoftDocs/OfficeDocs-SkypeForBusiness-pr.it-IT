---
title: Processo di migrazione-Dettagli
description: Processo di migrazione-dettagli.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8ecc5f23a328aef7cc65ad84e28dbb629d44b91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569582"
---
# <a name="migration-process---details"></a><span data-ttu-id="58b9c-103">Processo di migrazione-Dettagli</span><span class="sxs-lookup"><span data-stu-id="58b9c-103">Migration process - details</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58b9c-104">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="58b9c-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="58b9c-105">Utilizzare i prerequisiti seguenti e i passaggi dettagliati per eseguire la migrazione di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat in Lync Server 2013, Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="58b9c-105">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="58b9c-106">Prerequisiti per la migrazione</span><span class="sxs-lookup"><span data-stu-id="58b9c-106">Prerequisites for Migration</span></span>

<span data-ttu-id="58b9c-107">Assicurarsi di aver soddisfatto i prerequisiti seguenti prima di eseguire la migrazione di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat a Lync Server 2013, server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="58b9c-107">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="58b9c-108">Distribuire almeno un pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58b9c-108">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="58b9c-109">Se si dispone di più pool di Lync Server 2013, decidere quale pool di Lync Server 2013 sarà il pool Home per il nuovo pool di server Chat persistente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58b9c-109">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="58b9c-110">Installare il pool di server Chat persistente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58b9c-110">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="58b9c-111">Sarà vuoto (nessuna categoria, stanza o componente aggiuntivo).</span><span class="sxs-lookup"><span data-stu-id="58b9c-111">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="58b9c-112">Prima di eseguire la migrazione delle categorie, delle sale o dei componenti aggiuntivi legacy, è possibile creare sale, categorie o componenti aggiuntivi nella distribuzione di server Chat persistente in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58b9c-112">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="58b9c-113">Tenere presente che questi elementi appena creati possono essere in conflitto con gli elementi legacy di cui si esegue la migrazione.</span><span class="sxs-lookup"><span data-stu-id="58b9c-113">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="58b9c-114">Evitare conflitti di denominazione. in caso contrario, verranno sovrascritti quando si esegue la migrazione dei dati legacy.</span><span class="sxs-lookup"><span data-stu-id="58b9c-114">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="58b9c-115">Preparazione dei dati di origine per la migrazione</span><span class="sxs-lookup"><span data-stu-id="58b9c-115">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="58b9c-116">Eseguire la procedura seguente per preparare correttamente i dati di origine per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="58b9c-116">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="58b9c-117">Eseguire il backup dei database di origine per Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="58b9c-117">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="58b9c-118">Per informazioni dettagliate sul backup di SQL Server, vedere "Panoramica del backup (SQL Server)" all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=254851> .</span><span class="sxs-lookup"><span data-stu-id="58b9c-118">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <https://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="58b9c-119">I servizi di dominio Active Directory devono essere uguali.</span><span class="sxs-lookup"><span data-stu-id="58b9c-119">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="58b9c-120">Come condizione per la migrazione, non è possibile eseguire la migrazione a un pool in una distribuzione diversa, in particolare in una foresta di Active Directory diversa.</span><span class="sxs-lookup"><span data-stu-id="58b9c-120">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="58b9c-121">Esaminare le chat room e la configurazione delle categorie di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="58b9c-121">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="58b9c-122">Tutte le modifiche apportate alle categorie, alle sale o ai componenti aggiuntivi della distribuzione legacy esistente verranno eseguite dallo strumento di amministrazione di Group Chat.</span><span class="sxs-lookup"><span data-stu-id="58b9c-122">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="58b9c-123">Tutte le modifiche apportate alle categorie, alle sale o ai componenti aggiuntivi di Lync Server 2013, la distribuzione del server Chat persistente vengono eseguite dal pannello di controllo di Lync Server o dai cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58b9c-123">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="58b9c-124">Eseguire la procedura seguente per preparare il sistema legacy per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="58b9c-124">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="58b9c-125">Il server Chat persistente supporta un singolo livello di categorie, a differenza di un insieme gerarchico di categorie.</span><span class="sxs-lookup"><span data-stu-id="58b9c-125">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="58b9c-126">Dopo la migrazione, le sottocategorie sono prefissate con nomi di categoria completi padre.</span><span class="sxs-lookup"><span data-stu-id="58b9c-126">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="58b9c-127">Potrebbe essere necessario semplificare e appiattire la struttura delle categorie esistente in modo che la struttura risultante soddisfi i requisiti.</span><span class="sxs-lookup"><span data-stu-id="58b9c-127">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="58b9c-128">Verificare i **responsabili** nella categoria radice.</span><span class="sxs-lookup"><span data-stu-id="58b9c-128">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="58b9c-129">Se esistono Manager a questo livello, tali utenti verranno aggiunti come **Manager a tutte le sale** dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="58b9c-129">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="58b9c-130">Se non si tratta di un requisito per l'organizzazione, è necessario rimuovere questi Manager dalla categoria radice.</span><span class="sxs-lookup"><span data-stu-id="58b9c-130">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="58b9c-131">Verificare la lunghezza dei nomi delle chat.</span><span class="sxs-lookup"><span data-stu-id="58b9c-131">Verify the length of room names.</span></span> <span data-ttu-id="58b9c-132">Dopo la migrazione, a causa di strutture di categoria semplificate, se le camere sono presenti in una categoria figlio, sono preceduti da nomi di categoria completi padre.</span><span class="sxs-lookup"><span data-stu-id="58b9c-132">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="58b9c-133">Il limite di denominazione è 256 caratteri, inclusi i nomi delle categorie padre.</span><span class="sxs-lookup"><span data-stu-id="58b9c-133">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="58b9c-134">Se è troppo lungo, è necessario verificare la lunghezza dei nomi delle sale e possibilmente accorciare la lunghezza.</span><span class="sxs-lookup"><span data-stu-id="58b9c-134">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="58b9c-135">In Lync Server 2013, se le impostazioni per gli **inviti** di categoria sono impostate su true, è possibile scegliere True o false per gli inviti alle chat room della categoria.</span><span class="sxs-lookup"><span data-stu-id="58b9c-135">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="58b9c-136">Tuttavia, se le impostazioni per gli inviti di categoria sono impostate su false, le sale di quella categoria dispongono di inviti disattivati.</span><span class="sxs-lookup"><span data-stu-id="58b9c-136">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="58b9c-137">Prima di eseguire la migrazione, è necessario reimpostare le impostazioni degli inviti nella versione legacy di Lync Server Group Chat Server, se si desidera che le sale siano presenti in una categoria specifica.</span><span class="sxs-lookup"><span data-stu-id="58b9c-137">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="58b9c-138">In caso contrario, durante la migrazione, Lync Server 2013 Visualizza gli avvisi e imposta le sale sul valore predefinito false.</span><span class="sxs-lookup"><span data-stu-id="58b9c-138">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="58b9c-139">Se sono stati utilizzati file nelle chat room, è necessario eseguire il XCOPY dei file manualmente nel nuovo archivio file di Persistent Chat dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="58b9c-139">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="58b9c-140">Gli strumenti non lo fanno.</span><span class="sxs-lookup"><span data-stu-id="58b9c-140">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="58b9c-141">Se si disponeva di utenti federati e di stanze con utenti federati, tenere presente che il server Chat persistente non supporta la Federazione.</span><span class="sxs-lookup"><span data-stu-id="58b9c-141">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="58b9c-142">Verrà eseguita la migrazione delle sale con gli utenti federati. Tuttavia, gli utenti stessi non saranno in grado di accedere al contenuto, perché l'accesso federato non è supportato.</span><span class="sxs-lookup"><span data-stu-id="58b9c-142">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="58b9c-143">Identificare le sale di cui non si desidera eseguire la migrazione e contrassegnarle come disabilitate.</span><span class="sxs-lookup"><span data-stu-id="58b9c-143">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="58b9c-144">Identificare la data oltre la quale si desidera eseguire la migrazione del contenuto della chat room.</span><span class="sxs-lookup"><span data-stu-id="58b9c-144">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="58b9c-145">Ad esempio, potrebbe non essere necessario eseguire la migrazione dei messaggi prima del 1 ° gennaio 2010, in quanto questi messaggi possono essere obsoleti o non rilevanti per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="58b9c-145">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="58b9c-146">Esecuzione della migrazione</span><span class="sxs-lookup"><span data-stu-id="58b9c-146">Performing the Migration</span></span>

<span data-ttu-id="58b9c-147">Eseguire la procedura seguente per eseguire la migrazione del server di chat di gruppo legacy.</span><span class="sxs-lookup"><span data-stu-id="58b9c-147">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="58b9c-148">Arrestare i servizi server Chat persistente di Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58b9c-148">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="58b9c-149">Tutti i servizi devono essere interrotti, quindi pianificare l'operazione in un momento in cui il tempo di inattività è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="58b9c-149">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="58b9c-150">Come descritto in precedenza, assicurarsi di eseguire il backup del database di Group Chat corrente.</span><span class="sxs-lookup"><span data-stu-id="58b9c-150">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="58b9c-151">Eseguire il cmdlet **Export-CsPersistentChatData** di Windows PowerShell come membro del ruolo di amministratore RBAC di Persistent Chat (ruolo CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="58b9c-151">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="58b9c-152">Per informazioni dettagliate sui cmdlet per l'esportazione e l'importazione, vedere [risoluzione dei problemi relativi alla configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell in Lync server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="58b9c-152">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="58b9c-153">Esaminare il contenuto esportato.</span><span class="sxs-lookup"><span data-stu-id="58b9c-153">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="58b9c-154">Prima di essere pronti per l'importazione, arrestare Lync Server 2013, servizi del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="58b9c-154">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="58b9c-155">Tutti i servizi devono essere interrotti, quindi pianificare l'operazione in un momento in cui il tempo di inattività è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="58b9c-155">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="58b9c-156">Eseguire un backup del database di Persistent Chat se sono state create categorie, sale o componenti aggiuntivi nella distribuzione di Lync Server 2013 prima della migrazione.</span><span class="sxs-lookup"><span data-stu-id="58b9c-156">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="58b9c-157">Il processo di esportazione/importazione sarà in grado di unire i dati legacy nella distribuzione di Lync Server 2013, ma è consigliabile eseguire il backup del database nel caso in cui il contenuto venga inavvertitamente sovrascritto (ad esempio, se esistono ancora conflitti di denominazione).</span><span class="sxs-lookup"><span data-stu-id="58b9c-157">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="58b9c-158">Eseguire il cmdlet **Import-CsPersistentChatData** di Windows PowerShell (strumento di importazione), con un comando **whatIf** per popolare il server back-end del pool di server Chat persistente con i dati migrati.</span><span class="sxs-lookup"><span data-stu-id="58b9c-158">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="58b9c-159">Alcune conversioni si verificano nel processo per ospitare il modello di amministrazione semplificato.</span><span class="sxs-lookup"><span data-stu-id="58b9c-159">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="58b9c-160">Consente di risolvere eventuali errori o avvisi visualizzati.</span><span class="sxs-lookup"><span data-stu-id="58b9c-160">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="58b9c-161">Eseguire il cmdlet **Import-CsPersistentChatData** di Windows PowerShell per il server di chat persistente come membro del ruolo RBAC (ruolo CsPersistentChatAdministrator) Administrator di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="58b9c-161">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="58b9c-162">Per informazioni dettagliate sui cmdlet per l'esportazione e l'importazione, vedere [risoluzione dei problemi relativi alla configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell in Lync server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="58b9c-162">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="58b9c-163">È necessario XCOPY tutti i file caricati (l'intera cartella) nel nuovo archivio file di Lync Server 2013, Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="58b9c-163">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="58b9c-164">Lync 2013 (client) non supporta il caricamento o la visualizzazione di file nelle chat room.</span><span class="sxs-lookup"><span data-stu-id="58b9c-164">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="58b9c-165">È comunque possibile utilizzare il client legacy per inserire e visualizzare i file nella sala.</span><span class="sxs-lookup"><span data-stu-id="58b9c-165">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="58b9c-166">Porta l'URI del server di ricerca di Microsoft Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat all'oggetto contatto del server di chat persistente di Lync 2013 server.</span><span class="sxs-lookup"><span data-stu-id="58b9c-166">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="58b9c-167">I passaggi seguenti sono obbligatori se i client di chat di gruppo di Lync 2010 o di Office Communicator 2007 R2 devono connettersi all'ultima Lync 2013, Persistent Chat (client) dopo la migrazione senza modifiche alla configurazione sul fianco del client:</span><span class="sxs-lookup"><span data-stu-id="58b9c-167">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="58b9c-168">Eliminare l' \<domainName\> account utente del server di ricerca di OCSChat@. com.</span><span class="sxs-lookup"><span data-stu-id="58b9c-168">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="58b9c-169">Questo è stato utilizzato per puntare al servizio di ricerca in Lync Server 2010, Group Chat.</span><span class="sxs-lookup"><span data-stu-id="58b9c-169">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="58b9c-170">È possibile disinstallare il pool e rimuovere le voci attendibili in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="58b9c-170">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="58b9c-171">Creare un endpoint legacy (oggetto contatto del server Chat persistente) eseguendo il cmdlet di Windows PowerShell **New-CsPersistentChatEndpoint**con l'URI SIP identico in modo che il client legacy funzioni efficacemente quando il servizio viene riavviato.</span><span class="sxs-lookup"><span data-stu-id="58b9c-171">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="58b9c-172">Il processo di migrazione obbligatoria è stato completato a questo punto.</span><span class="sxs-lookup"><span data-stu-id="58b9c-172">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="58b9c-173">Lync 2010 Group Chat (clients) o Office Communicator 2007 R2 Group Chat (client) è in grado di connettersi al nuovo pool di server Chat persistente ora, in modo trasparente.</span><span class="sxs-lookup"><span data-stu-id="58b9c-173">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="58b9c-174">Seguire questi passaggi aggiuntivi per la rimozione delle autorizzazioni per Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="58b9c-174">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="58b9c-175">Avviare i servizi del server Chat persistente attivando tutti i computer nel nuovo pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="58b9c-175">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="58b9c-176">Utilizzare il pannello di controllo di Lync Server e i cmdlet di Windows PowerShell per verificare che i dati siano stati migrati correttamente.</span><span class="sxs-lookup"><span data-stu-id="58b9c-176">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="58b9c-177">Disinstallare Lync 2010 Group Chat o Office Communicator 2007 R2 Group Chat dai computer del pool di Group Chat Server.</span><span class="sxs-lookup"><span data-stu-id="58b9c-177">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="58b9c-178">Eliminare l'applicazione attendibile e il pool di applicazioni attendibili utilizzando i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58b9c-178">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="58b9c-179">Questo elimina gli elementi dall'archivio di gestione centrale e dalle voci del servizio attendibili associate (TSE) da Active Directory.</span><span class="sxs-lookup"><span data-stu-id="58b9c-179">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="58b9c-180">In alternativa, questo passaggio è compatibile con il generatore di topologie (anche le applicazioni o i pool attendibili dispongono di un nodo dedicato).</span><span class="sxs-lookup"><span data-stu-id="58b9c-180">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="58b9c-181">È ora possibile iniziare a abilitare la funzionalità del server Chat persistente tramite i nuovi client.</span><span class="sxs-lookup"><span data-stu-id="58b9c-181">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="58b9c-182">Per informazioni dettagliate sull'abilitazione del server Chat persistente, vedere [Deploying Persistent Chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="58b9c-182">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="58b9c-183">Lync Server 2013 supporta più pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="58b9c-183">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="58b9c-184">Tuttavia, è possibile eseguire la migrazione di un pool di chat di gruppo di Lync 2010 o di Office Communications Server 2007 R2 &nbsp; a un singolo pool di server di chat persistente di Lync server 2013.</span><span class="sxs-lookup"><span data-stu-id="58b9c-184">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="58b9c-185">È possibile aggiungere ulteriori nuovi pool di server Chat persistente nella distribuzione per soddisfare i requisiti normativi, ad esempio per mantenere i dati all'interno di una determinata geografia.</span><span class="sxs-lookup"><span data-stu-id="58b9c-185">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

