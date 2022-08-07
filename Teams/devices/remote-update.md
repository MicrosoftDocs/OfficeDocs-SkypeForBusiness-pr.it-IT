---
title: Aggiornare i dispositivi Microsoft Teams in remoto
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Aggiornare i telefoni di Microsoft Teams, i pannelli di Teams e le barre di collaborazione in remoto usando l'interfaccia di amministrazione di Teams
ms.openlocfilehash: 36f84025feec5b88b2cbf28a52fcb89cb76aeaa5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269461"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Aggiornare i dispositivi Microsoft Teams in remoto

Usando l'interfaccia di amministrazione di Microsoft Teams, è possibile aggiornare i dispositivi di Teams, ad esempio i telefoni di Teams, i pannelli di Teams e le barre di collaborazione, in remoto, e scegliere il comportamento di aggiornamento automatico del firmware del dispositivo. È possibile aggiornare quanto segue sui dispositivi usando l'interfaccia di amministrazione di Teams:

- Agente di amministrazione dell'app Teams e dei team
- App portale aziendale
- App agente OEM
- Firmware del dispositivo

Gli aggiornamenti del firmware del dispositivo possono essere applicati automaticamente o pianificati per una data e un'ora future. Gli altri aggiornamenti disponibili per i dispositivi non vengono applicati automaticamente, ma possono essere applicati manualmente o pianificati per una data e un'ora future.

> [!NOTE]
> Durante la pianificazione degli aggiornamenti del firmware del dispositivo, se la data e l'ora pianificate rientrano dopo il ritardo massimo di 30 o 90 giorni configurato, l'aggiornamento del firmware viene applicato quando viene raggiunto il ritardo massimo. La data e l'ora programmate vengono ignorate. Inoltre, l'aggiornamento remoto dei dispositivi Microsoft Teams è una funzionalità non ancora disponibile nei tenant cloud per il governo degli Stati Uniti (GCC-High).

Per gestire i dispositivi, è necessario essere un amministratore globale, un amministratore del servizio teams o un amministratore di dispositivi di Teams. Per altre informazioni sui ruoli di amministratore, vedere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](../using-admin-roles.md).

## <a name="choose-automatic-device-firmware-update-behavior"></a>Scegli il comportamento di aggiornamento automatico del firmware del dispositivo

Gli aggiornamenti del firmware del dispositivo vengono applicati automaticamente. È possibile decidere se applicare gli aggiornamenti non appena ne viene rilasciato uno (se si sceglie questa opzione, gli aggiornamenti vengono applicati il primo fine settimana dopo il rilascio di un aggiornamento) oppure 30 o 90 giorni dopo il rilascio di un aggiornamento. Per impostazione predefinita, gli aggiornamenti del firmware del dispositivo vengono applicati 30 giorni dopo il rilascio.

> [!IMPORTANT]
> La versione più recente dell'aggiornamento del firmware non viene applicata al dispositivo Teams. Al contrario, l'aggiornamento applicato automaticamente nel dispositivo subisce un ritardo di una versione. Si supponga ad esempio che nel dispositivo sia applicata la versione "10" e che venga rilasciata la versione "11". La versione "11" non verrà ancora applicata. Al contrario, il dispositivo verrà aggiornato alla versione "11" solo dopo il rilascio della versione "12".

> [!NOTE]
> Alcuni dispositivi non supportano ancora l'aggiornamento automatico del firmware. L'applicazione delle impostazioni di aggiornamento automatico del firmware nei dispositivi che non supportano gli aggiornamenti automatici non avrà alcun effetto su tali dispositivi. Per domande su se il dispositivo supporterà gli aggiornamenti automatici del firmware, contatta il produttore del dispositivo.

Per scegliere il comportamento di aggiornamento automatico per i tuoi dispositivi, esegui le operazioni seguenti:

1. Accedere all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Spostarsi tra **i telefoni IP** **dei dispositivi di** >  Teams o **le barre di collaborazione** o **i pannelli di Teams**.
3. Seleziona uno o più dispositivi e quindi seleziona **Aggiorna**.
4. In **Aggiornamento automatico firmware** seleziona una delle opzioni seguenti:
    - **Non appena disponibile** Il secondo aggiornamento del firmware del dispositivo viene applicato il primo fine settimana dopo il rilascio dell'aggiornamento più recente.
    - **Rinvia 30 giorni** Il secondo aggiornamento del firmware del dispositivo viene applicato 30 giorni dopo il rilascio dell'aggiornamento più recente.
    - **Rinvia 90 giorni** Il secondo aggiornamento del firmware del dispositivo viene applicato 90 giorni dopo il rilascio dell'ultimo aggiornamento.
5. Seleziona **Aggiorna**.

Se, per qualsiasi motivo, devi ripristinare un aggiornamento del firmware del dispositivo, devi ripristinare le impostazioni del produttore del dispositivo. Ripristina il dispositivo seguendo le istruzioni fornite dal produttore.  

## <a name="manually-update-remote-devices"></a>Aggiornare manualmente i dispositivi remoti

Quando si aggiornano uno o più dispositivi tramite l'interfaccia di amministrazione, è possibile decidere se aggiornare i dispositivi immediatamente o pianificare un aggiornamento per una data e un'ora future.

Per aggiornare manualmente i dispositivi remoti, eseguire le operazioni seguenti:

1. Accedere all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Spostarsi tra **i telefoni IP** **dei dispositivi di** >  Teams o **le barre di collaborazione** o **i pannelli di Teams**.
3. Seleziona uno o più dispositivi e quindi seleziona **Aggiorna**.
4. In **Aggiornamenti manuali** seleziona **Pianifica** se vuoi pianificare l'aggiornamento per una data e un'ora future. Gli aggiornamenti vengono applicati alla data e all'ora nel fuso orario selezionato in **Fuso orario**.

Ciò che vedrai dipende dal fatto che tu abbia uno o più dispositivi selezionati. L'immagine a sinistra seguente mostra più dispositivi selezionati mentre l'immagine a destra mostra un singolo dispositivo selezionato.

:::image type="content" source="../media/device-update-status.png" alt-text="Visualizzazioni per dispositivi singoli e multipli nel riquadro di stato dell'aggiornamento del dispositivo.":::

Quando selezioni più dispositivi, puoi scegliere quali tipi di aggiornamento applicare a ogni dispositivo selezionato. Seleziona i tipi di aggiornamento che vuoi applicare e seleziona **Aggiorna**.

Quando selezioni un singolo dispositivo, vengono visualizzati gli aggiornamenti disponibili per il dispositivo. Se sono disponibili più tipi di aggiornamento per il dispositivo, seleziona ogni tipo di aggiornamento da applicare. È possibile visualizzare la **versione corrente** applicata nel dispositivo e la **nuova versione** che verrà applicata. Seleziona gli aggiornamenti che vuoi applicare e seleziona **Aggiorna**.

Dopo aver selezionato **Aggiorna**, gli aggiornamenti vengono applicati ai dispositivi alla data e all'ora selezionate se hai pianificato un aggiornamento. Se non hai selezionato una data e un'ora future, gli aggiornamenti vengono applicati ai tuoi dispositivi entro pochi minuti.
