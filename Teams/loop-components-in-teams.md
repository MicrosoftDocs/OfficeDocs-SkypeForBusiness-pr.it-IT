---
title: Panoramica dei componenti loop in Teams
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
description: Informazioni su come gestire i componenti Loop in Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a43ea4c217e09ad4473513fd21e159bd15c89716
ms.sourcegitcommit: fd4d7557997c537c094e79ada21c569acde65aa6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2022
ms.locfileid: "62312448"
---
# <a name="overview-of-loop-components-in-teams"></a>Panoramica dei componenti loop in Teams

I componenti a ciclo continuo Teams chat offrono un nuovo modo per ideare, creare e prendere decisioni insieme. Inviare un componente, ad esempio una tabella, un elenco attività o un paragrafo, in cui tutti gli utenti della chat possono modificare le modifiche in linea e vedere le modifiche non appena vengono apportate. 

> [!Note]
> I componenti loop sono la prima funzionalità [dell'app Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) a essere disponibile in Teams. 

**È possibile eseguire più velocemente le attività insieme.** È possibile creare un'agenda, tenere traccia delle attività di un gruppo o prendere appunti collettivamente. Questi sono solo alcuni scenari semplificati con i componenti Loop.

**Condividere componenti.** In questa versione è possibile condividere i componenti loop in chat Teams chat. I destinatari possono modificare da qualsiasi posizione e visualizzare immediatamente gli aggiornamenti, indipendentemente da dove sono state apportate le modifiche.

**Inizia in chat, crea da lì.** Ogni componente creato da Teams chat viene salvato automaticamente in un file in OneDrive. Quindi, potresti iniziare a collaborare in chat e poi passare al file, dove hai uno spazio visivo più ampio per la modifica e puoi aggiungere tutti i componenti che vuoi.

## <a name="clients-and-platforms"></a>Client e piattaforme

Disponibile nelle app Teams su Windows, Mac, Linux, iOS e Android.

## <a name="loop-components-and-fluid-files"></a>Componenti a ciclo continuo e file fluidi

I componenti a ciclo continuo creati in Teams sono supportati da un file fluido archiviato nella cartella OneDrive. Essere un file in OneDrive significa che gli utenti possono creare, individuare e gestire i componenti Loop (file con estensione fluido) con la Office documento. I file fluidi funzionano con le caratteristiche di governance dei dati come eDiscovery, controllo, creazione di report e blocco legale.

## <a name="how-are-fluid--files-stored"></a>Come vengono archiviati i file CON ESTENSIONE FLUID?

I file fluidi vengono visualizzati in Office.com e OneDrive, ad esempio nelle aree Recenti e Consigliate. Gli utenti possono cercare contenuti nei file con estensione fluid da Office.com e OneDrive. I file FLUID possono essere ripristinati alle versioni precedenti da OneDrive. Per creare componenti loop, i partecipanti alla chat devono avere un account OneDrive utente. Senza un account OneDrive valido, i partecipanti alla chat potrebbero comunque essere in grado di collaborare a un componente creato da altri utenti che hanno un account OneDrive valido, ma non possono crearne uno personalizzato. 

Se si sposta un file fluido da OneDrive a un sito SharePoint, il componente in tempo reale non viene caricato Teams chat.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>Cosa succede se il proprietario del file lascia la società?

OneDrive criteri di conservazione si applicano ai file FLUID come ad altri contenuti creati dall'utente.

## <a name="how-are-fluid-files-shared"></a>Come vengono condivisi i file FLUID?

I componenti a ciclo continuo possono essere inseriti Teams chat o copiati da una chat a un'altra. I componenti a ciclo continuo non sono ancora supportati nei canali. Per impostazione predefinita, vengono assegnate alle autorizzazioni esistenti dell'organizzazione, ma gli utenti possono modificare le autorizzazioni prima dell'invio per assicurarsi che tutti gli utenti possano accedervi.

L'apertura di componenti Teams chat in Office.com offre funzionalità di condivisione nella parte superiore della finestra, in modo analogo alle opzioni di condivisione offerte per altri documenti Office documenti.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>Cosa succede se un file fluido viene danneggiato o danneggiato?

Cronologia versioni consente di rivedere e copiare da versioni precedenti del file.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Quali app possono aprire e modificare i file CON ESTENSIONE FLUID?

I file con estensione fluid possono essere aperti solo come collegamenti nel browser, ad esempio Office.com, e come componenti Loop in Teams chat. Se vengono scaricati, non possono essere riaperti senza prima caricarli di nuovo in OneDrive o SharePoint.

## <a name="known-issues"></a>Problemi noti

- I componenti a ciclo continuo nella chat non possono essere modificati tramite app Office quando si usa Teams su Android.
- Se le autorizzazioni predefinite per i file del tenant sono impostate su Persone *specifiche (solo* le persone specificate dall'utente) e il mittente rimuove  alcuni utenti dall'elenco Persone specifiche nella finestra di dialogo delle autorizzazioni durante la creazione di un componente, questi utenti potrebbero comunque avere accesso al contenuto.
- Con le autorizzazioni per i file predefinite del tenant impostate su Persone *specifiche (solo* le persone specificate dall'utente), copiare il collegamento al componente live e incollarli in un'altra chat richiede al mittente di usare la finestra di dialogo autorizzazioni e aggiungere i destinatari nell'opzione Persone specifiche per concedere correttamente l'accesso.
- Con le autorizzazioni predefinite per i file del tenant impostate su Persone *specifiche (solo* le persone specificate dall'utente), la creazione di un componente live nella chat di gruppo con più di 20 membri richiederà al mittente di selezionare manualmente le opzioni di autorizzazione per il componente.
- La ricerca di componenti Loop Teams ricerca restituirà un collegamento al componente in office.com, non al messaggio di chat stesso.
- I componenti a ciclo continuo vengono disabilitati nelle chat federate.
- I guest B2B non potranno collaborare a un componente live condiviso con loro tramite i collegamenti Persone nell'organizzazione, a meno che il tenant non imposta un'opzione di accesso esterno per consentire ai guest B2B di avere lo stesso livello di accesso dei membri del tenant. Per altre informazioni, vedere [Configurare le impostazioni di collaborazione esterna B2B](/azure/active-directory/external-identities/delegate-invitations#configure-b2b-external-collaboration-settings).
- I componenti a ciclo continuo non sono supportati Teams canali.
- I componenti a ciclo continuo nella chat non vengono caricati solo se il file è stato spostato in una raccolta diversa. Se il file viene spostato in un'altra cartella, continuerà a essere caricato in chat.
