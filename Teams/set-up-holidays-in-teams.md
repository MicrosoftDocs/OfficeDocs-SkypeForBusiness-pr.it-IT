---
title: Configurare le festività in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.holidays.overview
- seo-marvel-apr2020
description: Informazioni su come configurare le festività in Microsoft teams per l'uso con gli operatori automatici.
ms.openlocfilehash: ff87a3888bc98e1794f8074052aae4c0bbe3545d
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993472"
---
# <a name="set-up-holidays-in-microsoft-teams"></a>Configurare le festività in Microsoft Teams

È possibile usare la caratteristica teams Holidays per inviare messaggi alternativi e routing ai chiamanti per date e ore specifiche quando i reparti, le code di chiamata o le persone dell'organizzazione seguiranno diverse ore lavorative o non saranno disponibili. Ad esempio, potresti creare una festività per il giorno del nuovo anno in cui l'organizzazione potrebbe essere chiusa.

Le festività create in questo articolo sono disponibili quando si [configura un operatore automatico](create-a-phone-system-auto-attendant.md), ognuno con le proprie impostazioni di saluto e di routing delle chiamate.

## <a name="create-a-holiday"></a>Creare una festività

Per creare una festività

1. Nell'interfaccia di amministrazione di Microsoft teams, vai a vacanze **impostazioni a livello di organizzazione**  >  **Holidays**.

2. Selezionare **nuova festività**.

3. Immettere un nome per la festività.

4. Selezionare **Aggiungi nuova data**.

5. In **ora inizio** selezionare l'icona del calendario e scegliere la data in cui si vuole iniziare la festività.

6. Usare l'elenco a discesa per selezionare un'ora di inizio per la festività.

7. In **fine ora** selezionare l'icona del calendario e scegliere la data in cui si vuole terminare la festività.

8. Usare l'elenco a discesa per selezionare un'ora di fine per la festività. L' **ora di fine** deve essere successiva all' **ora di inizio**.  

   > [!NOTE]
   > Se la festività è per un giorno intero (ad esempio un periodo di 24 ore), l' **ora di fine** deve essere impostata sul giorno successivo e sull'ora di 12:00 AM. Ad esempio, se l'organizzazione è chiusa il 1 ° gennaio per il giorno del nuovo anno, impostare l' **ora di inizio** su gennaio 1 12:00 AM e impostare l' **ora di fine** del 2 gennaio @ 12:00 AM.

9. Facoltativamente, aggiungere altre date per le festività periodiche.

10. Selezionare **Salva**.

    ![Screenshot dell'interfaccia utente per le festività con date configurate per tre anni](media/holidays-set-up.png)

## <a name="change-a-holiday"></a>Modificare una festività

Per modificare una festività

1. Nell'interfaccia di amministrazione di Microsoft teams, vai a vacanze **impostazioni a livello di organizzazione**  >  **Holidays**.

2. Selezionare la festività nell'elenco.

3. In **ora inizio** selezionare l'icona del calendario e scegliere la data in cui si vuole iniziare la festività.

4. Usare l'elenco a discesa per selezionare un'ora di inizio per la festività.

5. In **fine ora** selezionare l'icona del calendario e scegliere la data in cui si vuole terminare la festività. 

6. Usare l'elenco a discesa per selezionare un'ora di fine per la festività. L' **ora di fine** deve essere successiva all' **ora di inizio**.  

7. Selezionare **Salva**.

## <a name="related-topics"></a>Argomenti correlati

[Pianificare gli operatori automatici di teams e le code di chiamata](plan-auto-attendant-call-queue.md)?
