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
description: Aggiornare i telefoni di Microsoft Teams, i pannelli di Teams e i Teams Rooms sui dispositivi Android in remoto usando l'interfaccia di amministrazione di Teams.
ms.openlocfilehash: c69a4deb43df5d40bf158a3c5bc467d431b041d5
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438264"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Aggiornare i dispositivi Microsoft Teams in remoto

Usando l'interfaccia di amministrazione di Microsoft Teams, è possibile aggiornare i dispositivi di Teams, ad esempio i telefoni di Teams, i pannelli teams e Teams Rooms su Android, in remoto. I componenti software seguenti nel dispositivo possono essere aggiornati dall'interfaccia di amministrazione di Teams:

- App Teams
- Firmware del dispositivo

Gli aggiornamenti del firmware del dispositivo si verificano automaticamente per impostazione predefinita. È tuttavia possibile aggiornare manualmente il firmware e altri componenti software. Quando si applicano manualmente gli aggiornamenti, possono essere applicati immediatamente o pianificati per una data e un'ora future.

Solo le versioni del firmware testate da Microsoft sono disponibili per l'aggiornamento automatico o manuale tramite l'interfaccia di amministrazione di Teams. Le versioni del firmware testate da Microsoft sono etichettate **come verificate da Microsoft**. Le versioni del firmware che non sono state testate da Microsoft sono etichettate come **Versione sconosciuta**. I dispositivi che eseguono una versione sconosciuta del firmware non possono essere aggiornati automaticamente; questi dispositivi possono essere aggiornati solo manualmente.

Per gestire i dispositivi, è necessario essere un amministratore globale, un amministratore del servizio teams o un amministratore di dispositivi di Teams. Per altre informazioni sui ruoli di amministratore, vedere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](../using-admin-roles.md).

## <a name="assign-devices-to-an-automatic-update-phase"></a>Assegnare dispositivi a una fase di aggiornamento automatico

L'assegnazione di dispositivi a una fase di aggiornamento automatico è una funzionalità di Teams Rooms Pro per Teams Rooms nei dispositivi Android. I dispositivi con una licenza Teams Rooms Basic verranno assegnati alla fase Generale. Verrà mantenuta qualsiasi fase pre-configurata e non saranno consentite ulteriori modifiche. Per altre informazioni, vedere [Microsoft Teams Rooms licenze](../rooms/rooms-licensing.md).  

Gli aggiornamenti automatici dei dispositivi Teams con l'interfaccia di amministrazione di Teams non sono disponibili in GCC High. Le organizzazioni in GCC High possono, tuttavia, [aggiornare manualmente i dispositivi di Teams](#manually-update-remote-devices) usando l'interfaccia di amministrazione di Teams.

> [!IMPORTANT]
> La funzionalità di aggiornamento automatico è attualmente in fase di rilascio anticipato. Aggiornamenti potrebbe essere distribuito più lentamente della fase selezionata. Nei prossimi mesi, la velocità con cui gli aggiornamenti vengono distribuiti automaticamente aumenterà fino a raggiungere la fase selezionata.

> [!NOTE]
> Alcuni dispositivi non supportano ancora gli aggiornamenti automatici del firmware. L'applicazione delle impostazioni di aggiornamento automatico del firmware nei dispositivi che non supportano gli aggiornamenti automatici non avrà alcun effetto su tali dispositivi. Per domande su se il dispositivo supporterà gli aggiornamenti automatici del firmware, contatta il produttore del dispositivo.
>
> Aggiornamenti vengono applicate nei fine settimana e al di fuori dell'orario di ufficio tipico per evitare interruzioni. I dispositivi in una fase verranno aggiornati gradualmente nell'arco di alcune settimane anziché tutti insieme.

Per scegliere la fase di aggiornamento automatico per i dispositivi, esegui le operazioni seguenti:

1. Accedere all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Passa ai **dispositivi Teams** e quindi seleziona **Telefoni**, **Schermi**, **Pannelli** o **Teams Rooms su Android**.  
3. Seleziona uno o più dispositivi e quindi seleziona **Aggiorna**.
4. In **Aggiornamento automatico firmware** seleziona una delle opzioni seguenti:
    - **Test** Questa opzione è ideale per i dispositivi di laboratorio o di test su cui è possibile eseguire qualsiasi convalida che è necessario eseguire. Aggiornamenti avviare la distribuzione non appena viene rilasciata l'ultima versione del firmware. Precedentemente chiamato **Il più presto possibile**.
    - **Generale** Questa è l'opzione predefinita ed è ideale per la maggior parte dei dispositivi di uso generale. Aggiornamenti avviare la distribuzione solo dopo 30 giorni dal rilascio della nuova versione del firmware. Precedentemente chiamato **Rinvia di 30 giorni**.
    - **Finale** Questa opzione è ideale per i dispositivi usati dai vip e in impostazioni di grandi dimensioni dopo il completamento della convalida su larga scala. Aggiornamenti avviare la distribuzione solo dopo 90 giorni dal rilascio della nuova versione del firmware. Precedentemente chiamato **Rinvia di 90 giorni**.
5. Seleziona **Aggiorna**.

Per vedere in quali dispositivi di fase si trovano, vedere la colonna **Aggiornamento automatico firmware** nell'interfaccia di amministrazione di Teams. Per vedere quali dispositivi fanno parte di una fase specifica, usare l'opzione **Filtro** con il parametro **fase di aggiornamento automatico** .

Per ripristinare un aggiornamento del firmware del dispositivo, devi ripristinare le impostazioni predefinite del dispositivo. Ripristina il dispositivo seguendo le istruzioni fornite dal produttore.  

## <a name="manually-update-remote-devices"></a>Aggiornare manualmente i dispositivi remoti

Se si vogliono aggiornare manualmente i dispositivi usando l'interfaccia di amministrazione di Teams, è possibile decidere se aggiornare i dispositivi immediatamente o pianificare un aggiornamento per una data e un'ora future.

Per aggiornare manualmente i dispositivi remoti, eseguire le operazioni seguenti:

1. Accedere all'interfaccia di amministrazione di Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Esplora **Dispositivi di Teams** e quindi seleziona **Telefoni**, **Schermi**, **Pannelli** o **Teams Rooms su Android**.
3. Seleziona uno o più dispositivi e quindi seleziona **Aggiorna**.
4. In **Aggiornamenti manuali** seleziona **Pianifica** se vuoi pianificare l'aggiornamento per una data e un'ora future. Gli aggiornamenti vengono applicati alla data e all'ora nel fuso orario selezionato in **Fuso orario**.

Ciò che vedrai dipende dal fatto che tu abbia uno o più dispositivi selezionati. L'immagine a sinistra seguente mostra più dispositivi selezionati mentre l'immagine a destra mostra un singolo dispositivo selezionato.

:::image type="content" source="../media/device-update-status.png" alt-text="Visualizzazioni per dispositivi singoli e multipli nel riquadro di stato dell'aggiornamento del dispositivo.":::

Quando selezioni più dispositivi, puoi scegliere quali tipi di aggiornamento applicare a ogni dispositivo selezionato. Seleziona i tipi di aggiornamento che vuoi applicare e seleziona **Aggiorna**.

Quando selezioni un singolo dispositivo, vengono visualizzati gli aggiornamenti disponibili per il dispositivo. Se sono disponibili più tipi di aggiornamento per il dispositivo, seleziona ogni tipo di aggiornamento da applicare. È possibile visualizzare la **versione corrente** applicata nel dispositivo e la **nuova versione** che verrà applicata. Seleziona gli aggiornamenti che vuoi applicare e seleziona **Aggiorna**.

Dopo aver selezionato **Aggiorna**, gli aggiornamenti vengono applicati ai dispositivi alla data e all'ora selezionate se hai pianificato un aggiornamento. Se non hai selezionato una data e un'ora future, gli aggiornamenti vengono applicati ai tuoi dispositivi entro pochi minuti.
