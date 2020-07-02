---
title: Usare lo strumento di ripristino di Microsoft teams rooms
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Questo articolo illustra come usare lo strumento di ripristino per le sale di Microsoft teams, che userai per creare un sistema fuori data in uno stato supportato.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021724"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usare lo strumento di ripristino di Microsoft teams rooms

Questo articolo illustra come usare lo strumento di ripristino per le sale di Microsoft teams, che userai per creare un sistema fuori data in uno stato supportato. Questo strumento deve essere applicato quando la console Microsoft teams Rooms Mostra un errore di "configurazione di sistema non aggiornata" oppure prima di eseguire un ripristino tramite pulsante Reimposta [Factory](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).

## <a name="prerequisites"></a>Prerequisiti

Scaricare il pacchetto di installazione più recente di [Microsoft teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) ed estrarlo in una Memory Stick USB o in una condivisione di rete accessibile al dispositivo Microsoft teams rooms.

> [!NOTE]
> L'estrazione dei file dall'MSI può essere eseguita con molti mezzi. Qualsiasi meccanismo che estrae tutti i file e mantiene la struttura della directory è accettabile. Uno di questi modi consiste nell'usare il comando `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` dove `PathToMsi` rappresenta il percorso completo del pacchetto di installazione della sala Microsoft teams e `PathToTarget` rappresenta il percorso completo della cartella a cui si vogliono estrarre i file.

## <a name="running-the-tool"></a>Eseguire lo strumento

1) Accedere all'account di amministratore nel dispositivo Microsoft teams Rooms e avviare un prompt dei comandi con privilegi elevati.
2) Verificare dal dispositivo Microsoft teams Rooms che si è in grado di accedere a `RecoveryTool.ps1 file` , incluso nei file estratti dal pacchetto di installazione di Microsoft teams rooms. Il kit può essere trovato nella condivisione di rete o nell'unità USB usata per la preparazione dei prerequisiti.
3) Esegui `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .
4) Per eseguire un ripristino di fabbrica:
   1. Quando richiesto dallo script, selezionare l'opzione 2: **Reimposta**.
   2. Se BitLocker è attivato, seguire le istruzioni fornite alla fine dell'output dello script per disabilitarlo.
   3. Eseguire il ripristino di fabbrica.
      1. Aprire l'app **Impostazioni** e selezionare **Aggiorna & sicurezza**
      2. Passare alla scheda **ripristino** .
      3. Sotto **Reimposta questo PC**selezionare **inizia**
      4. Selezionare **Rimuovi tutto**, quindi **Avanti** e **Reimposta**
        > [!WARNING]
        > Il dispositivo Microsoft teams Rooms può diventare inutilizzabile se **Keep My Files-rimuove le app e le impostazioni, ma mantiene** selezionata l'opzione file personali durante il processo di ripristino di Windows. Non selezionare questa opzione.
      5. Il sistema verrà riavviato più volte. Al termine del ripristino, il sistema sarà impostato sullo schermo Windows "fuori scatola" (OOBE).



## <a name="see-also"></a>Vedere anche

[Guida di Microsoft teams rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gestire Microsoft Teams Rooms](rooms-manage.md).
