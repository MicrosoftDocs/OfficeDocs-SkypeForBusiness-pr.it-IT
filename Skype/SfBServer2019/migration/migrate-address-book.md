---
title: Migrare Rubrica
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: "In generale, la Rubrica viene migrata insieme al resto della topologia. Tuttavia, potrebbe essere necessario eseguire alcuni passaggi di post-migrazione se sono stati personalizzati gli elementi seguenti nell'ambiente legacy:"
ms.openlocfilehash: 4a3a85715b73c3a6b5996ba677b0647c87a8db1e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238701"
---
# <a name="migrate-address-book"></a>Migrare Rubrica

In generale, la Rubrica viene migrata insieme al resto della topologia. Tuttavia, potrebbe essere necessario eseguire alcuni passaggi di post-migrazione se sono stati personalizzati gli elementi seguenti nell'ambiente legacy: 

- Personalizzare le regole di normalizzazione della Rubrica.

- Ha modificato il valore predefinito per il parametro **UseNormalizationRules** su false. 


 **Regole di normalizzazione per la Rubrica**

Se le regole di normalizzazione della Rubrica sono personalizzate nell'ambiente legacy, è necessario eseguire la migrazione delle regole personalizzate al pool di piloti. Se non sono state personalizzate le regole di normalizzazione della Rubrica, non è necessario eseguire la migrazione per il servizio Rubrica. Le regole di normalizzazione predefinite per Skype for Business Server 2019 sono le stesse delle regole predefinite per l'installazione legacy. Seguire la procedura descritta più avanti in questa sezione per eseguire la migrazione delle regole di normalizzazione personalizzate.

> [!NOTE]
> Se l'organizzazione usa il controllo delle chiamate remote e le regole di normalizzazione della rubrica personalizzate, è necessario eseguire la procedura descritta in questo argomento prima di poter usare il controllo delle chiamate remote. La procedura richiede l'appartenenza al gruppo RTCUniversalServerAdmins o i diritti equivalenti. 

 **UseNormalizationRules impostato su false**

Se si imposta il valore di **UseNormalizationRules** su false in modo che gli utenti possano usare i numeri di telefono come definiti in servizi di dominio Active Directory senza che Skype for Business Server 2019 applichi regole di normalizzazione, è necessario impostare la ** Parametri UseNormalizationRules** e **IgnoreGenericRules** su true. Seguire la procedura più avanti in questa sezione per impostare questi parametri su true. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Per eseguire la migrazione delle regole di normalizzazione personalizzate della Rubrica

1. Individuare il file Company_Phone_Number_Normalization_Rules. txt nella radice della cartella condivisa della Rubrica e copiarlo nella radice della cartella condivisa Rubrica nel pool di piloti di Skype for Business Server 2019.

    > [!NOTE]
    > Le regole di normalizzazione della Rubrica di esempio sono state installate nella directory dei file del componente Web ABS. Il percorso è **$installedDriveLetter: \Programmi\microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt**. Questo file può essere copiato e rinominato come **Company_Phone_Number_Normalization_Rules. txt** nella directory radice della cartella condivisa della Rubrica. Ad esempio, la rubrica condivisa in **$serverX**, il percorso sarà simile a: ** \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Per aprire il file Company_Phone_Number_Normalization_Rules. txt, usare un editor di testo, ad esempio Blocco note.

3. Alcuni tipi di voci non funzionano correttamente in Skype for Business Server 2019. Esaminare il file per i tipi di voci descritti in questo passaggio, modificarli come necessario e salvare le modifiche apportate alla cartella condivisa Rubrica nel pool di piloti.

    Le stringhe che includono gli spazi vuoti o la punteggiatura necessari causano l'errore delle regole di normalizzazione perché questi caratteri vengono rimossi dalla stringa che viene immessa nelle regole di normalizzazione. Se sono presenti stringhe che includono spazi vuoti o segni di punteggiatura necessari, è necessario modificare le stringhe. Ad esempio, la stringa seguente causerà l'errore della regola di normalizzazione:

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    La stringa seguente non provocherebbe l'errore della regola di normalizzazione:

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Per impostare UseNormalizationRules e IgnoreGenericRules su true

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Esegui una delle operazioni seguenti:

   - Se la distribuzione include solo Skype for Business Server 2019, eseguire il cmdlet seguente a livello globale per modificare i valori di **UseNormalizationRules** e **IgnoreGenericRules** in true: 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Se la distribuzione include una combinazione di Skype for Business Server 2019 e di un'installazione legacy, eseguire il cmdlet seguente e assegnarla a ogni pool di Skype for Business Server 2019 nella topologia:

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Attendere che la replica di Central Management store si verifichi in tutti i pool.

4. Modificare il file delle regole di normalizzazione del telefono, "Company_Phone_Number_Normalization_Rules. txt", per la distribuzione per cancellare il contenuto. Il file si trova nella condivisione file di ogni pool di Skype for Business Server 2019. Se il file non è presente, creare un file vuoto denominato "Company_Phone_Number_Normalization_Rules. txt".

5. Attendere diversi minuti per tutti i pool di front-end per leggere i nuovi file.

6. Eseguire il cmdlet seguente in ogni pool di Skype for Business Server 2019 nella distribuzione:

   ```
   Update-CsAddressBook
   ```


