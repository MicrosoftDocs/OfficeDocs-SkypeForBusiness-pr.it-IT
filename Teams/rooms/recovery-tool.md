---
title: Utilizza lo strumento di ripristino di Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Questo articolo descrive come usare lo strumento di ripristino per Microsoft Teams Rooms, che si userebbe per trasformare un sistema non aggiornato in uno stato supportato.
ms.openlocfilehash: c50b59ff4ed1ee997b990b0776ef4a7ee0ac29c2
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271161"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Utilizza lo strumento di ripristino di Microsoft Teams Rooms

Questo articolo descrive come usare lo strumento di ripristino per Microsoft Teams Rooms, che si userebbe per trasformare un sistema non aggiornato in uno stato supportato. Questo strumento deve essere applicato quando nella console Microsoft Teams Rooms viene visualizzato un errore "Configurazione di sistema non aggiornata" o prima di eseguire un [ripristino delle impostazioni di fabbrica](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore) del pulsante di scelta rapida.

## <a name="prerequisites"></a>Prerequisiti

Scarica l'ultimo [pacchetto di installazione Microsoft Teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) ed estrailo in un memory stick USB o una condivisione di rete accessibile a Microsoft Teams Rooms.

> [!NOTE]
> L'estrazione dei file dal file MSI può essere eseguita con molti mezzi. Qualsiasi meccanismo che estrae tutti i file e mantiene la struttura della directory è accettabile. Uno di questi modi consiste nell'usare il comando `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` in cui rappresenta il percorso completo del pacchetto di installazione della sala di Microsoft Teams e `PathToTarget` rappresenta il percorso completo della cartella in cui `PathToMsi` si vogliono estrarre i file.

## <a name="running-the-tool"></a>Esecuzione dello strumento

1) Accedere all'account di amministratore nel dispositivo Microsoft Teams Rooms e avviare un prompt dei comandi con privilegi elevati.
2) Verificare dal dispositivo Microsoft Teams Rooms che sia possibile accedere al `RecoveryTool.ps1` file, incluso nei file estratti dal pacchetto di installazione Microsoft Teams Rooms. Il kit è disponibile nella condivisione di rete o nell'unità USB utilizzata per la preparazione dei prerequisiti.
3) Esegui `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4) Per eseguire un ripristino delle impostazioni di fabbrica:
   1. Quando richiesto dallo script, selezionare l'opzione 2: **Reimposta**.
   2. Se BitLocker è attivato, segui le istruzioni fornite alla fine dell'output dello script per disabilitarlo.
   3. Eseguire il ripristino delle impostazioni predefinite.
      1. Apri l'app **Impostazioni** e seleziona **Aggiorna & Sicurezza**
      2. Passa alla scheda **Ripristino** .
      3. Sotto **Reimposta il PC** seleziona **Per iniziare**
      4. Seleziona **Rimuovi tutto**, quindi **Avanti** e **Reimposta**
        > [!WARNING]
        > Il dispositivo Microsoft Teams Rooms può diventare inutilizzabile se durante il processo di reimpostazione di Windows è selezionata l'opzione **Mantieni i miei file - Rimuove app e impostazioni, ma mantiene i file personali**. Non selezionare questa opzione.
      5. Il sistema verrà riavviato più volte. Al termine della reimpostazione, il sistema verrà visualizzato nella schermata "Configurazione guidata" di Windows.



## <a name="see-also"></a>Vedere anche

[Guida Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gestire Microsoft Teams Rooms](rooms-manage.md).
