---
title: Aggiornare manualmente un dispositivo Microsoft teams rooms
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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Informazioni su come aggiornare manualmente il dispositivo Microsoft teams rooms in una versione specifica.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731394"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Aggiornare manualmente un dispositivo Microsoft teams rooms

L'app Microsoft teams Rooms viene distribuita tramite Microsoft Store. Gli aggiornamenti dell'app vengono installati automaticamente da Microsoft Store durante la manutenzione notturna; Questo è il metodo consigliato per ottenere gli aggiornamenti. Esistono tuttavia alcune situazioni in cui un dispositivo di teams Rooms non può ricevere aggiornamenti da Microsoft Store. Ad esempio, i criteri di sicurezza potrebbero non consentire ai dispositivi di connettersi a Internet o potrebbero non consentire il download delle app da Microsoft Store. In alternativa, potresti voler aggiornare un dispositivo prima di eseguire la configurazione, durante il quale Microsoft Store non è disponibile.

Se non si riesce ad ottenere gli aggiornamenti da Microsoft Store, è possibile usare uno script di PowerShell per l'aggiornamento delle app offline per aggiornare manualmente i dispositivi delle sale di Teams a una versione più recente dell'app teams rooms. Seguire i passaggi di questo articolo per aggiornare manualmente i dispositivi di teams rooms.

> [!NOTE]
> Questo processo può aggiornare solo un dispositivo di teams Rooms con l'app teams rooms già installata. Non può essere usata per eseguire una nuova installazione. Inoltre, non può essere usato per declassare l'app a una versione precedente. Per eseguire una nuova installazione dell'app teams rooms, contattare il produttore del dispositivo per elementi multimediali specifici o vedere [preparare il supporto di installazione](console.md#prepare-the-installation-media).

## <a name="step-1-download-the-offline-app-update-script"></a>Passaggio 1: scaricare lo script di aggiornamento dell'app offline

Prima di tutto, Scarica la versione più recente dello script di aggiornamento dell'app offline. Per scaricare lo script, fare clic su <https://go.microsoft.com/fwlink/?linkid=2151817> . Lo script verrà scaricato nella cartella download predefinita del dispositivo.

I file scaricati possono essere contrassegnati come bloccati da Windows. Se è necessario eseguire lo script senza alcuna interazione, è necessario sbloccare lo script. Per sbloccare lo script, eseguire le operazioni seguenti:

1. Fare clic con il pulsante destro del mouse sul file in Esplora file
2. Fare clic su **Proprietà**
3. Selezionare **Sblocca**
4. Fare clic su **OK**

Per sbloccare lo script usando PowerShell, vedere [sbloccare file](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Dopo il download dello script di aggiornamento dell'app offline, trasferire il file nel dispositivo teams rooms. È possibile trasferire un file nel dispositivo usando un'unità USB o accedendo al file da una condivisione file di rete mentre si è in modalità amministratore nel dispositivo. Assicurarsi di notare dove salvare il file nel dispositivo.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Passaggio 2: eseguire lo script per aggiornare l'app teams rooms

Lo script di aggiornamento dell'app offline deve essere eseguito da un prompt dei comandi con privilegi elevati mentre l'utente Skype (l'utente in cui viene eseguita l'app) è ancora connesso. Per altre informazioni su come accedere a un account di amministratore per usare il prompt dei comandi con privilegi elevati mentre l'utente Skype è ancora connesso, vedere [passare alla modalità amministratore e viceversa quando l'app Microsoft teams Rooms è in esecuzione](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).

Per eseguire lo script da un prompt dei comandi con privilegi elevati, procedere come segue:

1. Passare alla modalità amministratore
2. Fare clic sull'icona Start, digitare **prompt dei comandi** e quindi scegliere **Esegui come amministratore**
3. Eseguire il comando seguente `<path to script>` , dove include il percorso completo dello script e il nome del file di script:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Ad esempio, se il file di script si trova `C:\Users\Admin\Downloads` e il nome del file di script è `MTR-Update-4.5.6.7.ps1` , eseguire il comando seguente:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Consentire l'esecuzione dello script. Al termine, lo script riavvia il dispositivo teams rooms.

Puoi anche eseguire lo script usando Remote PowerShell. Per altre informazioni sull'uso di PowerShell remoto con i dispositivi teams rooms, vedere [gestione remota tramite PowerShell](rooms-operations.md#remote-management-using-powershell).

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Passaggio 3: verificare che l'app sia stata aggiornata correttamente

Se lo script viene eseguito correttamente, il dispositivo verrà riavviato nell'app teams rooms.

Se lo script incontra un problema, indicherà qual è il problema nella riga di comando e ne registra l'output in un file. Seguire le istruzioni fornite dallo script. Se è necessario contattare il supporto tecnico Microsoft, assicurarsi di includere il file di log insieme alla richiesta di supporto. Lo script consentirà di specificare il percorso del file di log.
