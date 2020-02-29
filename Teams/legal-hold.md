---
title: Inserire un utente o un team di Microsoft teams in blocco legale
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Imparerai a inserire un utente o un team di Microsoft teams in blocco legale usando il centro conformità & sicurezza e scopri cosa richiede un blocco legale in base ai requisiti dei dati.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3727ac3f6b9ded4c3dbb34a1977f9b99cbaf15e
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341634"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Inserire un utente o un team di Microsoft teams in blocco legale
==================================================

Quando esiste una ragionevole aspettativa di controversia, le organizzazioni sono tenute a conservare le informazioni archiviate elettronicamente (ESI), inclusi i messaggi di chat in team che sono rilevanti per il caso. Le organizzazioni possono essere necessarie per mantenere tutti i messaggi correlati a un argomento specifico o a determinati utenti. Questo articolo riguarderà il blocco legale in Microsoft Teams (per indirizzare l'implementazione di blocco nello spazio M365, vedere [gestire i casi di eDiscovery: posizionare i percorsi di contenuto in attesa](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)).

> [!NOTE]
> In 2020 febbraio è stato attivato un blocco legale o un blocco di casi su canali privati (le chat di canale privato sono archiviate nelle cassette postali degli utenti, le chat di canale normale sono archiviate nelle cassette postali del gruppo dei team). Se esiste già un blocco legale per una cassetta postale dell'utente, il criterio di blocco verrà applicato automaticamente ai messaggi del canale privato archiviati nella cassetta postale. Non è necessaria alcuna ulteriore azione per attivare l'amministratore. È supportato anche il blocco legale dei file condivisi nei canali privati.

All'interno di Microsoft teams, un intero team o gli utenti selezionati possono essere messi in attesa o in attesa legale. In questo modo si verificherà che tutti i messaggi scambiati in questi team (inclusi i canali privati) o i messaggi scambiati da tali utenti siano individuabili dai responsabili della conformità dell'organizzazione o dagli amministratori di teams.

> [!NOTE]
> L'immissione di un utente in blocco non inserisce automaticamente un gruppo in attesa o viceversa.

Per inserire un utente o un team in attesa legale:

1. Passare al [centro conformità & sicurezza](https://go.microsoft.com/fwlink/?linkid=854628). Quando si crea un nuovo caso, viene visualizzata l'opzione per posizionare le cassette postali o i siti in attesa.
1. Accedere a eDiscovery o Advanced eDiscovery e creare un caso facendo clic su "+ crea un caso". Una volta creato il caso, aprirlo.
![È selezionata la scheda Microsoft teams eDiscovery, che mostra il pulsante Crea un caso.](media/LegalHold1.png)
1. Vai alla sezione "detiene" dal menu in alto e fai clic su "+ Crea" per creare un blocco per l'inserimento di un utente o di un team in blocco salva tutti i messaggi scambiati da tali utenti o messaggi quando crei un nuovo caso, ti viene presentato l'opzione per posizionare le cassette postali o i siti in attesa.
![Immagine che mostra la scheda detiene selezionata e il pulsante Crea sotto.](media/LegalHold2.png)
    1. **Assegnare un nome al blocco**. Selezionare un nome descrittivo e univoco per il blocco che si vuole creare.
![Questa schermata mostra il nome della scheda blocco, in cui è possibile immettere un nome e una descrizione per il blocco da creare.](media/LegalHold3.png)
    1. **Scegliere posizione**. Scegliere se si vuole che il blocco venga applicato a un utente o a un intero team (il blocco non può essere applicato ai singoli canali per ora). Nota: se un utente è in attesa, tutti i loro messaggi rimarranno in attesa, incluso quello inviato in una chat di 1:1, 1: molti o chat di gruppo o una conversazione di canale (inclusi i canali privati).
    ![Di seguito è disponibile la sezione scegliere percorsi per creare un nuovo blocco, in cui è possibile prendere decisioni sulle opzioni di M365, tra cui Microsoft teams, a cui si desidera applicare il blocco.](media/LegalHold4.png)
    1. **Crea query**. È possibile personalizzare il blocco se si vuole maggiore granularità nel criterio di blocco. Ad esempio, puoi specificare le parole chiave da cercare oppure aggiungere altre condizioni che devono essere soddisfatte perché l'esenzione abbia effetto.
    1. **Esaminare le impostazioni** prima di pubblicarle nell'organizzazione.

Dopo aver impostato il blocco legale, è possibile scoprire tutto il contenuto mantenuto da qualsiasi criterio di blocco dopo l'articolo [eDiscovery teams](eDiscovery-investigation.md) .

> [!IMPORTANT]
> Quando un utente o un gruppo viene messo in attesa, verranno mantenute tutte le copie del messaggio. Ad esempio, se un utente ha inviato un messaggio in un canale e quindi ha modificato il messaggio, in uno scenario di blocco vengono mantenute entrambe le copie del messaggio. Senza il blocco legale sul posto, viene mantenuto solo il messaggio più recente.

Come guida utile, è possibile usare la tabella seguente per capire cosa occorre inserire in blocco legale in base ai requisiti dei dati:

|Scenario  |Cosa posizionare in blocco  |
|---------|---------|
|**Contenuto della chat di Microsoft Teams da un utente (in chat di 1:1, 1: molti o chat di gruppo, conversazioni con canali privati e così via)**     |Cassetta postale dell'utente         |
|**Chat di canale di Microsoft Teams (esclusi i canali privati)**    |Cassetta postale del gruppo usata per il team         |
|**Contenuto di Microsoft Teams (ad esempio wiki, file)**     |Sito di SharePoint usato dal team         |
|**File di canale privato di Microsoft Teams**     |Sito di SharePoint canale privato dedicato     |
|**Contenuto privato dell'utente**     |Sito di OneDrive for business dell'utente         |

> [!NOTE]
> Per mantenere le comunicazioni nei canali privati, è necessario inserire le cassette postali utente (utenti del canale privato) in attesa e quando si usa lo strumento eDiscovery per eseguire una ricerca, è necessario eseguire una ricerca nella cassetta postale dell'utente. Come indicato in precedenza, le chat di canale private sono archiviate nelle cassette postali degli utenti e non nella cassetta postale del gruppo di un team.

Per altre informazioni su questo argomento per le aree non teams in M365, vedere gestire i casi di [eDiscovery: posizionare i percorsi di contenuto in blocco](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).
