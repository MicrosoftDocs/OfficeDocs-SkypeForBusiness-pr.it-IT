---
title: Conformità delle comunicazioni per Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Informazioni sulla conformità delle comunicazioni, parte del set di soluzioni di rischio Insider, dalla prospettiva Microsoft Teams (questo fa parte della funzionalità di conformità delle comunicazioni di M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01d9906044fe0ea8472cd8bb2ba8ccf247cdbeb9
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121696"
---
# <a name="communication-compliance-for-microsoft-teams"></a>Conformità delle comunicazioni per Microsoft Teams

La conformità delle comunicazioni fa parte della nuova soluzione Insider Risk impostata in Microsoft 365 che consente di ridurre al minimo i rischi per la comunicazione aiutandoli a rilevare, acquisire e adottare azioni correttive per i messaggi non appropriati nell'organizzazione. Aiuta ad identificare il linguaggio offensivo e l'anti-molestia nei canali del team o in 1:1 e chat di gruppo. È anche possibile impostare i criteri per verificare se le informazioni riservate vengono condivise come parte dei canali del team o di 1:1 e chat di gruppo. Per altre informazioni sui diversi tipi di criteri e su come configurarlo, vedere l' [articolo di M365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-teams"></a>Come usare la conformità delle comunicazioni in teams

### <a name="identify-inappropriate-messages"></a>Identificare i messaggi non appropriati

Per identificare i messaggi inviati in Microsoft Teams (1:1, chat di gruppo o conversazioni di canale) che contengono un linguaggio offensivo o anti-molestie, è possibile abilitare i criteri per identificare il problema e il revisore può esaminare i messaggi e eseguire le operazioni necessarie, ad esempio l'invio di materiale didattico o l'escalation alle autorità di destra.

### <a name="identify-sensitive-or-regulatory-information"></a>Identificare informazioni riservate o normative

Per analizzare i messaggi inviati in Microsoft Teams (1:1, chat di gruppo o conversazioni di canale) per informazioni riservate o tipi di regolamentazione, è possibile scegliere i criteri che supportano i tipi di normative o sensibili predefiniti.

> [!NOTE]
> I canali privati non sono supportati dalla conformità delle comunicazioni.

### <a name="custom-policy"></a>Criteri personalizzati

Usare questo modello per configurare specifici canali di comunicazione, singole condizioni di rilevamento e la quantità di contenuto da monitorare e rivedere nell'organizzazione.

### <a name="custom-trainable-classifier"></a>Classificatore addestrabile personalizzato

Usare i classificatori trainable quando uno dei classificatori fuori sede non soddisfa le proprie esigenze. Un classificatore Microsoft 365 è uno strumento che puoi addestrare per riconoscere vari tipi di contenuto dandogli esempi da esaminare. Formazione il classificatore include prima di tutto gli esempi che sono scelti in modo umano e corrispondono positivamente alla categoria. Dopo aver elaborato questi esempi, è quindi possibile testare le stime assegnando una combinazione di esempi positivi e negativi. Per altre informazioni su questo argomento, vedere l' [articolo di M365](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) .

> [!NOTE]
> La conformità delle comunicazioni ora supporta le distribuzioni ibride di Exchange.

La conformità delle comunicazioni supporta la cronologia delle conversazioni per tutti i messaggi corrispondenti alle forze di polizia. Questo fornisce il contesto all'amministratore delle indagini.

:::image type="content" source="media/communication-compliance-1.png" alt-text="Uno schermo per la conformità delle comunicazioni in Microsoft teams.":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a>Dove i criteri di comunicazione possono essere applicati in teams

I criteri di conformità delle comunicazioni possono essere impostati per i messaggi inviati in teams ai livelli seguenti:

- Livello utente: un amministratore può configurare i criteri a livello di singolo utente o applicarlo a tutti gli utenti del tenant. Verranno illustrati solo i messaggi inviati da un utente in 1:1 o chat di gruppo.
- Livello di Team: un amministratore può anche configurare i criteri in un team. In questo articolo vengono illustrati tutti i messaggi inviati nel canale del team (i messaggi di canale privato non sono supportati).
