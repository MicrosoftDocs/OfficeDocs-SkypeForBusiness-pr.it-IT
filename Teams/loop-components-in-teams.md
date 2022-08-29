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
description: Informazioni su come gestire i componenti loop in Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e468622d4aac30756e54127072045831374c5425
ms.sourcegitcommit: 0592f9d2696fe8c840a4ed3e7f99e55ca0c9c3e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "67418645"
---
# <a name="overview-of-loop-components-in-teams"></a>Panoramica dei componenti loop in Teams

I componenti loop nella chat di Teams offrono un nuovo modo per ideare, creare e prendere decisioni insieme. Invia un componente, ad esempio una tabella, un elenco attività o un paragrafo, in cui tutti i membri della chat possono modificare il testo in linea e vedere le modifiche man mano che vengono apportate. 

> [!Note]
> I componenti a ciclo continuo sono la prima funzionalità [dell'app Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) a diventare disponibili in Teams. 

**Collaborare più velocemente per completare le attività.** Creare un'agenda, tenere traccia delle attività di un gruppo o prendere appunti collettivamente.Crowd-source an agenda, track a group's action items, or take notes collectively. Questi sono solo alcuni scenari semplificati con i componenti loop.

**Condividere i componenti.** In questa versione, è possibile condividere i componenti loop in chat di Teams diverse. I destinatari possono modificare ovunque si trovino e visualizzare immediatamente gli aggiornamenti indipendentemente da dove sono state apportate le modifiche.

**Inizia in chat, crea da qui.** Ogni componente creato dalla chat di Teams viene salvato automaticamente in un file in OneDrive. Potresti quindi iniziare a collaborare in chat e poi passare in seguito al file su Office.com, dove hai uno spazio visivo più grande per la modifica e puoi aggiungere tutti i componenti che vuoi.

Per informazioni sulle impostazioni di amministrazione per i componenti Loop in Teams, vedere [Gestire i componenti loop in SharePoint](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>Client e piattaforme

Disponibile nelle app Teams su Windows, Mac, Linux, iOS e Android.

## <a name="loop-components-and-fluid-files"></a>Componenti a ciclo continuo e file fluidi

I componenti di ciclo creati in Teams sono supportati da un file .fluid (che verrà modificato in .loop nel prossimo futuro) archiviato nel OneDrive del creatore. Se si tratta di un file in OneDrive, gli utenti possono creare, individuare e gestire i componenti Loop (file fluidi) con la facilità di qualsiasi documento di Office. 

## <a name="how-are-fluid-files-stored"></a>Come vengono archiviati i file fluidi?

I file fluidi vengono visualizzati in Office.com e OneDrive, ad esempio nelle aree Recenti e Consigliate. Gli utenti possono cercare contenuti nei file fluidi da Office.com e OneDrive. È possibile ripristinare le versioni precedenti dei file fluidi da OneDrive. Per creare loop components, i partecipanti alla chat devono avere un account OneDrive. Senza un account OneDrive valido, i partecipanti alla chat potrebbero comunque essere in grado di collaborare a un componente creato da altri utenti che hanno un account di OneDrive valido, ma non possono crearne uno personalizzato. 

Se si sposta un file .fluid da OneDrive a un sito di SharePoint, il componente in tempo reale non viene caricato nella chat di Teams.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>Cosa succede se il proprietario del file lascia la società?

I criteri di conservazione di OneDrive si applicano ai file fluidi come per gli altri contenuti creati dall'utente.

## <a name="how-are-fluid-files-shared"></a>Come vengono condivisi i file fluidi?

I componenti di ciclo possono essere inseriti nella chat di Teams o copiati da una chat a un'altra. I componenti di ciclo non sono ancora supportati nei canali. Per impostazione predefinita, vengono assegnate alle autorizzazioni esistenti dell'organizzazione, ma gli utenti possono modificare le autorizzazioni prima dell'invio per assicurarsi che tutti gli utenti abbiano accesso.

L'apertura di componenti dalla chat di Teams in Office.com offre funzionalità di condivisione nella parte superiore della finestra, in modo simile alle opzioni di condivisione offerte per altri documenti di Office.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>Cosa succede se un file .fluid viene danneggiato o danneggiato?

Cronologia versioni consente di rivedere, ripristinare o copiare da versioni precedenti del file.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>Quali app possono aprire e modificare file fluid?

I file fluidi possono essere aperti solo come collegamenti nel browser, ad esempio Office.com e come componenti loop nella chat di Teams. Se vengono scaricati, non possono essere riaperti senza prima caricarli di nuovo in OneDrive o SharePoint.

## <a name="does-fluid-files-support-ediscovery"></a>I file .fluid supportano eDiscovery?

I file fluidi sono individuabili, ma hanno un supporto limitato per il flusso di lavoro di eDiscovery. Attualmente, i file .fluid sono archiviati in OneDrive del creatore e sono disponibili per la ricerca e la raccolta sia in eDiscovery (Standard) che in eDiscovery (Premium). Tuttavia, non viene eseguito il rendering in anteprima e il formato di esportazione per la revisione non è consumabile da strumenti esistenti. Per visualizzare il contenuto esportato, caricarlo in onedrive. Se lo desideri, puoi disabilitare temporaneamente queste esperienze, come descritto nella sezione [Gestione delle impostazioni](/sharepoint/manage-loop-components#settings-management) .

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>Se Loop è disabilitato dall'opzione di amministrazione, quale sarà l'esperienza utente?

Se si disabilitano queste esperienze come descritto nella sezione [Gestione delle impostazioni](/sharepoint/manage-loop-components#settings-management) , verranno applicate le modifiche seguenti:

- Il punto di ingresso di creazione/inserimento all'interno della messaggistica di Teams verrà nascosto. Gli utenti non saranno in grado di creare nuovi file .fluid.
- I messaggi esistenti che in precedenza sarebbero stati sottoposti a rendering come componente loop interattivo verranno invece visualizzati come collegamento ipertestuale "Componente ciclo". All'interno di Teams non verrà visualizzato alcun contenuto interattivo.
- Quando un utente finale fa clic sul collegamento ipertestuale "Loop component" o passa a un file .fluid in OneDrive for Business e fa clic per aprirlo, il file verrà aperto in una scheda del browser separata, ma gli utenti finali non saranno in grado di modificare il file.

## <a name="known-issues"></a>Problemi noti

- Con le autorizzazioni predefinite per i file tenant impostate su *Utenti specifici* (solo le persone specificate dall'utente), copiare il collegamento al componente Ciclo e incollarlo in un'altra chat richiede al mittente di usare la finestra di dialogo delle autorizzazioni e aggiungere i destinatari nell'opzione Persone specifiche per concedere correttamente l'accesso.
- Con le autorizzazioni predefinite per i file tenant impostate su *Utenti specifici* (solo le persone specificate dall'utente), la creazione di un componente live in Group Chat con più di 20 membri richiederà al mittente di selezionare manualmente le opzioni di autorizzazione per il componente.
- La ricerca di componenti Loop nella ricerca di Teams restituirà un collegamento al componente in office.com, non al messaggio di chat stesso.
- I componenti del ciclo sono disabilitati nelle chat federate.
- I guest non saranno in grado di collaborare su un componente in tempo reale condiviso con loro tramite il collegamento di condivisione aziendale. Impostare le autorizzazioni per **Persone attualmente in questa chat** per condividere i componenti con i guest.
- I componenti a ciclo continuo non sono supportati nei canali di Teams.
- I componenti a ciclo continuo nella chat non verranno caricati solo se il file è stato spostato in un'altra libreria. Se il file viene spostato in un'altra cartella, continuerà a essere caricato in chat.
