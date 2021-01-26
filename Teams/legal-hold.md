---
title: Inserire un utente o un team di Microsoft teams in blocco legale
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: Imparerai a inserire un utente o un team di Microsoft teams in blocco legale usando il centro conformità & sicurezza e scopri cosa richiede un blocco legale in base ai requisiti dei dati.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c04f3584aa7207d9d9ee1126df992657f84aa213
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980450"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Inserire un utente o un team di Microsoft teams in blocco legale
==================================================

Quando esiste una ragionevole aspettativa di controversia, le organizzazioni sono tenute a conservare le informazioni archiviate elettronicamente (ESI), inclusi i messaggi di chat in team che sono rilevanti per il caso. Le organizzazioni possono essere necessarie per mantenere tutti i messaggi correlati a un argomento specifico o a determinati utenti. Questo articolo riguarderà il blocco legale in Microsoft Teams (per indirizzare l'implementazione di blocco nello spazio M365, vedere [gestire i casi di eDiscovery: posizionare i percorsi di contenuto in attesa](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)).

> [!NOTE]
> Nel 2020 febbraio abbiamo abilitato il blocco legale o il blocco dei casi su canali privati (le chat di canale privato sono archiviate nelle cassette postali degli utenti, le chat di canale normali sono archiviate nella cassetta postale del gruppo del team). Se esiste già un blocco legale per una cassetta postale dell'utente, il criterio di blocco verrà applicato automaticamente ai messaggi del canale privato archiviati nella cassetta postale. Non è necessaria alcuna ulteriore azione per attivare l'amministratore. È supportato anche il blocco legale dei file condivisi nei canali privati.

All'interno di Microsoft teams, un intero team o gli utenti selezionati possono essere messi in attesa o in attesa legale. In questo modo si verificherà che tutti i messaggi scambiati in questi team (inclusi i canali privati) o i messaggi scambiati da tali utenti siano individuabili dai responsabili della conformità dell'organizzazione o dagli amministratori di teams.

> [!NOTE]
> L'immissione di un utente in blocco non inserisce automaticamente un gruppo in attesa o viceversa.

Per inserire un utente o un team in attesa legale:

1. Passare al [centro conformità & sicurezza](https://go.microsoft.com/fwlink/?linkid=854628). Quando si crea un nuovo caso, viene visualizzata l'opzione per posizionare le cassette postali o i siti in attesa.

2. Accedere a eDiscovery o Advanced eDiscovery e creare un caso facendo clic su "crea un caso". Una volta creato il caso, aprirlo.

   > [!div class="mx-imgBorder"]
   > ![È selezionata la scheda Microsoft teams eDiscovery, che mostra il pulsante Crea un caso.](media/LegalHold1.png)

3. Passa alla sezione "detiene" dal menu superiore e fai clic su "+ Crea" per creare un blocco. La messa in attesa di un utente o di un team consente di salvare tutti i messaggi scambiati da tali utenti o messaggi. Quando si crea un nuovo caso, viene visualizzata l'opzione per posizionare le cassette postali o i siti in attesa.

   > [!div class="mx-imgBorder"]
   > ![Immagine che mostra la scheda detiene selezionata e il pulsante Crea sotto.](media/LegalHold2.png)

   1. **Assegnare un nome al blocco**. Selezionare un nome descrittivo e univoco per il blocco che si vuole creare.

      > [!div class="mx-imgBorder"]
      > ![Questa schermata mostra il nome della scheda blocco, in cui è possibile immettere un nome e una descrizione per il blocco da creare.](media/LegalHold3.png)

    2. **Scegliere posizione**. Scegliere se si vuole che il blocco venga applicato a un utente o a un intero team (il blocco non può essere applicato ai singoli canali per ora). Nota: se un utente è in attesa, tutti i loro messaggi rimarranno in attesa, incluso quello inviato in una chat di 1:1, 1: molti o chat di gruppo o una conversazione di canale (inclusi i canali privati).
  
       > [!div class="mx-imgBorder"]
       > ![Di seguito è disponibile la sezione scegliere percorsi per creare un nuovo blocco, in cui è possibile prendere decisioni sulle opzioni di M365, tra cui Microsoft teams, a cui si desidera applicare il blocco.](media/LegalHold4.png)

    3. **Crea query**. È possibile personalizzare il blocco se si vuole maggiore granularità nel criterio di blocco. Ad esempio, puoi specificare le parole chiave da cercare oppure aggiungere altre condizioni che devono essere soddisfatte perché l'esenzione abbia effetto.
    
    4. **Esaminare le impostazioni** prima di pubblicarle nell'organizzazione.

Dopo aver impostato il blocco legale, è possibile scoprire tutto il contenuto mantenuto da qualsiasi criterio di blocco dopo l'articolo [eDiscovery teams](eDiscovery-investigation.md) .

> [!IMPORTANT]
> Quando un utente o un gruppo viene messo in attesa, verranno mantenute tutte le copie del messaggio. Ad esempio, se un utente ha inviato un messaggio in un canale e quindi ha modificato il messaggio, in uno scenario di blocco vengono mantenute entrambe le copie del messaggio. Senza il blocco legale sul posto, viene mantenuto solo il messaggio più recente.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Percorsi di contenuto da posizionare in blocco legale per conservare il contenuto di Teams

Come guida utile, è possibile usare la tabella seguente per comprendere la posizione del contenuto, ad esempio una cassetta postale o un sito, da inserire in blocco legale per mantenere i diversi tipi di contenuto del team.

|Scenario  |Posizione del contenuto  |
|---------|---------|
|Chat Team per un utente (ad esempio, chat di 1:1, 1: N chat di gruppo e conversazioni con canali privati)     |Cassetta postale dell'utente.         |
|Chat Channel in teams (esclusi i canali privati)    |Cassetta postale del gruppo usata per il team.         |
|Contenuto del file Teams (ad esempio, contenuto e file wiki)     |Sito di SharePoint usato dal team.         |
|File di canale privato Teams     |Sito di SharePoint dedicato per canali privati.     |
|Contenuto privato dell'utente     |Account di OneDrive for business dell'utente.         |
|Contenuto della scheda nelle chat|Cassetta postale dell'utente per le chat di 1:1, 1: N chat di gruppo e conversazioni di canale private o cassetta postale di gruppo per il contenuto della scheda nei messaggi di canale. Per altre informazioni, vedere la sezione "Mantieni contenuto della scheda" in [creare un blocco di eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).
||||

> [!NOTE]
> Per mantenere le comunicazioni nei canali privati, è necessario inserire le cassette postali utente (utenti del canale privato) in attesa e quando si usa lo strumento eDiscovery per eseguire una ricerca, è necessario eseguire una ricerca nella cassetta postale dell'utente. Come indicato in precedenza, le chat di canale private sono archiviate nelle cassette postali degli utenti e non nella cassetta postale del gruppo di un team.

Per altre informazioni su questo argomento per le aree non teams in Microsoft 365, vedere gestire i casi di [eDiscovery: posizionare i percorsi di contenuto in blocco](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).
