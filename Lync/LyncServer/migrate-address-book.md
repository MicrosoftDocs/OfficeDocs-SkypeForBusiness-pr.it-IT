---
title: Eseguire la migrazione della rubrica
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3282315d50b0a5075afc380487fb9204d4285c8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529903"
---
# <a name="migrate-address-book"></a><span data-ttu-id="1b88c-102">Eseguire la migrazione della rubrica</span><span class="sxs-lookup"><span data-stu-id="1b88c-102">Migrate Address Book</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b88c-103">_**Ultimo argomento modificato:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="1b88c-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="1b88c-104">In generale, la Rubrica di Lync Server 2010 viene migrata insieme al resto della topologia.</span><span class="sxs-lookup"><span data-stu-id="1b88c-104">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="1b88c-105">Tuttavia, potrebbe essere necessario eseguire alcuni passaggi dopo la migrazione se sono stati personalizzati gli elementi seguenti nell'ambiente Lync Server 2010:</span><span class="sxs-lookup"><span data-stu-id="1b88c-105">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="1b88c-106">Impostazione della proprietà WMI **PartitionbyOU** per raggruppare le voci della Rubrica per unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="1b88c-106">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="1b88c-107">Personalizzazione delle regole di normalizzazione della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="1b88c-107">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="1b88c-108">Impostazione del valore predefinito del parametro **UseNormalizationRules** su False.</span><span class="sxs-lookup"><span data-stu-id="1b88c-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="1b88c-109">**Voci della Rubrica raggruppate**</span><span class="sxs-lookup"><span data-stu-id="1b88c-109">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="1b88c-p102">Se la proprietà WMI **PartitionbyOU** è stata impostata su True per creare una Rubrica per ogni unità organizzativa e si desidera continuare a raggruppare le voci della Rubrica, è necessario impostare l'attributo di Active Directory **msRTCSIP-GroupingId** per utenti e contatti. Per limitare l'ambito delle ricerche nella Rubrica è consigliabile raggruppare le voci della Rubrica. Per utilizzare l'attributo **msRTCSIP-GroupingId**, creare uno script per popolare l'attributo, assegnando lo stesso valore per tutti gli utenti che si desidera raggruppare. Ad esempio, assegnare un unico valore a tutti gli utenti di un'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="1b88c-p102">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries. You might want to group address book entries to limit the scope of Address Book searches. To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together. For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="1b88c-114">**Regole di normalizzazione della Rubrica**</span><span class="sxs-lookup"><span data-stu-id="1b88c-114">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="1b88c-115">Se sono state personalizzate le regole di normalizzazione della Rubrica nell'ambiente Lync Server 2010, è necessario eseguire la migrazione delle regole personalizzate nel pool pilota.</span><span class="sxs-lookup"><span data-stu-id="1b88c-115">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="1b88c-116">Se non è stata personalizzata alcuna regola di normalizzazione della Rubrica, non sarà necessario effettuare alcuna migrazione per il servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="1b88c-116">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="1b88c-117">Le regole di normalizzazione predefinite per Lync Server 2013 sono le stesse delle regole predefinite per Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b88c-117">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="1b88c-118">Eseguire la procedura descritta più avanti in questa sezione per eseguire la migrazione delle regole di normalizzazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="1b88c-118">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b88c-p104">Se nell'organizzazione viene utilizzato il controllo delle chiamate remote e le regole di normalizzazione della Rubrica sono state personalizzate, prima di utilizzare il controllo delle chiamate remote è necessario eseguire la procedura descritta in questo argomento. L'esecuzione della procedura richiede l'appartenenza al gruppo RTCUniversalServerAdmins o diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="1b88c-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="1b88c-121">**UseNormalizationRules impostato su False**</span><span class="sxs-lookup"><span data-stu-id="1b88c-121">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="1b88c-122">Se si imposta il valore di **UseNormalizationRules** su false in modo che gli utenti possano utilizzare i numeri di telefono come definito in servizi di dominio Active Directory senza che Lync Server 2013 applichi regole di normalizzazione, è necessario impostare i parametri **UseNormalizationRules** e **IgnoreGenericRules** su true.</span><span class="sxs-lookup"><span data-stu-id="1b88c-122">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="1b88c-123">Eseguire la procedura descritta più avanti in questa sezione per impostare tali parametri su True.</span><span class="sxs-lookup"><span data-stu-id="1b88c-123">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="1b88c-124">Per eseguire la migrazione delle regole di normalizzazione personalizzate della Rubrica</span><span class="sxs-lookup"><span data-stu-id="1b88c-124">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="1b88c-125">Individuare il \_ file di normalizzazione dei numeri di telefono dell'azienda \_ \_ \_Rules.txt nella radice della cartella condivisa della Rubrica e copiarlo nella radice della cartella condivisa della Rubrica nel pool pilota di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b88c-125">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1b88c-126">Le regole di normalizzazione della Rubrica di esempio sono state installate nella directory dei file dei componenti Web del Servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="1b88c-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="1b88c-127">Il percorso è <STRONG>$installedDriveLetter:\Programmi\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1b88c-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="1b88c-128">Questo file può essere copiato e rinominato come &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> nella &nbsp; directory radice della cartella condivisa della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="1b88c-128">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="1b88c-129">Ad esempio, la rubrica condivisa in <STRONG>$serverX</STRONG>, &nbsp; il percorso sarà analogo al seguente: <STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1b88c-129">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="1b88c-130">Utilizzare un editor di testo, ad esempio Blocco note, per aprire il \_ file di normalizzazione dei numeri di telefono dell'azienda \_ \_ \_Rules.txt.</span><span class="sxs-lookup"><span data-stu-id="1b88c-130">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="1b88c-131">Alcuni tipi di voci non funzioneranno correttamente in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b88c-131">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="1b88c-132">Cercare all'interno del file i tipi di voci descritti in questo passaggio, modificarli secondo necessità e salvare le modifiche nella cartella condivisa della Rubrica all'interno del pool pilota.</span><span class="sxs-lookup"><span data-stu-id="1b88c-132">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="1b88c-p108">Le stringhe che includono spazi o caratteri di punteggiatura necessari provocano un errore nelle regole di normalizzazione poiché tali caratteri vengono rimossi dalla stringa utilizzata come input nelle regole di normalizzazione. Se sono presenti stringhe che includono spazi o caratteri di punteggiatura necessari, è necessario modificare le stringhe. La stringa seguente, ad esempio, genererà un errore nelle regola di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="1b88c-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="1b88c-136">La stringa seguente non causerebbe alcun errore della regola di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="1b88c-136">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="1b88c-137">Per impostare UseNormalizationRules e IgnoreGenericRules su True</span><span class="sxs-lookup"><span data-stu-id="1b88c-137">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="1b88c-138">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1b88c-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1b88c-139">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b88c-139">Do one of the following:</span></span>
    
      - <span data-ttu-id="1b88c-140">Se la distribuzione include solo Lync Server 2013, eseguire il seguente cmdlet a livello globale per modificare i valori di **UseNormalizationRules** e **IgnoreGenericRules** su true:</span><span class="sxs-lookup"><span data-stu-id="1b88c-140">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="1b88c-141">Se nella distribuzione è inclusa una combinazione di Lync Server 2013 e Lync Server 2010 o Office Communications Server 2007 R2, eseguire il cmdlet seguente e assegnarlo a ogni pool Lync Server 2013 nella topologia:</span><span class="sxs-lookup"><span data-stu-id="1b88c-141">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="1b88c-142">Attendere che la replica dell'archivio di gestione centrale venga eseguita in tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="1b88c-142">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="1b88c-143">Modificare il file delle regole di normalizzazione del telefono, " \_ normalizzazione dei numeri di telefono dell'azienda \_ \_ \_Rules.txt", per la distribuzione per cancellare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="1b88c-143">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="1b88c-144">Il file si trova nella condivisione file di ogni pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b88c-144">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="1b88c-145">Se il file non è presente, creare un file vuoto denominato "società di \_ \_ normalizzazione numeri di telefono \_ \_Rules.txt".</span><span class="sxs-lookup"><span data-stu-id="1b88c-145">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="1b88c-146">Attendere alcuni minuti per tutti i pool Front end per leggere i nuovi file.</span><span class="sxs-lookup"><span data-stu-id="1b88c-146">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="1b88c-147">Eseguire il cmdlet seguente in ogni pool di Lync Server 2013 nella distribuzione:</span><span class="sxs-lookup"><span data-stu-id="1b88c-147">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

