---
title: "Lync Server 2013: configurazione di Lync Server per l'utilizzo dell'archivio contatti unificato"
description: "Lync Server 2013: configurazione di Lync Server per l'utilizzo dell'archivio contatti unificato."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6905d2e393fec36fe5db3e40ee20087c0cca0991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570792"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a><span data-ttu-id="e0dd5-103">Configurazione di Microsoft Lync Server 2013 per l'utilizzo dell'archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="e0dd5-103">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0dd5-104">_**Ultimo argomento modificato:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="e0dd5-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="e0dd5-105">L'archivio contatti unificato consente agli utenti di gestire un singolo elenco contatti e quindi di disporre di tali contatti in più applicazioni, tra cui Microsoft Lync 2013, Microsoft Outlook 2013 e Microsoft Outlook Web App 2013.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-105">The unified contact store enables users to maintain a single contacts list and then have those contacts available in multiple applications, including Microsoft Lync 2013, Microsoft Outlook 2013, and Microsoft Outlook Web App 2013.</span></span> <span data-ttu-id="e0dd5-106">Quando si Abilita l'archivio contatti unificato per un utente, i contatti dell'utente non vengono archiviati in Microsoft Lync Server 2013 e quindi vengono recuperati utilizzando il protocollo SIP.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-106">When you enable the unified contact store for a user that user's contacts are not stored in Microsoft Lync Server 2013 and then retrieved using the SIP protocol.</span></span> <span data-ttu-id="e0dd5-107">Al contrario, i suoi contatti sono archiviati in Microsoft Exchange Server 2013 e vengono recuperati tramite i servizi Web di Exchange.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-107">Instead, his or her contacts are stored in Microsoft Exchange Server 2013 and are retrieved by using Exchange Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0dd5-108">Tecnicamente, le informazioni di contatto vengono memorizzate in una coppia di cartelle trovate nella cassetta postale di Exchange 2013 dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-108">Technically, contact information is stored in a pair of folders found in the user's Exchange 2013 mailbox.</span></span> <span data-ttu-id="e0dd5-109">I contatti stessi sono archiviati in una cartella denominata Lync contacts, visibile agli utenti finali. i metadati relativi ai contatti sono archiviati in una sottocartella che non è visibile agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-109">The contacts themselves are stored in a folder named Lync Contacts which is visible to end users; metadata about the contacts are stored in a subfolder that is not visible to end users.</span></span>



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a><span data-ttu-id="e0dd5-110">Abilitazione dell'archivio unificato per i contatti di un utente</span><span class="sxs-lookup"><span data-stu-id="e0dd5-110">Enabling the Unified Contact Store for a User</span></span>

<span data-ttu-id="e0dd5-111">Se è già stata configurata l'autenticazione da server a server tra Lync Server 2013 ed Exchange 2013, è stato anche abilitato l'utilizzo dell'archivio contatti unificato. non è necessaria alcuna configurazione aggiuntiva del server.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-111">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you have also enabled the use of the unified contact store; no additional server configuration is required.</span></span> <span data-ttu-id="e0dd5-112">Tuttavia, per spostare i contatti di un utente all'interno dell'archivio unificato è necessaria la configurazione di un ulteriore account utente.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-112">However, additional user account configuration is required in order to move a user's contacts into the unified contact store.</span></span> <span data-ttu-id="e0dd5-113">Per impostazione predefinita, i contatti dell'utente vengono conservati in Lync Server e non nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-113">By default, user contacts are kept in Lync Server and not in the unified contact store.</span></span>

<span data-ttu-id="e0dd5-114">L'accesso all'archivio contatti unificato viene gestito utilizzando i criteri dei servizi utente di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-114">Access to the unified contact store is managed by using Lync Server user services policies.</span></span> <span data-ttu-id="e0dd5-115">I criteri sono dotati di una proprietà singola (UcsAllowed), utilizzata per determinare il percorso in cui sono archiviati i contatti di un utente.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-115">User server policies have only a single property (UcsAllowed); this property is used to determine the location where a user's contacts are stored.</span></span> <span data-ttu-id="e0dd5-116">Se un utente è gestito da un criterio dei servizi utente in cui UcsAllowed impostato è stato impostato su true ($True), i contatti dell'utente verranno archiviati nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-116">If a user is managed by a user services policy where UcsAllowed has been set to True ($True) then the user's contacts will be stored in the unified contact store.</span></span> <span data-ttu-id="e0dd5-117">Se l'utente è gestito da un criterio dei servizi utente in cui UcsAllowed impostato è stato impostato su false ($False), i suoi contatti verranno archiviati in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-117">If the user is managed by a user services policy where UcsAllowed has been set to False ($False) then his or her contacts will be stored in Lync Server.</span></span>

<span data-ttu-id="e0dd5-118">Quando si installa Lync Server 2013, viene installato anche un criterio per i servizi utente singoli (configurato nell'ambito globale).</span><span class="sxs-lookup"><span data-stu-id="e0dd5-118">When you install Lync Server 2013 a single user services policy (configured at the global scope) is installed as well.</span></span> <span data-ttu-id="e0dd5-119">Il valore di UcsAllowed impostato in questo criterio è impostato su true, in modo che, per impostazione predefinita, i contatti utente vengano archiviati nell'archivio contatti unificato, presupponendo che sia stato distribuito e configurato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-119">The UcsAllowed value in this policy is set to True, meaning that, by default, user contacts will be stored in the unified contact store (assuming this has been deployed and configured).</span></span> <span data-ttu-id="e0dd5-120">Se si desidera eseguire la migrazione di tutti i contatti utente nell'archivio contatti unificato, non è necessario eseguire alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-120">If you want to migrate all of your user contacts to the unified contact store you do not have to do anything at all.</span></span>

<span data-ttu-id="e0dd5-121">Se si preferisce non eseguire la migrazione di tutti i contatti nell'archivio contatti unificato, è possibile disabilitare l'archivio contatti unificato per tutti gli utenti impostando la proprietà UcsAllowed impostato nel criterio globale su false:</span><span class="sxs-lookup"><span data-stu-id="e0dd5-121">If you would prefer not to migrate all your contacts to the unified contact store you can disable the unified contact store for all users by setting the UcsAllowed property in the global policy to False:</span></span>

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

<span data-ttu-id="e0dd5-122">Dopo aver disabilitato l'archivio contatti unificato nel criterio globale, è possibile creare un criterio per utente che consenta l'utilizzo dell'archivio contatti unificato. in questo modo è possibile che alcuni utenti mantengano i propri contatti nell'archivio contatti unificato, mentre altri utenti continuano a mantenere i propri contatti in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-122">After you have disabled the unified contact store in the global policy you can then create a per-user policy that enables the use of the unified contact store; this allows you to have some users keep their contacts in the unified contact store while other users continue to keep their contacts in Lync Server.</span></span> <span data-ttu-id="e0dd5-123">È possibile creare un criterio dei servizi utente per utente utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e0dd5-123">You can create a per-user user services policy by using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

<span data-ttu-id="e0dd5-p107">Dopo aver creato il nuovo criterio, bisognerà assegnarlo agli utenti ai quali si desidera concedere l'accesso all'archivio unificato per i contatti. I criteri "per utente" possono essere assegnati agli utenti attraverso un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e0dd5-p107">After you have created the new policy you must then assign that policy to any user who should have access to the unified contact store. Per-user policies can be assigned to users by using commands similar to this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

<span data-ttu-id="e0dd5-126">Dopo che il criterio è stato assegnato, Lync Server inizierà a eseguire la migrazione dei contatti dell'utente nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-126">After the policy has been assigned Lync Server will begin to migrate the user's contacts to the unified contact store.</span></span> <span data-ttu-id="e0dd5-127">Al termine della migrazione, l'utente riceverà i propri contatti archiviati in Exchange anziché in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-127">After migration is complete, the user will then have his or her contacts stored in Exchange rather than Lync Server.</span></span> <span data-ttu-id="e0dd5-128">Se l'utente è connesso a Lync 2013 al termine della migrazione, viene visualizzata una finestra di messaggio e gli viene chiesto di disconnettersi da Lync e quindi di eseguire l'accesso per completare il processo.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-128">If the user happens to be logged on to Lync 2013 at the time migration completes, a message box will appear and he or she will be asked to log off of Lync and then log back on in order to finalize the process.</span></span> <span data-ttu-id="e0dd5-129">Gli utenti a cui non è stato assegnato il criterio per utente non avranno la migrazione dei contatti nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-129">Users who have not been assigned this per-user policy will not have their contacts migrated to the unified contact store.</span></span> <span data-ttu-id="e0dd5-130">Ciò è dovuto al fatto che gli utenti vengono gestiti dal criterio globale e l'utilizzo dell'archivio contatti unificato è stato disabilitato nei criteri globali.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-130">That’s because those users are being managed by the global policy, and use of the unified contact store has been disabled in the global policy.</span></span>

<span data-ttu-id="e0dd5-131">È possibile verificare che i contatti di un utente siano stati correttamente migrati nell'archivio contatti unificato eseguendo il cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="e0dd5-131">You can verify that a user's contacts have successfully been migrated to the unified contact store by running the [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet from within the Lync Server Management Shell:</span></span>

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e0dd5-132">Se il cmdlet Test-CsUnifiedContactStore è eseguito con successo, i contatti del sip:kenmyer@litwareinc.com sono stati migrati correttamente all'archivio unificato per i contatti.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-132">If Test-CsUnifiedContactStore succeeds that means that the contacts for the user sip:kenmyer@litwareinc.com have been migrated to the unified contact store.</span></span>

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a><span data-ttu-id="e0dd5-133">Rollback (ripristino) dell'archivio unificato per i contatti</span><span class="sxs-lookup"><span data-stu-id="e0dd5-133">Rolling Back the Unified Contact Store</span></span>

<span data-ttu-id="e0dd5-134">Se è necessario rimuovere i contatti di un utente dall'archivio contatti unificato, ad esempio se l'utente deve essere reinstallato in Microsoft Lync Server 2010 e pertanto non è più in grado di utilizzare l'archivio contatti unificato, è necessario eseguire due operazioni.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-134">If you need to remove a user's contacts from the unified contact store (for example, if the user needs to be rehomed on Microsoft Lync Server 2010 and thus can no longer use the unified contact store) you must do two things.</span></span> <span data-ttu-id="e0dd5-135">Per prima cosa, è necessario assegnare all'utente un nuovo criterio dei servizi utente, che vieti l'archiviazione dei contatti nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-135">First, you must assign the user a new user services policy, one that prohibits storing contacts in the unified contact store.</span></span> <span data-ttu-id="e0dd5-136">(Ovvero, un criterio in cui la proprietà UcsAllowed impostato è stata impostata su $False). Se non si dispone di un criterio di questo tipo, è possibile crearne uno utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e0dd5-136">(That is, a policy where the UcsAllowed property has been set to $False.) If you do not have such a policy you can create one using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

<span data-ttu-id="e0dd5-137">È quindi possibile assegnare il nuovo criterio "per utente" (NoUnifiedContactStore) attraverso un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e0dd5-137">You can then assign this new per-user policy (NoUnifiedContactStore) by using a command like this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

<span data-ttu-id="e0dd5-138">Questo comando assegna all'utente Ken Myer il nuovo criterio, e fa in modo che i contatti di Ken non vengano migrati all'archivio unificato per i contatti.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-138">The preceding command assigns the new policy to the user Ken Myer, and also prevents Ken's contacts from being migrated to the unified contact store.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0dd5-p110">In alcuni casi è possibile ottenere lo stesso risultato semplicemente annullando il criterio dei servizi utente dall'utente in questione. Supponiamo, ad esempio, che a Ken Myer sia assegnato un criterio dei servizi utente di tipo "per utente", che attiva l'archivio unificato per i contatti, e che il criterio globale proibisce l'utilizzo di quest'ultimo. In questo caso, è possibile annullare il criterio dei servizi utente di tipo "per utente" da Ken. In questo modo, Ken sarà gestito automaticamente dal criterio globale, e non avrà più accesso all'archivio unificato per i contatti.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-p110">In some cases you can achieve the same net effect by simply unassigning the user's current user services policy. For example, suppose Ken Myer has a per-user user services policy the enables the unified contact store, but your global policy prohibits the use of the unified contact store. In that case, you could unassign Ken's per-user services policy. When you do that, Ken will automatically be managed by the global policy, and thus will no longer have access to the unified contact store.</span></span><BR><span data-ttu-id="e0dd5-143">Per annullare l'assegnazione di un criterio per utente precedentemente assegnato, utilizzare lo stesso comando illustrato in precedenza, ma impostare il parametro PolicyName su un valore null:</span><span class="sxs-lookup"><span data-stu-id="e0dd5-143">To unassign a previously-assigned per-user policy, use the same command as shown before, but this time set the PolicyName parameter to a null value:</span></span><BR><span data-ttu-id="e0dd5-144">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="e0dd5-144">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



</div>

<span data-ttu-id="e0dd5-145">La terminologia "impedisce la migrazione dei contatti di Ken nell'archivio contatti unificato" è importante da tenere presente quando si lavora con l'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-145">The terminology "prevents Ken's contacts from being migrated to the unified contact store" is important to keep in mind when working with the unified contact store.</span></span> <span data-ttu-id="e0dd5-146">Semplicemente assegnando a Ken un nuovo criterio dei servizi utente non sposterà i suoi contatti dall'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-146">Simply assigning Ken a new user services policy will not move his contacts out of the unified contact store.</span></span> <span data-ttu-id="e0dd5-147">Quando un utente accede a Lync Server 2013, il sistema verifica il criterio dei servizi utente dell'utente per verificare se i propri contatti devono essere conservati nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-147">When a user logs on to Lync Server 2013, the system checks the user's user services policy to see whether his or her contacts should be kept in the unified contact store.</span></span> <span data-ttu-id="e0dd5-148">Se la risposta è sì, ovvero se la proprietà UcsAllowed impostato è impostata su $True, i contatti verranno migrati nell'archivio contatti unificato, presupponendo che i contatti non siano già presenti nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-148">If the answer is yes (that is, if the UcsAllowed property is set to $True) then those contacts will be migrated to the unified contact store (assuming that those contacts are not already in the unified contact store).</span></span> <span data-ttu-id="e0dd5-149">Se la risposta è No, Lync Server ignora semplicemente i contatti dell'utente e passa alla relativa attività successiva.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-149">If the answer is no, then Lync Server simply ignores the user's contacts and moves on to its next task.</span></span> <span data-ttu-id="e0dd5-150">Questo significa che Lync Server non sposterà automaticamente i contatti di un utente dall'archivio contatti unificato, indipendentemente dal valore della proprietà UcsAllowed impostato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-150">That means that Lync Server will not automatically move a user's contacts from out of the unified contact store, regardless of the value of the UcsAllowed property.</span></span>

<span data-ttu-id="e0dd5-151">Questo significa anche che, dopo aver assegnato un nuovo criterio ai servizi utente, è necessario eseguire il cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) per spostare i contatti dell'utente fuori da Exchange 2013 e viceversa in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-151">That also means that, after assigning the user a new user services policy, you must then run the [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet in order to move the user's contacts out of Exchange 2013 and back to Lync Server 2013.</span></span> <span data-ttu-id="e0dd5-152">Ad esempio, dopo avere assegnato a Ken Myer un nuovo criterio dei servizi utente, è possibile spostare i suoi contatti fuori dall'archivio unificato per i contatti, utilizzando il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="e0dd5-152">For example, after assigning Ken Myer a new user services policy you can then move his contacts out of the unified contact store by using the following command:</span></span>

    Invoke-CsUcsRollback -Identity "Ken Myer"

<span data-ttu-id="e0dd5-153">Se si modifica il criterio dei servizi utente ma non si esegue il cmdlet Invoke-CsUcsRollback, i contatti di Ken non saranno rimossi dall'archivio unificato per i contatti.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-153">If you change the user services policy but do not run the Invoke-CsUcsRollback cmdlet Ken's contacts will not be removed from the unified contact store.</span></span> <span data-ttu-id="e0dd5-154">Cosa succede se si esegue il cmdlet Invoke-CsUcsRollback ma non si modifica il criterio dei servizi utente di Ken Myer?</span><span class="sxs-lookup"><span data-stu-id="e0dd5-154">What if you run Invoke-CsUcsRollback but do not change Ken Myer's user services policy?</span></span> <span data-ttu-id="e0dd5-155">In questo caso, i contatti di Ken vengono rimossi temporaneamente dall'archivio unificato per i contatti.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-155">In that case, Ken's contacts will be temporarily removed from the unified contact store.</span></span> <span data-ttu-id="e0dd5-156">È importante ricordare che questa rimozione è temporanea.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-156">The fact that this removal is temporary is important to keep in mind.</span></span> <span data-ttu-id="e0dd5-157">Dopo che i contatti di Ken sono stati rimossi dall'archivio contatti unificato, Lync Server 2013 attenderà 7 giorni e quindi verificherà quali criteri di servizi utente sono stati assegnati a Ken.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-157">After Ken's contacts have been removed from the unified contact store, Lync Server 2013 will wait 7 days and then check to see which user services policy has been assigned to Ken.</span></span> <span data-ttu-id="e0dd5-158">Se a Ken è ancora assegnato un criterio che consente l'utilizzo dell'archivio unificato per i contatti, i contatti saranno automaticamente spostati nuovamente nell'archivio unificato per i contatti.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-158">If Ken is still assigned a policy that enables the user of the unified contact store, then his contacts will automatically be moved back to into the contact store.</span></span> <span data-ttu-id="e0dd5-159">Per rimuovere temporaneamente i contatti dall'archivio unificato per i contatti, è necessario modificare il criterio dei servizi utente, oltre ad eseguire il cmdlet Invoke-CsUcsRollback.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-159">To permanently remove contacts from the unified contact store you must change the user services policy in addition to running the Invoke-CsUcsRollback cmdlet.</span></span>

<span data-ttu-id="e0dd5-160">A causa del numero elevato di variabili che possono influire sulla migrazione, è difficile stimare il tempo necessario prima che gli account vengano completamente migrati nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-160">Due to the large number of variables that can affect migration, it is difficult to estimate how long it will take before accounts are fully migrated to the unified contact store.</span></span> <span data-ttu-id="e0dd5-161">Come regola generale, tuttavia, la migrazione non ha effetto immediato: anche quando si esegue la migrazione di un numero limitato di contatti potrebbe essere necessario 10 minuti o più prima che lo spostamento sia stato completato.</span><span class="sxs-lookup"><span data-stu-id="e0dd5-161">As a general rule, however, migration does not take effect immediately: even when migrating a small number of contacts it might take 10 minutes or more before the move is complete.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

