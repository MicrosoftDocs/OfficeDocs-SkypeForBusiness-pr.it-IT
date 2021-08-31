---
title: Aggiornare Microsoft Teams dispositivi in remoto
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
ms.localizationpriority: medium
description: Aggiornare Microsoft Teams telefoni, Teams e barre di collaborazione in remoto usando l'interfaccia Teams di amministrazione
ms.openlocfilehash: c35fc24be2456c4ee1583e7a073a7c4dcf8e7214
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727465"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Aggiornare Microsoft Teams dispositivi in remoto

Usando l'interfaccia di amministrazione di Microsoft Teams, è possibile aggiornare i dispositivi Teams, ad esempio telefoni Teams, pannelli Teams e barre di collaborazione, in remoto e scegliere il comportamento di aggiornamento automatico del firmware del dispositivo. È possibile aggiornare quanto segue nei dispositivi usando l'interfaccia Teams di amministrazione:

- Teams'app e l'agente di amministrazione di Teams
- App portale aziendale
- App agente OEM
- Firmware del dispositivo

Gli aggiornamenti del firmware del dispositivo possono essere applicati automaticamente o pianificati per una data e un'ora future. Gli altri aggiornamenti disponibili per i dispositivi non vengono applicati automaticamente, ma possono essere applicati manualmente o pianificati per una data e un'ora future.

> [!NOTE]
> Anche se è possibile programmare gli aggiornamenti del firmware del dispositivo, se la data e l'ora pianificate rientrano dopo il ritardo massimo di 30 o 90 giorni configurato, l'aggiornamento del firmware viene applicato quando viene raggiunto il ritardo massimo. La data e l'ora pianificate vengono ignorate. Inoltre, l'aggiornamento Microsoft Teams dispositivi in remoto è una funzionalità non ancora disponibile nei tenant government cloud degli Stati Uniti (GCC-High).

Per gestire i dispositivi, è necessario essere un amministratore globale, un amministratore Teams Service o un amministratore Teams dispositivo. Per altre informazioni sui ruoli di amministratore, vedere Usare Microsoft Teams [di amministratore per gestire Teams](../using-admin-roles.md).

## <a name="choose-automatic-device-firmware-update-behavior"></a>Scegliere il comportamento di aggiornamento automatico del firmware del dispositivo

Gli aggiornamenti del firmware del dispositivo vengono applicati automaticamente. È possibile decidere se applicare gli aggiornamenti non appena ne viene rilasciato uno (se si sceglie questa opzione, gli aggiornamenti vengono applicati il primo fine settimana dopo il rilascio di un aggiornamento) o 30 o 90 giorni dopo il rilascio di un aggiornamento. Per impostazione predefinita, gli aggiornamenti del firmware del dispositivo vengono applicati 30 giorni dopo il rilascio.

> [!IMPORTANT]
> La versione più recente dell'aggiornamento del firmware non viene applicata nel Teams dispositivo. L'aggiornamento applicato automaticamente al dispositivo viene invece ritardato di una versione. Si supponga, ad esempio, che nel dispositivo sia applicata la versione "10" e che sia stata rilasciata la versione "11". La versione "11" non verrà ancora applicata. Il dispositivo verrà invece aggiornato alla versione "11" solo dopo il rilascio della versione "12".

> [!NOTE]
> Alcuni dispositivi non supportano ancora l'aggiornamento automatico del firmware. L'applicazione delle impostazioni di aggiornamento automatico del firmware nei dispositivi che non supportano gli aggiornamenti automatici non avrà alcun effetto su tali dispositivi. Per domande sul fatto che il dispositivo supporti gli aggiornamenti automatici del firmware, contattare il produttore del dispositivo.

Per scegliere il comportamento di aggiornamento automatico per i dispositivi, eseguire le operazioni seguenti:

1. Accedere all'Microsoft Teams di amministrazione https://admin.teams.microsoft.com visitando .
2. Esplorare **i telefoni** IP dei dispositivi o le barre di collaborazione o Teams  >   **pannelli.** 
3. Selezionare uno o più dispositivi e quindi scegliere **Aggiorna**.
4. In **Aggiornamento automatico firmware** selezionare una delle opzioni seguenti:
    - **Non appena disponibile** Il secondo aggiornamento del firmware del dispositivo più recente viene applicato il primo fine settimana dopo il rilascio dell'ultimo aggiornamento.
    - **Posticipa 30 giorni** Il secondo aggiornamento del firmware del dispositivo più recente viene applicato 30 giorni dopo il rilascio dell'ultimo aggiornamento.
    - **Posticipa 90 giorni** Il secondo aggiornamento del firmware del dispositivo più recente viene applicato 90 giorni dopo il rilascio dell'ultimo aggiornamento.
5. Selezionare **Aggiorna**.

Se, per qualsiasi motivo, è necessario ripristinare un aggiornamento del firmware del dispositivo, è necessario reimpostare il dispositivo alle impostazioni di fabbrica. Reimposta il dispositivo usando le istruzioni del produttore.  

## <a name="manually-update-remote-devices"></a>Aggiornare manualmente i dispositivi remoti

Quando si aggiornano uno o più dispositivi tramite l'interfaccia di amministrazione, è possibile decidere se aggiornare immediatamente i dispositivi o pianificare un aggiornamento per una data e un'ora future.

Per aggiornare manualmente i dispositivi remoti, eseguire le operazioni seguenti:

1. Accedere all'Microsoft Teams di amministrazione https://admin.teams.microsoft.com visitando .
2. Esplorare **i telefoni** IP dei  >  **dispositivi** o barre di **collaborazione** o **Teams pannelli.**
3. Selezionare uno o più dispositivi e quindi scegliere **Aggiorna**.
4. In **Aggiornamenti manuali** selezionare **Pianifica** se si vuole pianificare l'aggiornamento per una data e un'ora future. Gli aggiornamenti vengono applicati alla data e all'ora del fuso orario selezionato in **Fuso orario.**

Ciò che vedrai dipende dal fatto che tu abbia selezionato uno o più dispositivi. L'immagine a sinistra seguente mostra più dispositivi selezionati, mentre l'immagine a destra mostra un singolo dispositivo selezionato.

:::image type="content" source="../media/device-update-status.png" alt-text="Visualizzazioni per singoli e più dispositivi nel riquadro di stato dell'aggiornamento del dispositivo.":::

Quando si selezionano più dispositivi, è possibile scegliere i tipi di aggiornamento da applicare a ogni dispositivo selezionato. Selezionare i tipi di aggiornamento da applicare e scegliere **Aggiorna**.

Quando si seleziona un singolo dispositivo, vengono visualizzati gli aggiornamenti disponibili per il dispositivo. Se sono disponibili più tipi di aggiornamento per il dispositivo, selezionare ogni tipo di aggiornamento da applicare. È possibile visualizzare **la versione corrente** applicata nel dispositivo e la nuova **versione** che verrà applicata. Selezionare gli aggiornamenti da applicare e scegliere **Aggiorna**.

Dopo aver selezionato **Aggiorna,** gli aggiornamenti vengono applicati ai dispositivi alla data e all'ora selezionate se è stato pianificato un aggiornamento. Se non è stata selezionata una data e un'ora future, gli aggiornamenti vengono applicati ai dispositivi entro pochi minuti.
