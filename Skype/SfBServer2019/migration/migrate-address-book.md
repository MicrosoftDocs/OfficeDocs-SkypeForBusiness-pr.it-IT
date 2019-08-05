---
title: Migrare Rubrica
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: "In generale, la Rubrica viene migrata insieme al resto della topologia. Tuttavia, potrebbe essere necessario eseguire alcuni passaggi di post-migrazione se sono stati personalizzati gli elementi seguenti nell'ambiente legacy:"
ms.openlocfilehash: 4263ae5bff60859cc9606a3683a3a03b0d2d4c35
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195857"
---
# <a name="migrate-address-book"></a><span data-ttu-id="92915-104">Migrare Rubrica</span><span class="sxs-lookup"><span data-stu-id="92915-104">Migrate Address Book</span></span>

<span data-ttu-id="92915-105">In generale, la Rubrica viene migrata insieme al resto della topologia.</span><span class="sxs-lookup"><span data-stu-id="92915-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="92915-106">Tuttavia, potrebbe essere necessario eseguire alcuni passaggi di post-migrazione se sono stati personalizzati gli elementi seguenti nell'ambiente legacy:</span><span class="sxs-lookup"><span data-stu-id="92915-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="92915-107">Personalizzare le regole di normalizzazione della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="92915-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="92915-108">Ha modificato il valore predefinito per il parametro **UseNormalizationRules** su false.</span><span class="sxs-lookup"><span data-stu-id="92915-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="92915-109">**Regole di normalizzazione per la Rubrica**</span><span class="sxs-lookup"><span data-stu-id="92915-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="92915-110">Se le regole di normalizzazione della Rubrica sono personalizzate nell'ambiente legacy, è necessario eseguire la migrazione delle regole personalizzate al pool di piloti.</span><span class="sxs-lookup"><span data-stu-id="92915-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="92915-111">Se non sono state personalizzate le regole di normalizzazione della Rubrica, non è necessario eseguire la migrazione per il servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="92915-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="92915-112">Le regole di normalizzazione predefinite per Skype for Business Server 2019 sono le stesse delle regole predefinite per l'installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="92915-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="92915-113">Seguire la procedura descritta più avanti in questa sezione per eseguire la migrazione delle regole di normalizzazione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="92915-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="92915-114">Se l'organizzazione usa il controllo delle chiamate remote e le regole di normalizzazione della rubrica personalizzate, è necessario eseguire la procedura descritta in questo argomento prima di poter usare il controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="92915-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="92915-115">La procedura richiede l'appartenenza al gruppo RTCUniversalServerAdmins o i diritti equivalenti.</span><span class="sxs-lookup"><span data-stu-id="92915-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="92915-116">**UseNormalizationRules impostato su false**</span><span class="sxs-lookup"><span data-stu-id="92915-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="92915-117">Se si imposta il valore di **UseNormalizationRules** su false in modo che gli utenti possano usare i numeri di telefono come definiti in servizi di dominio Active Directory senza che Skype for Business Server 2019 applichi regole di normalizzazione, è necessario impostare la \*\* Parametri UseNormalizationRules\*\* e **IgnoreGenericRules** su true.</span><span class="sxs-lookup"><span data-stu-id="92915-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="92915-118">Seguire la procedura più avanti in questa sezione per impostare questi parametri su true.</span><span class="sxs-lookup"><span data-stu-id="92915-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="92915-119">Per eseguire la migrazione delle regole di normalizzazione personalizzate della Rubrica</span><span class="sxs-lookup"><span data-stu-id="92915-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="92915-120">Individuare il file Company_Phone_Number_Normalization_Rules. txt nella radice della cartella condivisa della Rubrica e copiarlo nella radice della cartella condivisa Rubrica nel pool di piloti di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="92915-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="92915-121">Le regole di normalizzazione della Rubrica di esempio sono state installate nella directory dei file del componente Web ABS.</span><span class="sxs-lookup"><span data-stu-id="92915-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="92915-122">Il percorso è **$installedDriveLetter: \Programmi\microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt**.</span><span class="sxs-lookup"><span data-stu-id="92915-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="92915-123">Questo file può essere copiato e rinominato come **Company_Phone_Number_Normalization_Rules. txt** nella directory radice della cartella condivisa della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="92915-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="92915-124">Ad esempio, la rubrica condivisa in **$serverX**, il percorso sarà simile a: \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*.</span><span class="sxs-lookup"><span data-stu-id="92915-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="92915-125">Per aprire il file Company_Phone_Number_Normalization_Rules. txt, usare un editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="92915-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="92915-126">Alcuni tipi di voci non funzionano correttamente in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="92915-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="92915-127">Esaminare il file per i tipi di voci descritti in questo passaggio, modificarli come necessario e salvare le modifiche apportate alla cartella condivisa Rubrica nel pool di piloti.</span><span class="sxs-lookup"><span data-stu-id="92915-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="92915-128">Le stringhe che includono gli spazi vuoti o la punteggiatura necessari causano l'errore delle regole di normalizzazione perché questi caratteri vengono rimossi dalla stringa che viene immessa nelle regole di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="92915-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="92915-129">Se sono presenti stringhe che includono spazi vuoti o segni di punteggiatura necessari, è necessario modificare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="92915-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="92915-130">Ad esempio, la stringa seguente causerà l'errore della regola di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="92915-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="92915-131">La stringa seguente non provocherebbe l'errore della regola di normalizzazione:</span><span class="sxs-lookup"><span data-stu-id="92915-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="92915-132">Per impostare UseNormalizationRules e IgnoreGenericRules su true</span><span class="sxs-lookup"><span data-stu-id="92915-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="92915-133">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="92915-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="92915-134">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="92915-134">Do one of the following:</span></span>

   - <span data-ttu-id="92915-135">Se la distribuzione include solo Skype for Business Server 2019, eseguire il cmdlet seguente a livello globale per modificare i valori di **UseNormalizationRules** e **IgnoreGenericRules** in true:</span><span class="sxs-lookup"><span data-stu-id="92915-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="92915-136">Se la distribuzione include una combinazione di Skype for Business Server 2019 e di un'installazione legacy, eseguire il cmdlet seguente e assegnarla a ogni pool di Skype for Business Server 2019 nella topologia:</span><span class="sxs-lookup"><span data-stu-id="92915-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="92915-137">Attendere che la replica di Central Management store si verifichi in tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="92915-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="92915-138">Modificare il file delle regole di normalizzazione del telefono, "Company_Phone_Number_Normalization_Rules. txt", per la distribuzione per cancellare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="92915-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="92915-139">Il file si trova nella condivisione file di ogni pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="92915-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="92915-140">Se il file non è presente, creare un file vuoto denominato "Company_Phone_Number_Normalization_Rules. txt".</span><span class="sxs-lookup"><span data-stu-id="92915-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="92915-141">Attendere diversi minuti per tutti i pool di front-end per leggere i nuovi file.</span><span class="sxs-lookup"><span data-stu-id="92915-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="92915-142">Eseguire il cmdlet seguente in ogni pool di Skype for Business Server 2019 nella distribuzione:</span><span class="sxs-lookup"><span data-stu-id="92915-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


