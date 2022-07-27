---
title: Risolvere i problemi di Career Coach per Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come risolvere i problemi comuni in Assistente alla carriera per Microsoft Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5ebda4324f7cc46d69b882a53684b21b4fa2932
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024171"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>Risolvere i problemi di Career Coach per Microsoft Teams

Questo articolo è rivolto agli amministratori IT dell'istruzione superiore che devono risolvere i problemi di Assistente alla carriera per Microsoft Teams.

Di seguito sono riportati i problemi comuni e i passaggi di risoluzione che gli amministratori IT possono eseguire con Career Coach.

## <a name="missing-required-configuration-data"></a>Dati di configurazione obbligatori mancanti

Se vedi "Assistente alla carriera è in fase di configurazione per l'uso futuro" nell'esperienza Assistente alla carriera, **non sono stati aggiunti tutti i dati di configurazione necessari**.

Le **sezioni seguenti devono essere completate** prima di poter utilizzare Assistente alla carriera:

- [Marchio e preferenze](career-coach-set-up-steps.md#brand-and-preferences)
- [Connessione LinkedIn](career-coach-set-up-steps.md#linkedin-connection)
- [Catalogo dei corsi](career-coach-set-up-steps.md#course-catalog)
- [Campi di studio](career-coach-set-up-steps.md#fields-of-study)

Fare riferimento allo [stato di configurazione di Assistente alla carriera](career-coach-set-up-steps.md#configuration-status) per vedere quali impostazioni devono essere completate.

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>Formattazione non corretta del catalogo del corso o dei campi dei dati di studio

I CSV per il catalogo dei corsi e il campo di studio hanno formati obbligatori e una dimensione massima di 18 MB.

Fare riferimento allo [schema dei documenti del catalogo dei corsi](career-coach-set-up-steps.md#course-catalog-document-format-and-schema) di Assistente alla carriera e ai campi assistente alla carriera [dello schema del documento di studio](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) per garantire una configurazione corretta.

Inoltre, un file di catalogo del corso non deve avere più di 15.000 righe per garantire una corretta elaborazione.

## <a name="missing-fields-in-career-coach-settings-pages"></a>Campi mancanti nelle pagine delle impostazioni di Assistente alla carriera

Le pagine delle impostazioni di Assistente alla carriera hanno campi obbligatori. Se i campi necessari non sono completati, la pagina non verrà invii.

È possibile che non venga visualizzato un messaggio di avviso e che la pagina non venga inviato.

L'invio ha esito positivo quando viene visualizzato un banner verde nella parte superiore della pagina.

## <a name="setup-policy-changes-arent-complete"></a>Le modifiche ai criteri di installazione non sono complete

Se Assistente alla carriera non viene visualizzato in Microsoft Teams per gli utenti, le modifiche ai criteri di configurazione potrebbero non essere ancora applicate. Career Coach non verrà installato e aggiunto per gli utenti in Microsoft Teams finché i criteri di configurazione non saranno applicati. L'applicazione delle modifiche ai criteri può richiedere alcune ore.

Tuttavia, Assistente alla carriera può essere installato direttamente dall'app store di Microsoft Teams.

- Se gli utenti non riescono a trovare Assistente alla carriera nell'app Store di Microsoft Teams, esamina i criteri di autorizzazione delle app e assicurati che Assistente alla carriera non sia un'app bloccata.
- Career Coach è un'app Microsoft ed è consigliabile consentire le app Microsoft in base ai criteri di autorizzazione. Altre informazioni sulla [configurazione dei criteri di autorizzazione](teams-app-permission-policies.md).

## <a name="career-coach-initialization-isnt-complete"></a>L'inizializzazione di Assistente alla carriera non è completa

Potrebbe essere visualizzato l'errore seguente: "Non è possibile recuperare le impostazioni dell'app. Riprovare. Se continui ad avere problemi, contatta il supporto tecnico Microsoft".

Controlla **lo stato di provisioning dei servizi** nella [pagina delle impostazioni di Assistente alla carriera](career-coach-set-up-steps.md#career-coach-settings-status).

Se il tenant è ancora in fase di inizializzazione, attendere 15 minuti e riprovare. Apri un ticket di supporto se continui a ricevere l'errore.
