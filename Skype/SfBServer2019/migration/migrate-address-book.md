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
description: "In generale, la migrazione della Rubrica viene eseguita insieme al resto della topologia. Tuttavia, potrebbe essere necessario eseguire alcuni passaggi di post-migrazione se nell'ambiente legacy sono stati personalizzati i seguenti elementi:"
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752838"
---
# <a name="migrate-address-book"></a>Eseguire la migrazione della rubrica

In generale, la migrazione della Rubrica viene eseguita insieme al resto della topologia. Tuttavia, potrebbe essere necessario eseguire alcuni passaggi di post-migrazione se nell'ambiente legacy sono stati personalizzati i seguenti elementi: 

- Personalizzazione delle regole di normalizzazione della Rubrica.

- Impostazione del valore predefinito del parametro **UseNormalizationRules** su False. 


 **Regole di normalizzazione della Rubrica**

Se le regole di normalizzazione della Rubrica sono personalizzate nell'ambiente legacy, è necessario eseguire la migrazione delle regole personalizzate nel pool pilota. Se non è stata personalizzata alcuna regola di normalizzazione della Rubrica, non sarà necessario effettuare alcuna migrazione per il servizio Rubrica. Le regole di normalizzazione predefinite per Skype for Business Server 2019 sono le stesse predefinite per l'installazione legacy. Eseguire la procedura descritta più avanti in questa sezione per eseguire la migrazione delle regole di normalizzazione personalizzate.

> [!NOTE]
> Se nell'organizzazione viene utilizzato il controllo delle chiamate remote e le regole di normalizzazione della Rubrica sono state personalizzate, prima di utilizzare il controllo delle chiamate remote è necessario eseguire la procedura descritta in questo argomento. L'esecuzione della procedura richiede l'appartenenza al gruppo RTCUniversalServerAdmins o diritti equivalenti. 

 **UseNormalizationRules impostato su False**

Se si imposta il valore di **UseNormalizationRules** su False in modo che gli utenti possano utilizzare i numeri di telefono così come sono definiti in Servizi di dominio Active Directory senza che Skype for Business Server 2019 appliche le regole di normalizzazione, è necessario impostare i parametri **UseNormalizationRules** e **IgnoreGenericRules** su True. Eseguire la procedura descritta più avanti in questa sezione per impostare tali parametri su True. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Per eseguire la migrazione delle regole di normalizzazione personalizzate della Rubrica

1. Trovare il file Company_Phone_Number_Normalization_Rules.txt nella radice della cartella condivisa della Rubrica e copiarlo nella radice della cartella condivisa della Rubrica nel pool pilota di Skype for Business Server 2019.

    > [!NOTE]
    > Le regole di normalizzazione della Rubrica di esempio sono state installate nella directory dei file dei componenti Web del Servizio Rubrica. Il percorso è **$installedDriveLetter:\Programmi\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**. Questo file può essere copiato e rinominato **Company_Phone_Number_Normalization_Rules.txt** nella directory radice della cartella condivisa della rubrica. Ad esempio, la rubrica condivisa in **$serverX**, il percorso sarà simile a: **\\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles.** 

2. Utilizzare un editor di testo, ad esempio il Blocco Note, per aprire il file Company_Phone_Number_Normalization_Rules.txt.

3. Alcuni tipi di voci non funzionano correttamente in Skype for Business Server 2019. Cercare all'interno del file i tipi di voci descritti in questo passaggio, modificarli secondo necessità e salvare le modifiche nella cartella condivisa della Rubrica all'interno del pool pilota.

    Le stringhe che includono spazi o caratteri di punteggiatura necessari provocano un errore nelle regole di normalizzazione poiché tali caratteri vengono rimossi dalla stringa utilizzata come input nelle regole di normalizzazione. Se sono presenti stringhe che includono spazi o caratteri di punteggiatura necessari, è necessario modificare le stringhe. La stringa seguente, ad esempio, genererà un errore nelle regola di normalizzazione:

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    La stringa seguente non causerebbe alcun errore della regola di normalizzazione:

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Per impostare UseNormalizationRules e IgnoreGenericRules su True

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Microsoft Skype for Business Server 2019** e quindi **Skype for Business Server Management Shell.**

2. Eseguire una delle operazioni seguenti:

   - Se la distribuzione include solo Skype for Business Server 2019, eseguire il cmdlet seguente a livello globale per modificare i valori di **UseNormalizationRules** e **IgnoreGenericRules** su True: 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Se la distribuzione include una combinazione di Skype for Business Server 2019 e un'installazione legacy, eseguire il cmdlet seguente e assegnarlo a ogni pool di Skype for Business Server 2019 nella topologia:

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Attendere che la replica dell'archivio di gestione centrale si verifichi in tutti i pool.

4. Modificare il file delle regole di normalizzazione dei numeri di telefono, "Company_Phone_Number_Normalization_Rules.txt", per la distribuzione per cancellare il contenuto. Il file si trova nella condivisione file di ogni pool di Skype for Business Server 2019. Se il file non è presente, creare un file vuoto denominato "Company_Phone_Number_Normalization_Rules.txt".

5. Attendere alcuni minuti che tutti i pool Front End leggono i nuovi file.

6. Eseguire il cmdlet seguente in ogni pool di Skype for Business Server 2019 nella distribuzione:

   ```PowerShell
   Update-CsAddressBook
   ```


