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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Informazioni su come aggiornare manualmente il dispositivo Sale di Microsoft Teams a una versione specifica.
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731394"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>Aggiornare manualmente un dispositivo Microsoft Teams Rooms

L'app Sale di Microsoft Teams viene distribuita tramite Microsoft Store. Gli aggiornamenti dell'app vengono installati automaticamente da Microsoft Store durante la manutenzione notturna; questo è il metodo consigliato per ottenere gli aggiornamenti. In alcune situazioni, tuttavia, un dispositivo Sale di Teams non può ricevere gli aggiornamenti da Microsoft Store. Ad esempio, i criteri di sicurezza potrebbero non consentire la connessione a Internet dei dispositivi o il download di app da Microsoft Store. Oppure, potresti voler aggiornare un dispositivo prima di eseguire la configurazione, durante il quale Microsoft Store non è disponibile.

Se non è possibile ottenere gli aggiornamenti da Microsoft Store, è possibile usare uno script di PowerShell per l'aggiornamento offline delle app per aggiornare manualmente i dispositivi della chat room di Teams a una versione più recente dell'app Sale di Teams. Seguire i passaggi di questo articolo per aggiornare manualmente i dispositivi di Teams Rooms.

> [!NOTE]
> Questo processo può aggiornare solo un dispositivo Teams Rooms con l'app Sale di Teams già installata. Non può essere usato per eseguire una nuova installazione. Non può inoltre essere usato per eseguire il downgrade dell'app a una versione precedente. Per eseguire una nuova installazione dell'app Sale di Teams, contattare il produttore del dispositivo per ottenere elementi multimediali specifici oppure vedere Preparare il [supporto di installazione.](console.md#prepare-the-installation-media)

## <a name="step-1-download-the-offline-app-update-script"></a>Passaggio 1: Scaricare lo script di aggiornamento delle app offline

Prima di tutto, scaricare l'ultima versione dello script di aggiornamento dell'app offline. Per scaricare lo script, fare clic su <https://go.microsoft.com/fwlink/?linkid=2151817> . Lo script verrà scaricato nella cartella download predefinita del dispositivo.

I file scaricati potrebbero essere contrassegnati come bloccati da Windows. Se è necessario eseguire lo script senza alcuna interazione, è necessario sbloccare lo script. Per sbloccare lo script, eseguire le operazioni seguenti:

1. Fare clic con il pulsante destro del mouse sul file in Esplora file
2. Fare clic **su Proprietà**
3. Selezionare **Sblocca**
4. Fare clic **su OK**

Per sbloccare lo script con PowerShell, vedere [Sblocca file.](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)

Dopo aver scaricato lo script di aggiornamento dell'app offline, trasferire il file nel dispositivo Teams Room. Puoi trasferire un file nel dispositivo usando un'unità USB o accedendo al file da una condivisione file di rete mentre sei in modalità amministratore nel dispositivo. Prendere nota della posizione in cui si salva il file nel dispositivo.

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>Passaggio 2: Eseguire lo script per aggiornare l'app Sale di Teams

Lo script di aggiornamento dell'app offline deve essere eseguito da un prompt dei comandi con privilegi elevati mentre l'utente Skype (l'utente con cui viene eseguita l'app) ha ancora eseguito l'accesso. Per ulteriori informazioni su come accedere a un account amministratore per usare il prompt dei comandi con privilegi elevati mentre l'utente di Skype è ancora connesso, consulta Passare alla modalità amministratore e tornare quando [l'app Sale](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)di Microsoft Teams è in esecuzione.

Eseguire la procedura seguente per eseguire lo script da un prompt dei comandi con privilegi elevati:

1. Passare alla modalità amministratore
2. Fare clic sull'icona Start, **digitare Prompt dei** comandi e quindi selezionare Esegui come **amministratore**
3. Eseguire il comando `<path to script>` seguente, che include il percorso completo dello script e il nome del file script:

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

Ad esempio, se il file script si trova in `C:\Users\Admin\Downloads` e il nome del file script è , eseguire il comando `MTR-Update-4.5.6.7.ps1` seguente:

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

Consentire l'esecuzione dello script. Al termine, lo script riavvierà il dispositivo Teams Rooms.

È anche possibile eseguire lo script usando una sessione remota di PowerShell. Per altre informazioni sull'uso di Una sessione remota di PowerShell con i dispositivi Room di Teams, vedere [Gestione remota con PowerShell.](rooms-operations.md#remote-management-using-powershell)

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>Passaggio 3: Verificare che l'app sia stata aggiornata correttamente

Se lo script viene eseguito correttamente, il dispositivo verrà riavviato nell'app Teams Rooms.

Se lo script rileva un problema, indicherà quale è il problema nella riga di comando e registrerà l'output in un file. Seguire le istruzioni fornite nello script. Se è necessario contattare il supporto tecnico Microsoft, assicurarsi di includere il file di log insieme alla richiesta di supporto. Lo script fornirà il percorso del file di log.
