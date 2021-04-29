---
title: Guida per gli amministratori a Reflect in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: "Una guida per amministratori a Reflect in Microsoft Teams per l'istruzione. "
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2594b39fed7d7194aabacd5df1a977a9d1262d70
ms.sourcegitcommit: 03ff569a0b7a8e04d7b0ab32f370a9a537fa7fe7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "52064865"
---
# <a name="it-admin-guide-to-reflect-in-microsoft-teams"></a>Guida per gli amministratori a Reflect in Microsoft Teams

Questo documento fornisce informazioni relative a [Reflect](https://aka.ms/reflect) – una componente primaria di [Education Insights in Microsoft Teams](class-insights.md). Reflect aiuta gli studenti a riconoscere ed esplorare le proprie emozioni offrendo opportunità regolari per condividere ed essere ascoltati. Reflect può contribuire a espandere il lessico emotivo e aumentare l'empatia verso i propri compagni fornendo input utili ai docenti per creare ambienti scolastici più salutari.  

Questa app utilizza emoji e granularità emotiva basata sulla ricerca per supportare i docenti introducendo elementi di apprendimento sociale ed emotivo nella loro routine impegnativa.


## <a name="privacy-and-security"></a>Privacy e sicurezza
Reflect applica gli stessi standard di sicurezza e riservatezza di Education Insights per proteggere i dati sensibili degli studenti.

Le informazioni raccolte e visualizzate tramite Reflect soddisfano [oltre 90 standard normativi e di settore](/compliance/regulatory/offering-home), tra cui [GDPR](/compliance/regulatory/gdpr) e [FERPA (Family Education Rights and Privacy Act)](/compliance/regulatory/offering-ferpa) per la sicurezza degli studenti e dei bambini e altre normative simili orientate alla privacy.

Gli studenti *non vedono mai* i nomi degli altri studenti, ma solo il modo in cui rispondono.  Anche se possono vedere la distribuzione delle risposte, *non possono* vedere i nomi associati a ogni riflessione. 

> [!NOTE]
> Se rispondono meno di cinque studenti, nessun dato viene mostrato agli studenti. In questo modo viene minimizzata la capacità degli studenti di identificare le risposte dei compagni.

## <a name="data-collection-and-storage"></a>Raccolta e archiviazione dei dati
I dati appartengono all'istituto di istruzione, e Microsoft si limita solo a raccoglierli e ad archiviarli. Il personale Microsoft non può accedere ai dati o visualizzarli, se non per quanto consentito dalla conformità in modo controllato per gestire il servizio, ad esempio per il recupero dei dati.

I dati vengono archiviati in Education Insights. Per impostazione predefinita, Education Insights è attivato. Quando si sceglie di non usare il servizio, **tutti i dati raccolti per Reflect verranno eliminati**. Se si riattiva Education Insights, la raccolta dei dati inizierà dal momento in cui il servizio viene riattivato.

Nella [Guida per gli amministratori a Education Insights](class-insights.md), puoi leggere il funzionamento di Education Insights (inclusi percorsi di archiviazione) e [come attivare o disattivare Education Insights](class-insights.md#turn-insights-off-or-on) quando vuoi cancellare i dati o abilitare il servizio.

I dati sono raccolti dagli studenti in Reflect, anche se i dati degli utenti guest non vengono raccolti. **Se uno studente viene definito come un utente guest, i dati non vengono raccolti.** 

## <a name="enable-reflect"></a>Abilita Reflect
Se gestisci i criteri di configurazione delle app per il tuo istituto, assicurai che Reflect sia *consentito* nel tuo tenant. Puoi anche aggiungere Reflect ai team di classe rilevanti dall'interfaccia di amministrazione di Teams.

Per consentire a un utente di installare e interagire con qualsiasi app, devi autorizzazione l'app a livello di organizzazione nella pagina **Gestisci app** e nel **criterio di autorizzazione dell'app** assegnato all'utente.

Se in precedenza hai stabilito che ogni app deve essere autorizzata, passa alla pagina Gestisci app e "consenti" Reflect. **Quando blocchi un'app, l'app non compare in Teams per qualsiasi utente dell'organizzazione.**

> [!TIP]
> Per altri dettagli, leggi [come consentire un'app o aggiungerla a un team di classe](manage-apps.md#allow-and-block-apps).


## <a name="where-do-educators-find-reflect"></a>Dove possono trovare Reflect i docenti?
Dopo aver abilitato Reflect, gli educatori entrano nella classe e selezionano **Nuova conversazione**. Possono poi selezionare '**…**' per aprire le estensioni di messaggistica e immettere **Reflect** nella barra di ricerca. La finestra di dialogo li guida nella definizione delle domanda e delle autorizzazioni di lettura degli utenti

:::image type="content" source="media/reflect-add-app.png" alt-text="Aggiungere Reflect al team di classe":::

È possibile fare clic destro sull'icona Reflect e selezionare **Blocca in alto** per accedervi rapidamente.

:::image type="content" source="media/insights-pin-app.png" alt-text="Aggiungere l'app Insights":::

> [!TIP]
> È anche possibile individuare l'app Insights tramite questo collegamento: [https://aka.ms/getReflect](https://aka.ms/getReflect)

> [!TIP]
> Per altri dettagli, visita la [pagina dell'assistenza di Reflect](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a). Questa pagina fornisce istruzioni sia per i docenti che per gli studenti, e descrive come creare il primo check-in di Reflect.
