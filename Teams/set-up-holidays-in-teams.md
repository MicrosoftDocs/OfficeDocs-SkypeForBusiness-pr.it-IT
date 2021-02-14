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
description: Informazioni su come configurare le festività in Microsoft Teams per l'uso con gli operatori automatici.
ms.openlocfilehash: ff87a3888bc98e1794f8074052aae4c0bbe3545d
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993472"
---
# <a name="set-up-holidays-in-microsoft-teams"></a>Configurare le festività in Microsoft Teams

È possibile usare la funzionalità Festività di Teams per fornire messaggi alternativi e instradamento ai chiamanti per date e orari specifici in cui reparti, code di chiamata o persone dell'organizzazione se ne seguireranno l'orario di lavoro diverso o non saranno disponibili. Ad esempio, è possibile creare una festività per il giorno di Capodanno quando l'organizzazione potrebbe essere chiusa.

Le festività create qui sono disponibili quando [si](create-a-phone-system-auto-attendant.md)configura un operatore automatico, ognuna con il proprio messaggio di saluto e le impostazioni di instradamento delle chiamate.

## <a name="create-a-holiday"></a>Creare una festività

Per creare una festività

1. Nell'interfaccia di amministrazione di Microsoft Teams passare a Impostazioni **a livello di organizzazione**  >  **Festività.**

2. Selezionare **Nuova festività.**

3. Immettere un nome per la festività.

4. Selezionare **Aggiungi nuova data.**

5. In **Ora inizio** selezionare l'icona del calendario e scegliere la data in cui si desidera che inizi la festività.

6. Usare l'elenco a discesa per selezionare un'ora di inizio per la festività.

7. In **Ora fine** selezionare l'icona del calendario e scegliere la data in cui si desidera terminare la festività.

8. Usare l'elenco a discesa per selezionare un'ora di fine per la festività. **L'ora di** fine deve essere dopo **l'ora di inizio.**  

   > [!NOTE]
   > Se la festività è per un'intera giornata (ad esempio un  periodo di 24 ore), l'ora di fine deve essere impostata sul giorno successivo e l'ora su 12.00. Ad esempio, se l'organizzazione è chiusa il 1 gennaio  per il giorno di Capodanno, impostare l'ora  di inizio su 1 gennaio 12.00 e impostare l'ora di fine su 2 gennaio @ 12.00.

9. Facoltativamente, aggiungere altre date per le festività ricorrenti.

10. Selezionare **Salva**.

    ![Screenshot dell'interfaccia utente delle festività con le date impostate per tre anni](media/holidays-set-up.png)

## <a name="change-a-holiday"></a>Modificare una festività

Per modificare una festività

1. Nell'interfaccia di amministrazione di Microsoft Teams passare a Impostazioni **a livello di organizzazione**  >  **Festività.**

2. Selezionare la festività nell'elenco.

3. In **Ora inizio** selezionare l'icona del calendario e scegliere la data in cui si desidera che inizi la festività.

4. Usare l'elenco a discesa per selezionare un'ora di inizio per la festività.

5. In **Ora fine** selezionare l'icona del calendario e scegliere la data in cui si desidera terminare la festività. 

6. Usare l'elenco a discesa per selezionare un'ora di fine per la festività. **L'ora di** fine deve essere dopo **l'ora di inizio.**  

7. Selezionare **Salva**.

## <a name="related-topics"></a>Argomenti correlati

[Pianificare gli operatori automatici e le code di chiamata di Teams?](plan-auto-attendant-call-queue.md)
