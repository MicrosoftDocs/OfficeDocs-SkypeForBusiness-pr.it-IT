---
title: Pacchetti dei criteri di Microsoft teams per gli amministratori EDU
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i pacchetti di criteri in Microsoft teams.
ms.openlocfilehash: a49ab725ff0042b75afca9b1f9b4d7d9655c34b7
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676254"
---
# <a name="microsoft-teams-policy-packages-for-edu-admins"></a>Pacchetti dei criteri di Microsoft teams per gli amministratori EDU

Un pacchetto di criteri in Microsoft teams raccoglie i criteri predefiniti e le impostazioni dei criteri che è possibile assegnare agli utenti con ruoli simili nell'istituzione. I pacchetti di criteri semplificano, semplificano e aiutano a fornire coerenza durante la gestione dei criteri. Nella pratica normale assegna a ogni utente un pacchetto di criteri e, se necessario, ridefini i criteri in ogni pacchetto in base alle esigenze del gruppo di utenti. Quando si aggiornano le impostazioni in un pacchetto, tutti gli utenti assegnati al pacchetto vengono modificati come aggiornamento in blocco.

Gli istituti di istruzione in generale hanno molti tipi di utenti con esigenze esclusive, a seconda dell'età e della maturità degli studenti. Ad esempio, potresti voler concedere agli insegnanti e al personale l'accesso completo a Microsoft teams, ma vuoi limitare le funzionalità di Microsoft teams agli studenti per incoraggiare un ambiente di apprendimento sicuro e focalizzato. È possibile usare i pacchetti di criteri per personalizzare le impostazioni in base alle esigenze delle varie coorti della comunità scolastica.

## <a name="what-is-a-policy-package"></a>Che cos'è un pacchetto di criteri?

I pacchetti di criteri consentono di controllare le caratteristiche di Microsoft teams che consentono o limitano l'uso di Microsoft teams per specifici gruppi di persone dell'organizzazione. Ogni pacchetto di criteri è progettato intorno a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività tipiche di tale ruolo.

I pacchetti di criteri predefiniscono i criteri per:
- Messaggistica
-  Riunioni
- Configurazione dell'app
- Chiamate
- Eventi live

Microsoft teams include attualmente i seguenti pacchetti di criteri:

|Nome pacchetto elencato nell'interfaccia di amministrazione di Microsoft Teams |Ottimamente usato per  |Descrizione |
|:--- |:--- |:--- |
|Education_Teacher| Docenti e personale| Usare questo set di criteri e le impostazioni dei criteri per concedere agli insegnanti e al personale dell'organizzazione l'accesso completo alla chat, alle chiamate e alle riunioni tramite Microsoft teams. |
|Education_PrimaryStudent | Studenti delle scuole primarie di età compresa  | Gli studenti di età scolare più giovani e primari all'interno dell'Istituto potrebbero avere bisogno di più limiti all'interno di Microsoft teams. Usare questo set di criteri e le impostazioni dei criteri per limitare le funzionalità come la creazione e la gestione delle riunioni, la gestione delle chat e le chiamate private. |
|Education_SecondaryStudent| Studenti di età superiore | Gli studenti delle scuole secondarie di età compresa nell'Istituto potrebbero avere bisogno di più limiti in Microsoft teams. Usare questo set di criteri e le impostazioni dei criteri per limitare le funzionalità come la creazione e la gestione delle riunioni, la gestione delle chat e le chiamate private. |
|Education_HigherEducationStudent | Studenti dell'istruzione superiore | Gli studenti dell'istruzione superiore all'interno dell'intuizione potrebbero avere bisogno di meno limiti rispetto agli studenti più giovani, ma alcune limitazioni potrebbero essere consigliate. Puoi usare questo set di criteri e le impostazioni dei criteri per consentire l'accesso a chat, chiamate e riunioni all'interno dell'organizzazione, ma limita il modo in cui gli studenti usano Microsoft teams con partecipanti esterni. |
|||

A ogni singolo criterio viene assegnato il nome del pacchetto di criteri in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri. Ad esempio, quando si assegna il pacchetto di criteri Education_Teacher agli insegnanti dell'Istituto di istruzione, viene creato un criterio denominato Education_Teacher per ogni criterio nel pacchetto.

![Screenshot del pacchetto dei criteri di Education_Teacher](media/policy-packages-education_teacher.png)

> [!NOTE]
> Se si decide che gli insegnanti e il personale di supporto amministrativo necessitano di criteri diversi, è possibile riutilizzare un pacchetto esistente: identificare un pacchetto che non si sta usando e modificare le impostazioni in modo che siano appropriate per il gruppo. Potrebbe essere necessario prendere nota di quale gruppo ha il pacchetto, ma questo è l'unico ostacolo per riutilizzare un pacchetto.

## <a name="why-use-policy-packages"></a>Perché usare i pacchetti di criteri

Se l'Istituto ha centinaia o anche migliaia di utenti, è possibile chiedersi: "perché richiedere il tempo necessario per assegnare un pacchetto o un altro a tutti gli utenti?"

L'assegnazione di pacchetti a centinaia di utenti è un investimento in termini amministrativi, senza dubbio. Un aspetto importante degli investimenti è che ripagano nel tempo, invece che immediatamente.

In un ambiente didattico sono presenti molti utenti con ruoli uguali o simili. Si spendono meno sforzi nel tempo quando si gestiscono le proprie esperienze utente nello stesso modo. I pacchetti raggruppano un set di criteri specifici per i vari ruoli nell'istituzione. Gli utenti con la stessa licenza, ma con ruoli diversi, possono avere criteri pertinenti assegnati in base al loro ruolo, che è più efficiente rispetto ai criteri di tweaking per singoli utenti.

Una volta che tutti gli utenti dell'Istituto sono stati ordinati in gruppi e i pacchetti sono stati applicati, la loro gestione da allora in poi è una questione di cambiare le impostazioni del pacchetto una sola volta per tutti gli utenti assegnati al pacchetto. Puoi scegliere di ottimizzare i criteri all'interno di un pacchetto prima o dopo l'assegnazione degli utenti al pacchetto.

Vedere [gestire i pacchetti di criteri in Microsoft teams](manage-policy-packages.md) per informazioni dettagliate sull'assegnazione di un pacchetto a singoli utenti, l'assegnazione di pacchetti in blocco a un massimo di 20 utenti e la gestione e l'aggiornamento dei criteri collegati a ogni pacchetto.
