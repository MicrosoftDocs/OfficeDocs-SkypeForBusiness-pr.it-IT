---
title: Usare lo strumento di ripristino di Microsoft teams rooms
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 755a85c9013d160197c8a8d57f74ef18b207e052
ms.sourcegitcommit: 3d393ceded4d64963411cfdc96931952d480ded5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225280"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usare lo strumento di ripristino di Microsoft teams rooms

Questo articolo illustra come usare lo strumento di ripristino per le sale di Microsoft teams, che userai per creare un sistema fuori data in uno stato supportato. Questo strumento deve essere applicato quando la console Microsoft teams Rooms Mostra un errore di "configurazione di sistema non aggiornata" oppure prima di eseguire un ripristino tramite pulsante Reimposta [Factory](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).

## <a name="prerequisites"></a>Prerequisiti

Scaricare il pacchetto di installazione più recente di [Microsoft teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) ed estrarlo in una Memory Stick USB o in una condivisione di rete accessibile al dispositivo Microsoft teams rooms.

> [!NOTE]
> L'estrazione dei file dall'MSI può essere eseguita con molti mezzi. Qualsiasi meccanismo che estrae tutti i file e mantiene la struttura della directory è accettabile. Uno di questi modi consiste nell'usare il `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` comando `PathToMsi` dove rappresenta il percorso completo del pacchetto di installazione della sala Microsoft teams e `PathToTarget` rappresenta il percorso completo della cartella a cui si vogliono estrarre i file.

## <a name="running-the-tool"></a>Eseguire lo strumento

1) Accedere all'account di amministratore nel dispositivo Microsoft teams Rooms e avviare un prompt dei comandi con privilegi elevati.
2) Verificare dal dispositivo Microsoft teams Rooms che si è in grado di accedere `RecoveryTool.ps1 file`a, incluso nei file estratti dal pacchetto di installazione di Microsoft teams rooms. Il kit può essere trovato nella condivisione di rete o nell'unità USB usata per la preparazione dei prerequisiti.
3) Esegui `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4) Se si esegue un ripristino di fabbrica:
   - Quando richiesto dallo script, selezionare l'opzione 2: **Reimposta**.
   - Se BitLocker è attivato, seguire le istruzioni fornite alla fine dell'output dello script per disabilitarlo.
   - Eseguire il ripristino di fabbrica.
      - Aprire l'app **Impostazioni** e selezionare **Aggiorna & sicurezza**
      - Passare alla scheda **ripristino** .
      - Sotto **Reimposta questo PC**selezionare **inizia**
      - Selezionare **Rimuovi tutto**, quindi **Avanti** e **Reimposta**
      - Il sistema verrà riavviato più volte. Al termine del ripristino, il sistema sarà nella schermata della configurazione guidata di Windows.
5) Se si sta riparando un sistema "fuori data":
    - Quando viene richiesto dallo script, selezionare l'opzione 1: **Ripristina**.
    - Al termine, riavviare il dispositivo Microsoft teams rooms. Verrà riavviato automaticamente e verrà recuperato completamente la seconda volta.

> [!NOTE]
> Si è verificato un problema noto in cui le sale di Microsoft teams possono diventare inutilizzabili se la funzione **Mantieni file-rimuove le app e le impostazioni, ma mantiene l'opzione file personali** selezionata durante il processo di ripristino di Windows. Non *usare questa* opzione.

## <a name="see-also"></a>Vedere anche

[Guida di Microsoft teams rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gestire le sale di Microsoft Teams](rooms-manage.md)
