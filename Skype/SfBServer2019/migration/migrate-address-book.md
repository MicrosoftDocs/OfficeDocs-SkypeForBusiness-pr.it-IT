---
title: Eseguire la migrazione della rubrica
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
description: "In generale, la Rubrica viene migrata insieme al resto della topologia. Tuttavia, potrebbe essere necessario eseguire alcuni passaggi dopo la migrazione se sono stati personalizzati gli elementi seguenti nell'ambiente legacy:"
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752838"
---
# <a name="migrate-address-book"></a><span data-ttu-id="ec553-104">Eseguire la migrazione della rubrica</span><span class="sxs-lookup"><span data-stu-id="ec553-104">Migrate Address Book</span></span>

<span data-ttu-id="ec553-105">In generale, la Rubrica viene migrata insieme al resto della topologia.</span><span class="sxs-lookup"><span data-stu-id="ec553-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="ec553-106">Tuttavia, potrebbe essere necessario eseguire alcuni passaggi dopo la migrazione se sono stati personalizzati gli elementi seguenti nell'ambiente legacy:</span><span class="sxs-lookup"><span data-stu-id="ec553-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="ec553-107">Personalizzazione delle regole di normalizzazione della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="ec553-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="ec553-108">Impostazione del valore predefinito del parametro **UseNormalizationRules** su False.</span><span class="sxs-lookup"><span data-stu-id="ec553-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="ec553-109">**Regole di normalizzazione della Rubrica**</span><span class="sxs-lookup"><span data-stu-id="ec553-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="ec553-110">Se si personalizzano le regole di normalizzazione della Rubrica nell'ambiente legacy, è necessario eseguire la migrazione delle regole personalizzate nel pool pilota.</span><span class="sxs-lookup"><span data-stu-id="ec553-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="ec553-111">Se non è stata personalizzata alcuna regola di normalizzazione della Rubrica, non sarà necessario effettuare alcuna migrazione per il servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="ec553-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="ec553-112">Le regole di normalizzazione predefinite per Skype for Business Server 2019 sono le stesse delle regole predefinite per l'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="ec553-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="ec553-113">Eseguire la procedura descritta più avanti in questa sezione per eseguire la migrazione delle regole di normalizzazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ec553-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="ec553-p104">Se nell'organizzazione viene utilizzato il controllo delle chiamate remote e le regole di normalizzazione della Rubrica sono state personalizzate, prima di utilizzare il controllo delle chiamate remote è necessario eseguire la procedura descritta in questo argomento. L'esecuzione della procedura richiede l'appartenenza al gruppo RTCUniversalServerAdmins o diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="ec553-p104">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="ec553-116">**UseNormalizationRules impostato su False**</span><span class="sxs-lookup"><span data-stu-id="ec553-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="ec553-117">Se si imposta il valore di **UseNormalizationRules** su false in modo che gli utenti possano utilizzare i numeri di telefono come definito in servizi di dominio Active Directory senza che Skype for Business Server 2019 applichi regole di normalizzazione, è necessario impostare i parametri **UseNormalizationRules** e **IgnoreGenericRules** su true.</span><span class="sxs-lookup"><span data-stu-id="ec553-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="ec553-118">Eseguire la procedura descritta più avanti in questa sezione per impostare tali parametri su True.</span><span class="sxs-lookup"><span data-stu-id="ec553-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="ec553-119">Per eseguire la migrazione delle regole di normalizzazione personalizzate della Rubrica</span><span class="sxs-lookup"><span data-stu-id="ec553-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="ec553-120">Individuare il file Company_Phone_Number_Normalization_Rules.txt nella radice della cartella condivisa della Rubrica e copiarlo nella radice della cartella condivisa della Rubrica nel pool pilota di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ec553-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec553-121">Le regole di normalizzazione della Rubrica di esempio sono state installate nella directory dei file dei componenti Web del Servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="ec553-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="ec553-122">Il percorso è **$installedDriveLetter: \Programmi\microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span><span class="sxs-lookup"><span data-stu-id="ec553-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="ec553-123">Questo file può essere copiato e rinominato come **Company_Phone_Number_Normalization_Rules.txt** nella directory radice della cartella condivisa della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="ec553-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="ec553-124">Ad esempio, la rubrica condivisa in **$serverX**, il percorso sarà analogo al seguente: \*\* \\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="ec553-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="ec553-125">Utilizzare un editor di testo, ad esempio il Blocco Note, per aprire il file Company_Phone_Number_Normalization_Rules.txt.</span><span class="sxs-lookup"><span data-stu-id="ec553-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="ec553-126">Alcuni tipi di voci non funzioneranno correttamente in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ec553-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="ec553-127">Cercare all'interno del file i tipi di voci descritti in questo passaggio, modificarli secondo necessità e salvare le modifiche nella cartella condivisa della Rubrica all'interno del pool pilota.</span><span class="sxs-lookup"><span data-stu-id="ec553-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="ec553-p108">Le stringhe che includono spazi o caratteri di punteggiatura necessari provocano un errore nelle regole di normalizzazione poiché tali caratteri vengono rimossi dalla stringa utilizzata come input nelle regole di normalizzazione. Se sono presenti stringhe che includono spazi o caratteri di punteggiatura necessari, è necessario modificare le stringhe. La stringa seguente, ad esempio, genererà un errore nelle regola di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="ec553-p108">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:</span></span>

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="ec553-131">La stringa seguente non causerebbe alcun errore della regola di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="ec553-131">The following string would not cause the normalization rule to fail:</span></span>

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="ec553-132">Per impostare UseNormalizationRules e IgnoreGenericRules su True</span><span class="sxs-lookup"><span data-stu-id="ec553-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="ec553-133">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ec553-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ec553-134">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec553-134">Do one of the following:</span></span>

   - <span data-ttu-id="ec553-135">Se la distribuzione include solo Skype for Business Server 2019, eseguire il seguente cmdlet a livello globale per modificare i valori di **UseNormalizationRules** e **IgnoreGenericRules** su true:</span><span class="sxs-lookup"><span data-stu-id="ec553-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="ec553-136">Se la distribuzione include una combinazione di Skype for Business Server 2019 e un'installazione legacy, eseguire il cmdlet seguente e assegnarlo a ogni pool di Skype for Business Server 2019 nella topologia:</span><span class="sxs-lookup"><span data-stu-id="ec553-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="ec553-137">Attendere che la replica dell'archivio di gestione centrale venga eseguita in tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="ec553-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="ec553-138">Modificare il file delle regole di normalizzazione dei numeri di telefono, "Company_Phone_Number_Normalization_Rules.txt", per la distribuzione per cancellare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="ec553-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="ec553-139">Il file si trova nella condivisione file di ogni pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ec553-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ec553-140">Se il file non è presente, creare un file vuoto denominato "Company_Phone_Number_Normalization_Rules.txt".</span><span class="sxs-lookup"><span data-stu-id="ec553-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="ec553-141">Attendere alcuni minuti per tutti i pool Front end per leggere i nuovi file.</span><span class="sxs-lookup"><span data-stu-id="ec553-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="ec553-142">Eseguire il cmdlet seguente in ogni pool di Skype for Business Server 2019 nella distribuzione:</span><span class="sxs-lookup"><span data-stu-id="ec553-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```PowerShell
   Update-CsAddressBook
   ```


