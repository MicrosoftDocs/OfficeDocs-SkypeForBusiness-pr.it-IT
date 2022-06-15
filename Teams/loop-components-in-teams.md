---
title: Panoramica dei componenti di Loop in Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come gestire Loop componenti in Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fb436ef2e8b32f737fcfa10823b54dc0e6a7cca
ms.sourcegitcommit: 07abd8fdb653e57a839ded72620d0179049f25dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "66088582"
---
# <a name="overview-of-loop-components-in-teams"></a>Panoramica dei componenti di Loop in Teams

Loop componenti in Teams chat offrono un nuovo modo per ideare, creare e prendere decisioni insieme. Invia un componente, ad esempio una tabella, un elenco attività o un paragrafo, in cui tutti i membri della chat possono modificare il testo in linea e vedere le modifiche man mano che vengono apportate. 

> [!Note]
> Loop componenti è la prima funzionalità [dell'app Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) disponibile in Teams. 

**Collaborare più velocemente per completare le attività.** Creare un'agenda, tenere traccia delle attività di un gruppo o prendere appunti collettivamente.Crowd-source an agenda, track a group's action items, or take notes collectively. Questi sono solo alcuni scenari semplificati con Loop componenti.

**Condividere i componenti.** In questa versione è possibile condividere Loop componenti in chat di Teams diverse. I destinatari possono modificare ovunque si trovino e visualizzare immediatamente gli aggiornamenti indipendentemente da dove sono state apportate le modifiche.

**Inizia in chat, crea da qui.** Ogni componente creato da Teams chat viene salvato automaticamente in un file in OneDrive. Potresti quindi iniziare a collaborare in chat e poi passare in un secondo momento al file, in cui hai uno spazio visivo più grande per la modifica e puoi aggiungere tutti i componenti che vuoi.

Per informazioni sulle impostazioni amministrative per Loop componenti in Teams, vedere [Gestire Loop componenti in SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Client e piattaforme

Disponibile nelle app Teams su Windows, Mac, Linux, iOS e Android.

## <a name="loop-components-and-fluid-files"></a>Loop componenti e file fluidi

Loop componenti creati in Teams sono supportati da un file .fluid archiviato nella OneDrive del creatore. Essere un file in OneDrive significa che gli utenti possono creare, individuare e gestire Loop componenti (file fluidi) con la facilità di qualsiasi Office documento. 

## <a name="how-are-fluid--files-stored"></a>Come vengono archiviati i file fluidi?

I file fluidi vengono visualizzati in Office.com e OneDrive, ad esempio nelle aree Recenti e Consigliati. Gli utenti possono cercare contenuti nei file fluid da Office.com e OneDrive. I file fluid possono essere ripristinati alle versioni precedenti da OneDrive. Per creare Loop componenti, i partecipanti alla chat devono avere un account OneDrive. Senza un account OneDrive valido, i partecipanti alla chat potrebbero comunque essere in grado di collaborare su un componente creato da altri utenti che hanno un account di OneDrive valido, ma non possono crearne uno personalizzato. 

Se si sposta un file .fluid da OneDrive a un sito di SharePoint, il componente in tempo reale non viene caricato in Teams chat.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>Cosa succede se il proprietario del file lascia la società?

OneDrive criteri di conservazione si applicano ai file fluidi come per gli altri contenuti creati dall'utente.

## <a name="how-are-fluid-files-shared"></a>Come vengono condivisi i file fluidi?

Loop componenti possono essere inseriti in Teams chat o copiati da una chat a un'altra. (Loop componenti non sono ancora supportati nei canali. Per impostazione predefinita, vengono assegnate alle autorizzazioni esistenti dell'organizzazione, ma gli utenti possono modificare le autorizzazioni prima dell'invio per assicurarsi che tutti gli utenti abbiano accesso.

L'apertura di componenti da Teams chat in Office.com offre funzionalità di condivisione nella parte superiore della finestra, in modo simile alle opzioni di condivisione offerte per altri documenti Office.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>Cosa succede se un file .fluid viene danneggiato o danneggiato?

Cronologia versioni consente di rivedere e copiare da versioni precedenti del file.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Quali app possono aprire e modificare file fluid?

I file fluidi possono essere aperti solo come collegamenti nel browser, ad esempio Office.com, e come componenti Loop in Teams chat. Se vengono scaricati, non possono essere riaperti senza prima caricarli di nuovo in OneDrive o SharePoint.

## <a name="does-fluid-files-support-ediscovery"></a>I file .fluid supportano eDiscovery?

I file fluidi sono individuabili, ma hanno un supporto limitato per il flusso di lavoro di eDiscovery. Attualmente, i file .fluid sono archiviati nella OneDrive del creatore e sono disponibili per la ricerca e la raccolta sia in eDiscovery (Standard) che in eDiscovery (Premium). Tuttavia, non viene eseguito il rendering in anteprima e il formato di esportazione per la revisione non è consumabile da strumenti esistenti. Per visualizzare il contenuto esportato, caricarlo in qualsiasi OneDrive. Se lo si desidera, è possibile disabilitare temporaneamente queste esperienze, come descritto nella sezione [Impostazioni gestione](/sharepoint/manage-loop-components#settings-management).

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>Se Loop è disabilitata dall'opzione amministratore, quale sarà l'esperienza utente?

Se si disabilitano queste esperienze come descritto nella sezione [gestione Impostazioni](/sharepoint/manage-loop-components#settings-management), verranno applicate le modifiche seguenti:

- Il punto di ingresso di creazione/inserimento all'interno di Teams messaggistica verrà nascosto. Gli utenti non saranno in grado di creare nuovi file .fluid.
- I messaggi esistenti che in precedenza sarebbero stati visualizzati come componente di Loop interattivo verranno invece visualizzati come collegamento ipertestuale "componente Loop". All'interno di Teams non verrà visualizzato alcun contenuto interattivo.
- Quando un utente finale fa clic sul collegamento ipertestuale "componente Loop" o passa a un file .fluid in OneDrive for Business e fa clic per aprirlo, il file verrà aperto in una scheda del browser separata, ma gli utenti finali non saranno in grado di modificare il file.

## <a name="known-issues"></a>Problemi noti

- Loop componenti in chat non possono essere modificati tramite app Office quando si usa Teams in Android.
- Se le autorizzazioni predefinite per i file tenant sono impostate su *Utenti specifici* (solo le persone specificate dall'utente) e il mittente rimuove alcuni utenti dall'elenco *Utenti specifici* nella finestra di dialogo delle autorizzazioni durante la creazione di un componente, tali utenti potrebbero comunque avere accesso al contenuto.
- Con le autorizzazioni predefinite per i file tenant impostate su *Utenti specifici* (solo le persone specificate dall'utente), per copiare il collegamento al componente in tempo reale e incollare in un'altra chat è necessario che il mittente usi la finestra di dialogo delle autorizzazioni e aggiungi i destinatari nell'opzione Persone specifiche per concedere correttamente l'accesso.
- Con le autorizzazioni predefinite per i file tenant impostate su *Utenti specifici* (solo le persone specificate dall'utente), la creazione di un componente live in Group Chat con più di 20 membri richiederà al mittente di selezionare manualmente le opzioni di autorizzazione per il componente.
- La ricerca di componenti Loop in Teams ricerca restituirà un collegamento al componente in office.com, non il messaggio di chat stesso.
- Loop componenti sono disabilitati nelle chat federate.
- I guest B2B non saranno in grado di collaborare su un componente in tempo reale condiviso con loro tramite Company Share Link. Impostare le autorizzazioni su **Persone attualmente presenti in questa chat** per condividere i componenti con i guest B2B.
- Loop componenti non sono supportati nei canali Teams.
- Loop componenti in chat non verranno caricati solo se il file è stato spostato in un'altra raccolta. Se il file viene spostato in un'altra cartella, continuerà a essere caricato in chat.
