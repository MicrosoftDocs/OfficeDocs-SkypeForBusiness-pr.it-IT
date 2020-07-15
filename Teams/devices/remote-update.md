---
title: Aggiornare i dispositivi Microsoft teams in remoto
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
description: Aggiornare i telefoni di Microsoft teams e le barre di collaborazione in remoto usando l'interfaccia di amministrazione Teams
ms.openlocfilehash: f7607da002be7f038e4cafe5b4b6026ea2d99ddf
ms.sourcegitcommit: 2cc36c954200f50de33b909856b33fe0a9a6b7a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45125949"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Aggiornare i dispositivi Microsoft teams in remoto

Con l'interfaccia di amministrazione di Microsoft teams è possibile aggiornare i dispositivi team, ad esempio telefoni e barre di collaborazione, in remoto e scegliere il comportamento di aggiornamento automatico del firmware del dispositivo. È possibile aggiornare i seguenti dispositivi usando l'interfaccia di amministrazione di teams:

- App teams e agente di amministrazione Teams
- App portale aziendale
- App agente OEM
- Firmware del dispositivo

Gli aggiornamenti del firmware del dispositivo possono essere applicati automaticamente o pianificati per una data e un'ora future. Gli altri aggiornamenti del dispositivo disponibili non vengono applicati automaticamente, ma possono essere applicati manualmente o pianificati per una data e un'ora future.

> [!NOTE]
> Mentre gli aggiornamenti del firmware del dispositivo possono essere pianificati, se la data e l'ora pianificate ricadono dopo il ritardo massimo configurato di 30 o 90 giorni, l'aggiornamento del firmware viene applicato quando viene raggiunto il ritardo massimo. La data e l'ora pianificate vengono ignorate. Inoltre, l'aggiornamento remoto di Microsoft teams Devices è una funzionalità non ancora disponibile nei tenant di cloud governative degli Stati Uniti (GCC-High).

## <a name="choose-automatic-device-firmware-update-behavior"></a>Scegliere il comportamento di aggiornamento automatico del firmware del dispositivo

Gli aggiornamenti del firmware del dispositivo vengono applicati automaticamente. È possibile decidere se applicare gli aggiornamenti non appena uno viene rilasciato oppure 30 o 90 giorni dopo il rilascio di un aggiornamento. Per impostazione predefinita, gli aggiornamenti del firmware del dispositivo vengono applicati 30 giorni uno rilasciato.

> [!IMPORTANT]
> La versione più recente dell'aggiornamento del firmware non viene applicata nel dispositivo teams. L'aggiornamento applicato automaticamente al dispositivo è invece ritardato di una versione. Si supponga, ad esempio, che il dispositivo abbia applicato la versione "10" e che la versione "11" sia stata rilasciata. La versione "11" non verrà ancora applicata. Al contrario, il dispositivo verrà aggiornato alla versione "11" dopo il rilascio della versione "12".

Per scegliere il comportamento di aggiornamento automatico per i dispositivi, eseguire le operazioni seguenti:

1. Accedere all'interfaccia di amministrazione di Microsoft teams visitandohttps://admin.teams.microsoft.com
2. Spostarsi tra i telefoni dei **dispositivi**  >  **Phones** o le **barre di collaborazione**
3. Selezionare uno o più dispositivi e quindi fare clic su **Aggiorna**
4. In **aggiornamento automatico del firmware**selezionare una delle opzioni seguenti:
    - Non **appena disponibile** Il secondo aggiornamento del firmware per dispositivi più recente viene applicato il più presto possibile dopo il rilascio dell'ultimo aggiornamento.
    - **Rinviare 30 giorni** Il secondo aggiornamento del firmware per dispositivi più recente viene applicato 30 giorni dopo il rilascio dell'ultimo aggiornamento.
    - **Rinviare 90 giorni** Il secondo aggiornamento del firmware per il dispositivo viene applicato 90 giorni dopo il rilascio dell'ultimo aggiornamento.
5. Selezionare **Aggiorna**

Se, per qualsiasi motivo, è necessario ripristinare un aggiornamento del firmware del dispositivo, è necessario reimpostare il dispositivo sulle impostazioni di fabbrica. Reimpostare il dispositivo usando le istruzioni del produttore.  

## <a name="manually-update-remote-devices"></a>Aggiornare manualmente i dispositivi remoti

Quando si aggiorna uno o più dispositivi con l'interfaccia di amministrazione, è possibile decidere se aggiornare i dispositivi immediatamente o pianificare un aggiornamento per una data e un'ora future.

Per aggiornare manualmente i dispositivi remoti, eseguire le operazioni seguenti:

1. Accedere all'interfaccia di amministrazione di Microsoft teams visitandohttps://admin.teams.microsoft.com
2. Spostarsi tra i telefoni dei **dispositivi**  >  **Phones** o le **barre di collaborazione**
3. Selezionare uno o più dispositivi e quindi fare clic su **Aggiorna**
4. In **aggiornamenti manuali**selezionare **pianificazione** se si vuole pianificare l'aggiornamento per una data e un'ora future. Gli aggiornamenti vengono applicati alla data e all'ora nel fuso orario selezionato in **TimeZone**.

Ciò che vedrai dipende dal fatto che tu abbia uno o più dispositivi selezionati. L'immagine a sinistra seguente mostra più dispositivi selezionati mentre l'immagine a destra mostra un singolo dispositivo selezionato.

:::image type="content" source="../media/device-update-status.png" alt-text="Visualizzazioni per dispositivi singoli e multipli nel riquadro Stato aggiornamento dispositivi":::

Quando si selezionano più dispositivi, è possibile scegliere i tipi di aggiornamento da applicare a ogni dispositivo selezionato. Selezionare i tipi di aggiornamento che si desidera applicare e selezionare **Aggiorna**.

Quando si seleziona un singolo dispositivo, vengono visualizzati gli aggiornamenti disponibili per il dispositivo. Se sono disponibili più tipi di aggiornamento per il dispositivo, selezionare ogni tipo di aggiornamento da applicare. È possibile visualizzare la **versione corrente** applicata al dispositivo e la **nuova versione** che verrà applicata. Selezionare gli aggiornamenti che si desidera applicare e selezionare **Aggiorna**.

Dopo aver selezionato **aggiornamento**, gli aggiornamenti vengono applicati ai dispositivi in corrispondenza della data e dell'ora selezionata se è stato programmato un aggiornamento. Se non è stata selezionata una data e un'ora future, gli aggiornamenti vengono applicati ai dispositivi in pochi minuti.
