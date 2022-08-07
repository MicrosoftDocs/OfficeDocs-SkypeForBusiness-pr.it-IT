---
title: Aggiornare manualmente un dispositivo Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Informazioni su come aggiornare manualmente il dispositivo Microsoft Teams Rooms a una versione specifica.
ms.openlocfilehash: c3128f5b909901da0eb5578f1586aaad785b49a6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267641"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Aggiornare manualmente un dispositivo Microsoft Teams Rooms

L'app Microsoft Teams Rooms viene distribuita tramite Microsoft Store. Aggiornamenti all'app vengono installate automaticamente da Microsoft Store durante la manutenzione notturna; questo è il metodo consigliato per ottenere gli aggiornamenti. Esistono tuttavia alcune situazioni in cui un dispositivo Teams Rooms non può ricevere aggiornamenti da Microsoft Store. Ad esempio, i criteri di sicurezza potrebbero non consentire ai dispositivi di connettersi a Internet o potrebbero non consentire il download di app da Microsoft Store. In alternativa, potresti voler aggiornare un dispositivo prima di eseguire la configurazione, durante la quale Microsoft Store non è disponibile.

Se non riesci a ottenere aggiornamenti da Microsoft Store, puoi usare un'app offline per aggiornare lo script di PowerShell per aggiornare manualmente i dispositivi Teams Rooms a una versione più recente dell'app Teams Rooms. Seguire i passaggi descritti in questo articolo per aggiornare manualmente i dispositivi Teams Rooms.

> [!NOTE]
> Questo processo può aggiornare solo un dispositivo Teams Rooms con l'app Teams Rooms già installata. Non può essere usato per eseguire una nuova installazione. Inoltre, non può essere usato per eseguire il downgrade dell'app a una versione precedente. Per eseguire una nuova installazione dell'app Teams Rooms, contatta il produttore del dispositivo per ottenere supporti specifici.

## <a name="step-1-download-the-offline-app-update-script"></a>Passaggio 1: Scaricare lo script di aggiornamento dell'app offline

Prima di tutto, scarica l'ultima versione dello script di aggiornamento dell'app offline. Per scaricare lo script, fare clic su <https://go.microsoft.com/fwlink/?linkid=2151817>. Lo script verrà scaricato nella cartella di download predefinita del dispositivo.

I file scaricati potrebbero essere contrassegnati come bloccati da Windows. Se è necessario eseguire lo script senza alcuna interazione, è necessario sbloccarlo. Per sbloccare lo script, eseguire le operazioni seguenti:

1. Fare clic con il pulsante destro del mouse sul file in Esplora file
2. Fare clic su **Proprietà**
3. Seleziona **Sblocca**
4. Fare clic su **OK**

Per sbloccare lo script con PowerShell, vedere [Sbloccare un file](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Dopo aver scaricato lo script di aggiornamento dell'app offline, trasferire il file nel dispositivo Teams Rooms. Puoi trasferire un file nel dispositivo tramite un'unità USB o accedendo al file da una condivisione file di rete in modalità Amministrazione sul dispositivo. Assicurati di prendere nota del percorso in cui salvare il file nel dispositivo.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Passaggio 2: Eseguire lo script per aggiornare l'app Teams Rooms

Lo script di aggiornamento dell'app offline deve essere eseguito da un prompt dei comandi con privilegi elevati mentre l'utente Skype (l'utente con cui viene eseguita l'app) è ancora connesso. Per ulteriori informazioni su come accedere a un account amministratore per usare il prompt dei comandi con privilegi elevati mentre l'utente Skype è ancora connesso, vedi [Passaggio alla modalità Amministrazione e ritorno in caso di arresto anomalo dell'app Microsoft Teams Rooms](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes).

Eseguire le operazioni seguenti per eseguire lo script da un prompt dei comandi con privilegi elevati:

1. Passare alla modalità Amministrazione
2. Fare clic sull'icona Start, digitare **Prompt dei comandi** e quindi selezionare **Esegui come amministratore**
3. Eseguire il comando seguente, che `<path to script>` include il percorso completo dello script e il nome del file di script:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Ad esempio, se il file script si trova in `C:\Users\Admin\Downloads`e il nome del file script è `MTR-Update-4.5.6.7.ps1`, eseguire il comando seguente:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Consentire l'esecuzione dello script. Al termine, lo script riavvierà il dispositivo Teams Rooms.

È anche possibile eseguire lo script usando Una remota PowerShell. Per altre informazioni sull'uso di PowerShell remoto con Teams Rooms dispositivi, vedere [Gestione remota con PowerShell](rooms-operations.md#remote-management-using-powershell).

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Passaggio 3: Verificare che l'app sia stata aggiornata correttamente

Se lo script viene eseguito correttamente, il dispositivo verrà riavviato nell'app Teams Rooms.

Se lo script rileva un problema, indicherà il problema nella riga di comando e ne registrerà l'output in un file. Seguire le istruzioni fornite dallo script. Se è necessario contattare supporto tecnico Microsoft, assicurarsi di includere il file di log insieme alla richiesta di supporto. Lo script fornirà il percorso del file di log.
