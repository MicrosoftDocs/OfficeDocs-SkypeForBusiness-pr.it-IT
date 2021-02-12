---
title: Aggiornare i dispositivi di Microsoft Teams in remoto
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Aggiornare i telefoni e le barre di collaborazione di Microsoft Teams in remoto usando l'interfaccia di amministrazione di Teams
ms.openlocfilehash: e57ca3f357deeb005f845d37a17c4b20db5d2035
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962887"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Aggiornare i dispositivi di Microsoft Teams in remoto

Utilizzando l'interfaccia di amministrazione di Microsoft Teams, è possibile aggiornare i dispositivi di Teams, come telefoni e barre di collaborazione, in remoto, e scegliere il comportamento di aggiornamento automatico del firmware del dispositivo. È possibile aggiornare quanto segue nei dispositivi usando l'interfaccia di amministrazione di Teams:

- Agente di amministrazione dell'app Teams e dei team
- App portale aziendale
- App agente OEM
- Firmware del dispositivo

Gli aggiornamenti del firmware del dispositivo possono essere applicati automaticamente o pianificati per una data e un'ora future. Gli altri aggiornamenti disponibili per i dispositivi non vengono applicati automaticamente, ma possono essere applicati manualmente o pianificati in futuro.

> [!NOTE]
> Anche se è possibile programmare gli aggiornamenti del firmware del dispositivo, se la data e l'ora pianificate rientrano dopo il ritardo massimo di 30 o 90 giorni configurato, l'aggiornamento del firmware viene applicato quando viene raggiunto il ritardo massimo. La data e l'ora pianificate vengono ignorate. Inoltre, l'aggiornamento remoto di dispositivi Microsoft Teams è una funzionalità non ancora disponibile nei tenant di US Government Cloud (GCC-High).

Per gestire i dispositivi, è necessario essere un amministratore globale, un amministratore dei servizi di Teams o un amministratore di dispositivi di Teams. Per altre informazioni sui ruoli di amministratore, vedere Usare i ruoli di amministratore [di Microsoft Teams per gestire Teams.](../using-admin-roles.md)

## <a name="choose-automatic-device-firmware-update-behavior"></a>Scegliere il comportamento di aggiornamento automatico del firmware del dispositivo

Gli aggiornamenti del firmware del dispositivo vengono applicati automaticamente. È possibile decidere se applicare gli aggiornamenti non appena uno viene rilasciato (se si sceglie questa opzione, gli aggiornamenti vengono applicati il primo fine settimana dopo il rilascio di un aggiornamento) oppure 30 o 90 giorni dopo il rilascio di un aggiornamento. Per impostazione predefinita, gli aggiornamenti del firmware del dispositivo vengono applicati 30 giorni dopo il rilascio.

> [!IMPORTANT]
> L'ultima versione dell'aggiornamento del firmware non viene applicata sul tuo dispositivo Teams. L'aggiornamento applicato automaticamente nel dispositivo viene invece ritardato di una versione. Ad esempio, si supponga che nel dispositivo sia applicata la versione "10" e che sia stata rilasciata la versione "11". La versione "11" non verrà ancora applicata. Il dispositivo verrà invece aggiornato alla versione "11" solo dopo il rilascio della versione "12".

> [!NOTE]
> Alcuni dispositivi non supportano ancora l'aggiornamento automatico del firmware. L'applicazione delle impostazioni di aggiornamento automatico del firmware sui dispositivi che non supportano gli aggiornamenti automatici non avrà alcun effetto su tali dispositivi. Per domande sul supporto degli aggiornamenti automatici del firmware per il dispositivo, contatta il produttore del dispositivo.

Per scegliere il comportamento di aggiornamento automatico per i dispositivi, eseguire le operazioni seguenti:

1. Accedi all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com
2. Spostarsi **tra i telefoni** dei  >  **dispositivi** o le barre di **collaborazione**
3. Seleziona uno o più dispositivi e quindi seleziona **Aggiorna**
4. In **Aggiornamento automatico firmware** selezionare una delle opzioni seguenti:
    - **Non appena disponibile** Il secondo aggiornamento più recente del firmware per dispositivi viene applicato il primo fine settimana dopo il rilascio dell'ultimo aggiornamento.
    - **Rimandare 30 giorni** Il secondo aggiornamento più recente del firmware per dispositivi viene applicato 30 giorni dopo il rilascio dell'ultimo aggiornamento.
    - **Rimandare 90 giorni** Il secondo aggiornamento più recente del firmware per dispositivi viene applicato 90 giorni dopo il rilascio dell'ultimo aggiornamento.
5. Selezionare **Aggiorna**

Se, per qualsiasi motivo, devi ripristinare un aggiornamento del firmware del dispositivo, devi ripristinare le impostazioni del produttore del dispositivo. Reimposta il dispositivo usando le istruzioni del produttore.  

## <a name="manually-update-remote-devices"></a>Aggiornare manualmente i dispositivi remoti

Quando si aggiornano uno o più dispositivi con l'interfaccia di amministrazione, è possibile decidere se aggiornare immediatamente i dispositivi o pianificare un aggiornamento per una data e un'ora future.

Per aggiornare manualmente i dispositivi remoti, eseguire le operazioni seguenti:

1. Accedi all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com
2. Spostarsi **tra i telefoni** dei  >  **dispositivi** o le barre di **collaborazione**
3. Seleziona uno o più dispositivi e quindi seleziona **Aggiorna**
4. In **Aggiornamenti manuali** selezionare Pianificazione **se** si vuole pianificare l'aggiornamento per una data e un'ora future. Gli aggiornamenti vengono applicati alla data e all'ora nel fuso orario selezionato in **Fuso orario.**

Ciò che viene visualizzato dipende dal fatto che siano selezionati uno o più dispositivi. L'immagine a sinistra seguente mostra più dispositivi selezionati, mentre l'immagine a destra mostra un singolo dispositivo selezionato.

:::image type="content" source="../media/device-update-status.png" alt-text="Visualizzazioni per singoli dispositivi e più dispositivi nel riquadro di stato di aggiornamento del dispositivo":::

Quando si selezionano più dispositivi, è possibile scegliere i tipi di aggiornamento da applicare a ogni dispositivo selezionato. Selezionare i tipi di aggiornamento da applicare e quindi **Aggiorna.**

Quando si seleziona un singolo dispositivo, vengono visualizzati gli aggiornamenti disponibili per il dispositivo. Se sono disponibili più tipi di aggiornamento per il dispositivo, selezionare ogni tipo di aggiornamento da applicare. È possibile visualizzare **la versione corrente** applicata nel dispositivo e la nuova versione che verrà applicata.  Selezionare gli aggiornamenti da applicare e quindi **Aggiorna.**

Dopo aver selezionato **Aggiorna,** gli aggiornamenti vengono applicati ai dispositivi alla data e all'ora selezionate se è stato pianificato un aggiornamento. Se non è stata selezionata una data e un'ora future, gli aggiornamenti vengono applicati ai dispositivi entro pochi minuti.
