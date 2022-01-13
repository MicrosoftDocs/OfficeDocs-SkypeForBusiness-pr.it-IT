---
title: Aggiornare manualmente un Microsoft Teams Rooms dispositivo
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
description: Informazioni su come aggiornare manualmente il dispositivo Microsoft Teams Rooms a una versione specifica.
ms.openlocfilehash: 0b8ec08880d3f8c7ecce28293c92fb6ada901277
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2022
ms.locfileid: "62014996"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Aggiornare manualmente un Microsoft Teams Rooms dispositivo

L Microsoft Teams Rooms app viene distribuita tramite il Microsoft Store. Gli aggiornamenti dell'app vengono installati automaticamente dal Microsoft Store durante la manutenzione notturna. Questo è il metodo consigliato per ottenere gli aggiornamenti. Esistono tuttavia alcune situazioni in cui un dispositivo Teams Rooms non può ricevere gli aggiornamenti dal Microsoft Store. Ad esempio, i criteri di sicurezza potrebbero non consentire la connessione dei dispositivi a Internet o il download delle app dal Microsoft Store. In caso contrario, è possibile aggiornare un dispositivo prima di eseguire la configurazione, durante il quale il Microsoft Store non è disponibile.

Se non è possibile ottenere gli aggiornamenti dal Microsoft Store, è possibile usare uno script di PowerShell di aggiornamento dell'app offline per aggiornare manualmente i dispositivi Teams Rooms a una versione più recente dell'app Teams Rooms. Seguire i passaggi descritti in questo articolo per aggiornare manualmente i dispositivi Teams Rooms mobili.

> [!NOTE]
> Questo processo può aggiornare solo un dispositivo Teams Rooms con l'app Teams Rooms già installata. Non può essere usato per eseguire una nuova installazione. Non può inoltre essere usato per eseguire il downgrade dell'app a una versione precedente. Per eseguire una nuova installazione dell'app Teams Rooms, contattare il produttore del dispositivo per ottenere elementi multimediali specifici.

## <a name="step-1-download-the-offline-app-update-script"></a>Passaggio 1: Scaricare lo script di aggiornamento dell'app offline

Prima di tutto, scaricare l'ultima versione dello script di aggiornamento dell'app offline. Per scaricare lo script, fare clic su <https://go.microsoft.com/fwlink/?linkid=2151817> . Lo script verrà scaricato nella cartella di download predefinita del dispositivo.

I file scaricati potrebbero essere contrassegnati come bloccati da Windows. Se è necessario eseguire lo script senza alcuna interazione, è necessario sbloccarlo. Per sbloccare lo script, eseguire le operazioni seguenti:

1. Fare clic con il pulsante destro del mouse sul file in Esplora file
2. Fare clic **su Proprietà**
3. Selezionare **Sblocca**
4. Fare clic **su OK**

Per sbloccare lo script con PowerShell, vedere [Sblocca file](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).

Dopo aver scaricato lo script di aggiornamento dell'app offline, trasferire il file nel Teams Rooms dispositivo. È possibile trasferire un file nel dispositivo usando un'unità USB o accedendo al file da una condivisione file di rete mentre è attiva la modalità di amministrazione nel dispositivo. Assicurarsi di prendere nota della posizione in cui si salva il file nel dispositivo.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Passaggio 2: Eseguire lo script per aggiornare l Teams Rooms app

Lo script di aggiornamento dell'app offline deve essere eseguito da un prompt dei comandi con privilegi elevati mentre l'utente di Skype (l'utente con cui viene eseguita l'app) è ancora connesso. Per altre informazioni su come accedere a un account di amministratore per usare il prompt dei comandi con privilegi elevati mentre l'utente di Skype è ancora connesso, vedere Passare alla modalità di amministrazione e tornare alla modalità di amministrazione quando [l'app Microsoft Teams Rooms](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes)si arresta in modo anomalo.

Eseguire le operazioni seguenti per eseguire lo script da un prompt dei comandi con privilegi elevati:

1. Passare alla modalità di amministrazione
2. Fare clic sull'icona Start, **digitare Prompt dei comandi** e quindi selezionare Esegui come **amministratore**
3. Eseguire il comando seguente, dove `<path to script>` include il percorso completo dello script e il nome del file di script:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Ad esempio, se il file script si trova in `C:\Users\Admin\Downloads` e il nome del file script è , eseguire il comando `MTR-Update-4.5.6.7.ps1` seguente:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Consentire l'esecuzione dello script. Al termine, lo script riavvierà il Teams Rooms dispositivo.

È anche possibile eseguire lo script usando PowerShell remoto. Per altre informazioni sull'uso di PowerShell remoto con Teams Rooms, vedere Gestione [remota tramite PowerShell.](rooms-operations.md#remote-management-using-powershell)

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Passaggio 3: Verificare che l'app sia stata aggiornata correttamente

Se lo script viene eseguito correttamente, il dispositivo verrà riavviato nell Teams Rooms app.

Se lo script rileva un problema, indicherà qual è il problema nella riga di comando e ne registrerà l'output in un file. Seguire le istruzioni fornite nello script. Se è necessario contattare il supporto tecnico Microsoft, assicurarsi di includere il file di log insieme alla richiesta di supporto. Lo script fornirà il percorso del file di log.
