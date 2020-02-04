---
title: Processo di migrazione - Dettagli
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d3b46e2b80d9ad5a4b08108d1dc2bad03cf5f0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a><span data-ttu-id="71cd7-102">Processo di migrazione - Dettagli</span><span class="sxs-lookup"><span data-stu-id="71cd7-102">Migration process - details</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71cd7-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="71cd7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="71cd7-104">Usare i prerequisiti seguenti e i passaggi dettagliati per eseguire la migrazione di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat in Lync Server 2013, Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="71cd7-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="71cd7-105">Prerequisiti per la migrazione</span><span class="sxs-lookup"><span data-stu-id="71cd7-105">Prerequisites for Migration</span></span>

<span data-ttu-id="71cd7-106">Verificare di avere soddisfatto i prerequisiti seguenti prima di eseguire la migrazione di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat a Lync Server 2013, Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="71cd7-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="71cd7-107">Distribuire almeno un pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71cd7-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="71cd7-108">Se si dispone di più pool di Lync Server 2013, decidere quale pool di Lync Server 2013 sarà il pool Home per il nuovo pool di server di chat persistente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71cd7-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="71cd7-109">Installare il pool di server di chat persistente di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71cd7-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="71cd7-110">Sarà vuota (nessun categorie, sale o componenti aggiuntivi).</span><span class="sxs-lookup"><span data-stu-id="71cd7-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="71cd7-111">Prima di eseguire la migrazione delle categorie, delle sale o dei componenti aggiuntivi legacy, è possibile creare sale, categorie o componenti aggiuntivi in Lync Server 2013, la distribuzione del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="71cd7-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="71cd7-112">Tieni presente che questi elementi appena creati potrebbero essere in conflitto con gli elementi legacy migrati.</span><span class="sxs-lookup"><span data-stu-id="71cd7-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="71cd7-113">Evitare qualsiasi conflitto di denominazione; in caso contrario, verranno sovrascritti quando si esegue la migrazione dei dati legacy.</span><span class="sxs-lookup"><span data-stu-id="71cd7-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="71cd7-114">Preparazione dei dati di origine per la migrazione</span><span class="sxs-lookup"><span data-stu-id="71cd7-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="71cd7-115">Eseguire la procedura seguente per preparare correttamente i dati di origine per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="71cd7-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="71cd7-116">Eseguire il backup dei database di origine per Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="71cd7-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="71cd7-117">Per informazioni dettagliate sul backup di SQL Server, vedere "Panoramica del backup (SQL Server)" <http://go.microsoft.com/fwlink/p/?linkid=254851>all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="71cd7-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <http://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="71cd7-118">I servizi di dominio Active Directory dovrebbero essere gli stessi.</span><span class="sxs-lookup"><span data-stu-id="71cd7-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="71cd7-119">Come condizione per la migrazione, non è possibile eseguire la migrazione a un pool in una distribuzione diversa (in particolare in una foresta di Active Directory diversa).</span><span class="sxs-lookup"><span data-stu-id="71cd7-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="71cd7-120">Esaminare le chat room e la configurazione delle categorie di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="71cd7-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="71cd7-121">Tutte le modifiche apportate alle categorie, alle sale o ai componenti aggiuntivi nella distribuzione legacy esistente verranno eseguite dallo strumento di amministrazione di Group Chat.</span><span class="sxs-lookup"><span data-stu-id="71cd7-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="71cd7-122">Qualsiasi modifica apportata a categorie, sale o componenti aggiuntivi in Lync Server 2013, la distribuzione del server di chat persistente viene eseguita dal pannello di controllo di Lync Server o dai cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71cd7-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="71cd7-123">Seguire questa procedura per preparare il sistema legacy per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="71cd7-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="71cd7-124">Il server di chat persistente supporta un singolo livello di categorie, a differenza di un set gerarchico profondo di categorie.</span><span class="sxs-lookup"><span data-stu-id="71cd7-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="71cd7-125">Dopo la migrazione, le sottocategorie sono prefissate con i nomi di categoria padre completo.</span><span class="sxs-lookup"><span data-stu-id="71cd7-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="71cd7-126">È consigliabile semplificare e appiattire la struttura delle categorie esistente in modo che la struttura risultante soddisfi le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="71cd7-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="71cd7-127">Verificare i **responsabili** della categoria radice.</span><span class="sxs-lookup"><span data-stu-id="71cd7-127">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="71cd7-128">Se sono presenti Manager di questo livello, questi utenti verranno aggiunti come **responsabili a tutte le sale** dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="71cd7-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="71cd7-129">Se non si tratta di un requisito per l'organizzazione, è necessario rimuovere questi Manager dalla categoria radice.</span><span class="sxs-lookup"><span data-stu-id="71cd7-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="71cd7-130">Verificare la lunghezza dei nomi delle chat room.</span><span class="sxs-lookup"><span data-stu-id="71cd7-130">Verify the length of room names.</span></span> <span data-ttu-id="71cd7-131">Dopo la migrazione, a causa di strutture di categoria semplificate, se le sale sono presenti in una categoria figlio, sono preceduti da nomi di categoria padre completo.</span><span class="sxs-lookup"><span data-stu-id="71cd7-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="71cd7-132">Il limite di denominazione è 256 caratteri, inclusi i nomi delle categorie padre.</span><span class="sxs-lookup"><span data-stu-id="71cd7-132">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="71cd7-133">È necessario verificare la lunghezza dei nomi delle stanze e possibilmente accorciare la lunghezza, se troppo lunga.</span><span class="sxs-lookup"><span data-stu-id="71cd7-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="71cd7-134">In Lync Server 2013, se le impostazioni per gli **inviti** alle categorie sono impostate su true, è possibile scegliere vero o falso per gli inviti alle camere in tale categoria.</span><span class="sxs-lookup"><span data-stu-id="71cd7-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="71cd7-135">Tuttavia, se le impostazioni per gli inviti alle categorie sono impostate su false, le sale in tale categoria hanno inviti disattivati.</span><span class="sxs-lookup"><span data-stu-id="71cd7-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="71cd7-136">Prima di eseguire la migrazione, è necessario reimpostare le impostazioni dell'invito nella versione legacy di Group Chat Server di Lync Server, se si vuole che le camere siano presenti in una categoria specifica.</span><span class="sxs-lookup"><span data-stu-id="71cd7-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="71cd7-137">In caso contrario, durante la migrazione, Lync Server 2013 Visualizza gli avvisi e imposta le camere sul valore predefinito false.</span><span class="sxs-lookup"><span data-stu-id="71cd7-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="71cd7-138">Se sono stati usati file nelle chat room, è necessario eseguire il XCOPY manuale dei file nel nuovo archivio di file della chat persistente dopo la migrazione.</span><span class="sxs-lookup"><span data-stu-id="71cd7-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="71cd7-139">Gli strumenti non lo fanno.</span><span class="sxs-lookup"><span data-stu-id="71cd7-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="71cd7-140">Se si dispone di utenti e camere federati con utenti federati, tenere presente che il server di chat persistente non supporta la Federazione.</span><span class="sxs-lookup"><span data-stu-id="71cd7-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="71cd7-141">Verranno migrate le camere con gli utenti federati; Tuttavia, gli utenti stessi non saranno in grado di accedere al contenuto, perché l'accesso federato non è supportato.</span><span class="sxs-lookup"><span data-stu-id="71cd7-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="71cd7-142">Identificare le sale di cui non si vuole eseguire la migrazione e contrassegnarle come disabilitate.</span><span class="sxs-lookup"><span data-stu-id="71cd7-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="71cd7-143">Identificare la data oltre la quale si vuole eseguire la migrazione del contenuto della chat room.</span><span class="sxs-lookup"><span data-stu-id="71cd7-143">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="71cd7-144">Ad esempio, potresti non voler eseguire la migrazione dei messaggi prima del 1 ° gennaio 2010, perché questi messaggi potrebbero essere obsoleti o non rilevanti per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="71cd7-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="71cd7-145">Esecuzione della migrazione</span><span class="sxs-lookup"><span data-stu-id="71cd7-145">Performing the Migration</span></span>

<span data-ttu-id="71cd7-146">Eseguire la procedura seguente per eseguire la migrazione del server di chat di gruppo legacy.</span><span class="sxs-lookup"><span data-stu-id="71cd7-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="71cd7-147">Arrestare Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat o Lync Server 2013, servizi di chat server permanenti.</span><span class="sxs-lookup"><span data-stu-id="71cd7-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="71cd7-148">Tutti i servizi devono essere interrotti, quindi pianificare questa operazione in un momento in cui si verificano tempi di inattività sufficienti.</span><span class="sxs-lookup"><span data-stu-id="71cd7-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="71cd7-149">Come descritto in precedenza, assicurati di eseguire il backup del database corrente della chat di gruppo.</span><span class="sxs-lookup"><span data-stu-id="71cd7-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="71cd7-150">Eseguire il cmdlet **Export-CsPersistentChatData** di Windows PowerShell come membro del ruolo di amministratore RBAC della chat persistente (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="71cd7-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="71cd7-151">Per informazioni dettagliate sui cmdlet di esportazione/importazione, vedere [risoluzione dei problemi relativi alla configurazione del server di chat persistente con i cmdlet di Windows PowerShell in Lync server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="71cd7-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="71cd7-152">Esaminare il contenuto esportato.</span><span class="sxs-lookup"><span data-stu-id="71cd7-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="71cd7-153">Prima di essere pronti per l'importazione, arrestare Lync Server 2013, servizi server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="71cd7-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="71cd7-154">Tutti i servizi devono essere interrotti, quindi pianificare questa operazione in un momento in cui si verificano tempi di inattività sufficienti.</span><span class="sxs-lookup"><span data-stu-id="71cd7-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="71cd7-155">Eseguire una copia di backup del database della chat persistente se sono state create categorie, sale o componenti aggiuntivi nella distribuzione di Lync Server 2013 prima della migrazione.</span><span class="sxs-lookup"><span data-stu-id="71cd7-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="71cd7-156">Il processo di esportazione/importazione sarà in grado di unire i dati legacy alla distribuzione di Lync Server 2013, ma si vorrà eseguire il backup del database nel caso in cui il contenuto venga sovrascritto in modo involontario, ad esempio se esistono ancora conflitti di denominazione.</span><span class="sxs-lookup"><span data-stu-id="71cd7-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="71cd7-157">Eseguire il cmdlet **Import-CsPersistentChatData** di Windows PowerShell (strumento di importazione), con un comando **whatIf** per popolare il server back-end del pool del server di chat persistente con i dati migrati.</span><span class="sxs-lookup"><span data-stu-id="71cd7-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="71cd7-158">Alcune conversioni si verificano nel processo per adattare il modello di amministrazione semplificato.</span><span class="sxs-lookup"><span data-stu-id="71cd7-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="71cd7-159">Correggere eventuali errori o avvisi visualizzati.</span><span class="sxs-lookup"><span data-stu-id="71cd7-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="71cd7-160">Eseguire il cmdlet **Import-CsPersistentChatData** di Windows PowerShell per il server di chat persistente come membro del ruolo di amministratore RBAC della chat persistente (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="71cd7-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="71cd7-161">Per informazioni dettagliate sui cmdlet di esportazione/importazione, vedere [risoluzione dei problemi relativi alla configurazione del server di chat persistente con i cmdlet di Windows PowerShell in Lync server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="71cd7-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="71cd7-162">È necessario XCOPY tutti i file caricati (l'intera cartella) nel nuovo Lync Server 2013, l'archivio di file della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="71cd7-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="71cd7-163">Lync 2013 (client) non supporta il caricamento o la visualizzazione di file nelle chat room.</span><span class="sxs-lookup"><span data-stu-id="71cd7-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="71cd7-164">È comunque possibile usare il client legacy per pubblicare e visualizzare i file nella sala.</span><span class="sxs-lookup"><span data-stu-id="71cd7-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="71cd7-165">Porta l'URI Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat Server Lookup a Lync Server 2013, l'oggetto contatto del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="71cd7-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="71cd7-166">I passaggi seguenti sono obbligatori se la chat di gruppo di Lync 2010 o i client di chat di gruppo di Office Communicator 2007 R2 devono connettersi alla versione più recente di Lync 2013, la chat persistente (client) dopo la migrazione senza alcuna modifica della configurazione lato client:</span><span class="sxs-lookup"><span data-stu-id="71cd7-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="71cd7-167">Eliminare l'account\<utente del\>Server di ricerca di OCSChat@ NomeDominio. com.</span><span class="sxs-lookup"><span data-stu-id="71cd7-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="71cd7-168">Questa operazione è stata usata per posizionare il puntatore del servizio di ricerca in Lync Server 2010, chat di gruppo.</span><span class="sxs-lookup"><span data-stu-id="71cd7-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="71cd7-169">È possibile disinstallare il pool e rimuovere le voci attendibili in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="71cd7-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="71cd7-170">Crea un endpoint legacy (oggetto Contact del server di chat persistente) eseguendo il cmdlet di Windows PowerShell, **New-CsPersistentChatEndpoint**, con l'URI SIP identico in modo che il client legacy funzioni efficacemente quando il servizio viene riavviato.</span><span class="sxs-lookup"><span data-stu-id="71cd7-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="71cd7-171">Il processo di migrazione obbligatoria è completato a questo punto.</span><span class="sxs-lookup"><span data-stu-id="71cd7-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="71cd7-172">Lync 2010 Group Chat (client) o Office Communicator 2007 R2 Group Chat (client) può connettersi al nuovo pool di server di chat persistente ora, in modo trasparente.</span><span class="sxs-lookup"><span data-stu-id="71cd7-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="71cd7-173">Seguire queste procedure aggiuntive per la disattivazione per Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat.</span><span class="sxs-lookup"><span data-stu-id="71cd7-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="71cd7-174">Avviare i servizi del server di chat persistente attivando tutti i computer nel nuovo pool del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="71cd7-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="71cd7-175">Utilizzare il pannello di controllo di Lync Server e i cmdlet di Windows PowerShell per verificare che i dati siano stati correttamente migrati.</span><span class="sxs-lookup"><span data-stu-id="71cd7-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="71cd7-176">Disinstallare Lync 2010 Group Chat o Office Communicator 2007 R2 Group Chat dai computer del pool di Group Chat Server.</span><span class="sxs-lookup"><span data-stu-id="71cd7-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="71cd7-177">Eliminare l'applicazione attendibile e il pool di applicazioni attendibili usando i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71cd7-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="71cd7-178">Questo elimina questi elementi dall'Central Management store e dalle voci di servizio attendibili associate (TSE) da Active Directory.</span><span class="sxs-lookup"><span data-stu-id="71cd7-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="71cd7-179">In alternativa, questo passaggio funziona usando il generatore di topologie (anche le applicazioni/i pool attendibili hanno un nodo dedicato).</span><span class="sxs-lookup"><span data-stu-id="71cd7-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="71cd7-180">Ora puoi iniziare a abilitare la funzionalità del server di chat persistente tramite i nuovi client.</span><span class="sxs-lookup"><span data-stu-id="71cd7-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="71cd7-181">Per informazioni dettagliate sull'abilitazione del server di chat persistente, vedere [distribuzione di un server di chat persistente in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="71cd7-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="71cd7-182">Lync Server 2013 supporta più pool di server di chat persistenti.</span><span class="sxs-lookup"><span data-stu-id="71cd7-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="71cd7-183">Tuttavia, sosteniamo la migrazione di una chat di gruppo di Lync 2010 o di&nbsp;un pool di chat di Office Communications Server 2007 R2 a un singolo pool di server di chat di lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71cd7-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="71cd7-184">È possibile aggiungere altri nuovi pool di server di chat persistenti nella distribuzione per soddisfare le esigenze di regolamentazione, ad esempio per mantenere i dati all'interno di una data geografia.</span><span class="sxs-lookup"><span data-stu-id="71cd7-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

