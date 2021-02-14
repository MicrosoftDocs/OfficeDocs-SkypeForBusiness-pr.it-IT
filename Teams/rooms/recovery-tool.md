---
title: Usare lo strumento di ripristino Sale di Microsoft Teams
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
description: Questo articolo illustra come usare lo strumento di ripristino per Microsoft Teams Rooms, che consente di portare un sistema non aggiornato in uno stato supportato.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021724"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Usare lo strumento di ripristino Sale di Microsoft Teams

Questo articolo illustra come usare lo strumento di ripristino per Microsoft Teams Rooms, che consente di portare un sistema non aggiornato in uno stato supportato. Questo strumento deve essere applicato quando la console di Microsoft Teams Room mostra un errore di "configurazione del sistema non aggiornata" o prima di eseguire un ripristino del produttore con pulsante [push.](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>Prerequisiti

Scaricare l'ultimo pacchetto di installazione di [Microsoft Teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) ed estrarlo in un memory stick USB o in una condivisione di rete accessibile per il dispositivo Microsoft Teams Rooms.

> [!NOTE]
> L'estrazione dei file dal file MSI può essere eseguita in molti modi. È accettabile qualsiasi meccanismo che estrae tutti i file e mantiene la struttura della directory. Uno di questi modi è usare il comando dove rappresenta il percorso completo del pacchetto di installazione di Microsoft Teams Room e rappresenta il percorso completo della cartella in cui si desidera estrarre i `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` file.

## <a name="running-the-tool"></a>Esecuzione dello strumento

1) Accedere all'account amministratore nel dispositivo Microsoft Teams Rooms e avviare un prompt dei comandi con privilegi elevati.
2) Verificare dal dispositivo Sale di Microsoft Teams che sia possibile accedere a , che è incluso nei file estratti dal pacchetto di installazione `RecoveryTool.ps1 file` Sale di Microsoft Teams. Il kit è disponibile nella condivisione di rete o nell'unità USB usata per preparare i prerequisiti.
3) Eseguire `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .
4) Per eseguire un ripristino delle impostazioni factory:
   1. Quando richiesto dallo script, selezionare l'opzione 2: **Reimposta.**
   2. Se BitLocker è attivato, seguire le istruzioni fornite alla fine dell'output dello script per disabilitarlo.
   3. Eseguire il ripristino delle impostazioni factory.
      1. Aprire **l'app** Impostazioni e selezionare **Aggiorna & sicurezza**
      2. Passare alla **scheda** Ripristino.
      3. Sotto **Reimposta questo PC,** seleziona **Inizia**
      4. Seleziona **Rimuovi tutto,** quindi **Avanti** e **Reimposta**
        > [!WARNING]
        > Il dispositivo Sale di Microsoft Teams può diventare inutilizzabile se l'opzione Mantieni i file - Rimuove app e **impostazioni,** mantenendo però i file personali selezionata durante il processo di reimpostazione di Windows. Non selezionare questa opzione.
      5. Il sistema verrà riavviato più volte. Una volta completata la reimpostazione, il sistema si trova nella schermata "Configurazione guidata" di Windows.



## <a name="see-also"></a>Vedere anche

[Guida di Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gestire Microsoft Teams Rooms](rooms-manage.md).
