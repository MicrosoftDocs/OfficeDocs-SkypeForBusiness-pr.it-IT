---
title: Utilizza lo strumento di ripristino di Microsoft Teams Rooms
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Questo articolo illustra come usare lo strumento di ripristino per Microsoft Teams Rooms, che è possibile usare per portare un sistema non aggiornato in uno stato supportato.
ms.openlocfilehash: 4abd13abcfd20385c6f26e029dae1435883f0f8e
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503693"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Utilizza lo strumento di ripristino di Microsoft Teams Rooms

Questo articolo illustra come usare lo strumento di ripristino per Microsoft Teams Rooms, che è possibile usare per portare un sistema non aggiornato in uno stato supportato. Questo strumento deve essere applicato quando nella console di Microsoft Teams Rooms viene visualizzato un errore "Configurazione di sistema non aggiornata" o prima di eseguire un ripristino di fabbrica con un pulsante [di comando](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore).

## <a name="prerequisites"></a>Prerequisiti

Scaricare il pacchetto di [Microsoft Teams Rooms di installazione](https://go.microsoft.com/fwlink/?linkid=851168) più recente ed estrarlo in una memory stick USB o in una condivisione di rete accessibile Microsoft Teams Rooms.

> [!NOTE]
> L'estrazione dei file dal file MSI può essere eseguita in molti modi. Qualsiasi meccanismo che estrae tutti i file e mantiene la struttura della directory è accettabile. Uno di questi `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` modi è usare il comando dove rappresenta il percorso completo del pacchetto di installazione di Microsoft Teams Room `PathToTarget` e rappresenta il percorso completo della cartella in cui si desidera estrarre i file.

## <a name="running-the-tool"></a>Esecuzione dello strumento

1) Accedere all'account di amministratore nel dispositivo Microsoft Teams Rooms e avviare un prompt dei comandi con privilegi elevati.
2) Verificare dal dispositivo Microsoft Teams Rooms `RecoveryTool.ps1` che sia possibile accedere al file, incluso nei file estratti dal pacchetto Microsoft Teams Rooms di installazione. Il kit è disponibile nella condivisione di rete o nell'unità USB usata per la preparazione dei prerequisiti.
3) Eseguire `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4) Per eseguire un ripristino in fabbrica:
   1. Quando richiesto dallo script, selezionare l'opzione 2: **Reimposta**.
   2. Se BitLocker è attivato, seguire le istruzioni fornite alla fine dell'output dello script per disabilitarlo.
   3. Eseguire il ripristino in fabbrica.
      1. Aprire l **Impostazioni** app e selezionare **Aggiorna & sicurezza**
      2. Passare alla **scheda** Ripristino.
      3. Sotto **Reimposta questo PC**, seleziona **Inizia**
      4. Seleziona **Rimuovi tutto**, quindi **Avanti e** **Reimposta**
        > [!WARNING]
        > Il Microsoft Teams Rooms può diventare inutilizzabile se l'opzione Mantieni i file **personali -** Rimuove app e impostazioni, ma mantiene i file personali è selezionata durante il processo di Windows reimpostazione. Non selezionare questa opzione.
      5. Il sistema verrà riavviato più volte. Una volta completato il ripristino, il sistema si trova nella schermata Windows "Esperienza fuori campo" (OOBE).



## <a name="see-also"></a>Vedere anche

[Guida Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gestire Microsoft Teams Rooms](rooms-manage.md).
