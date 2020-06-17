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
# <a name="migrate-address-book"></a>Eseguire la migrazione della rubrica

In generale, la Rubrica viene migrata insieme al resto della topologia. Tuttavia, potrebbe essere necessario eseguire alcuni passaggi dopo la migrazione se sono stati personalizzati gli elementi seguenti nell'ambiente legacy: 

- Personalizzazione delle regole di normalizzazione della Rubrica.

- Impostazione del valore predefinito del parametro **UseNormalizationRules** su False. 


 **Regole di normalizzazione della Rubrica**

Se si personalizzano le regole di normalizzazione della Rubrica nell'ambiente legacy, è necessario eseguire la migrazione delle regole personalizzate nel pool pilota. Se non è stata personalizzata alcuna regola di normalizzazione della Rubrica, non sarà necessario effettuare alcuna migrazione per il servizio Rubrica. Le regole di normalizzazione predefinite per Skype for Business Server 2019 sono le stesse delle regole predefinite per l'installazione legacy. Eseguire la procedura descritta più avanti in questa sezione per eseguire la migrazione delle regole di normalizzazione personalizzate.

> [!NOTE]
> If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights. 

 **UseNormalizationRules impostato su False**

Se si imposta il valore di **UseNormalizationRules** su false in modo che gli utenti possano utilizzare i numeri di telefono come definito in servizi di dominio Active Directory senza che Skype for Business Server 2019 applichi regole di normalizzazione, è necessario impostare i parametri **UseNormalizationRules** e **IgnoreGenericRules** su true. Eseguire la procedura descritta più avanti in questa sezione per impostare tali parametri su True. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Per eseguire la migrazione delle regole di normalizzazione personalizzate della Rubrica

1. Individuare il file Company_Phone_Number_Normalization_Rules.txt nella radice della cartella condivisa della Rubrica e copiarlo nella radice della cartella condivisa della Rubrica nel pool pilota di Skype for Business Server 2019.

    > [!NOTE]
    > Le regole di normalizzazione della Rubrica di esempio sono state installate nella directory dei file dei componenti Web del Servizio Rubrica. Il percorso è **$installedDriveLetter: \Programmi\microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**. Questo file può essere copiato e rinominato come **Company_Phone_Number_Normalization_Rules.txt** nella directory radice della cartella condivisa della Rubrica. Ad esempio, la rubrica condivisa in **$serverX**, il percorso sarà analogo al seguente: ** \\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Utilizzare un editor di testo, ad esempio il Blocco Note, per aprire il file Company_Phone_Number_Normalization_Rules.txt.

3. Alcuni tipi di voci non funzioneranno correttamente in Skype for Business Server 2019. Cercare all'interno del file i tipi di voci descritti in questo passaggio, modificarli secondo necessità e salvare le modifiche nella cartella condivisa della Rubrica all'interno del pool pilota.

    Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    La stringa seguente non causerebbe alcun errore della regola di normalizzazione:

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Per impostare UseNormalizationRules e IgnoreGenericRules su True

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Eseguire una delle operazioni seguenti:

   - Se la distribuzione include solo Skype for Business Server 2019, eseguire il seguente cmdlet a livello globale per modificare i valori di **UseNormalizationRules** e **IgnoreGenericRules** su true: 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Se la distribuzione include una combinazione di Skype for Business Server 2019 e un'installazione legacy, eseguire il cmdlet seguente e assegnarlo a ogni pool di Skype for Business Server 2019 nella topologia:

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Attendere che la replica dell'archivio di gestione centrale venga eseguita in tutti i pool.

4. Modificare il file delle regole di normalizzazione dei numeri di telefono, "Company_Phone_Number_Normalization_Rules.txt", per la distribuzione per cancellare il contenuto. Il file si trova nella condivisione file di ogni pool di Skype for Business Server 2019. Se il file non è presente, creare un file vuoto denominato "Company_Phone_Number_Normalization_Rules.txt".

5. Attendere alcuni minuti per tutti i pool Front end per leggere i nuovi file.

6. Eseguire il cmdlet seguente in ogni pool di Skype for Business Server 2019 nella distribuzione:

   ```PowerShell
   Update-CsAddressBook
   ```


