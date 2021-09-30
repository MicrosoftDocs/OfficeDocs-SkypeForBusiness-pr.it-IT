---
title: Applicazione di un blocco legale Microsoft Teams un utente o un team
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
description: Informazioni su come impostare un blocco legale Microsoft Teams un utente o un team tramite il Centro sicurezza & conformità e scoprire cosa richiede un blocco legale in base ai requisiti di dati.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ace4098b56539408e8c29e5d16e43c8ae255f372
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013350"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Applicazione di un blocco legale Microsoft Teams un utente o un team

Quando esiste una ragionevole aspettativa di controversie legali, le organizzazioni devono conservare le informazioni archiviate elettronicamente (ESI), inclusi Teams messaggi di chat rilevanti per il caso. Le organizzazioni potrebbero dover conservare tutti i messaggi relativi a un argomento specifico o a determinati utenti. Questo articolo illustra il blocco legale in Microsoft Teams. Per mantenere il contenuto in Microsoft 365, vedere [Creare un blocco di eDiscovery.](/microsoft-365/compliance/create-ediscovery-holds)

> [!NOTE]
> A febbraio 2020 è stato attivato il blocco legale per i canali privati. Le chat di canale privato vengono archiviate nelle cassette postali degli utenti, mentre le chat dei canali normali vengono archiviate nella cassetta postale Teams di gruppo. Se esiste già un blocco legale per una cassetta postale utente, il criterio di blocco verrà applicato automaticamente ai messaggi del canale privato archiviati nella cassetta postale. Non sono necessarie altre azioni per l'attivazione di questa opzione da parte di un amministratore. È supportato anche il blocco legale dei file condivisi nei canali privati.

All'Microsoft Teams, un intero team o utenti selezionati può essere sospeso per motivi legali. In questo modo si assicura che tutti i messaggi s scambiati in questi team (inclusi i canali privati) o i messaggi s scambio da tali utenti siano individuabili dai responsabili della conformità dell'organizzazione o dagli amministratori Teams aziendali.

> [!NOTE]
> L'applicazione di un blocco a un utente non comporta automaticamente il blocco di un gruppo o viceversa.
> Le notifiche inviate nel feed attività non possono essere poste in blocco.

Per impostare un blocco legale per un utente o un team in un caso di eDiscovery di base:

1. Passare al [Centro conformità Microsoft 365](https://compliance.microsoft.com). Quando si crea un nuovo caso, viene visualizzata l'opzione per mettere in blocco cassette postali o siti.

2. Passare a **eDiscovery**  >  **Core** e creare un caso facendo clic **su Crea un caso.** Dopo aver creato il caso, aprirlo.
  
   ![Microsoft Teams scheda eDiscovery selezionata, con il pulsante Crea un caso.](media/LegalHold1.png)

   > [!NOTE]
   > È anche possibile inserire un utente in un blocco associato a un Advanced eDiscovery caso. Per altre informazioni, vedere [Gestire i blocchi in Advanced eDiscovery](/microsoft-365/compliance/managing-holds).

3. Passare alla scheda **Blocchi** nel menu superiore e fare clic **su Crea** per creare un blocco. L'applicazione di un blocco a un utente o a un team mantiene tutti i messaggi s scambiati da tali utenti o messaggi. Quando si crea un nuovo caso, viene visualizzata l'opzione per mettere in blocco cassette postali o siti.

   ![Immagine che mostra la scheda Blocchi selezionata e il pulsante Crea sotto.](media/LegalHold2.png)
    
    1. **Assegnare un nome al blocco**. Selezionare un nome descrittivo e univoco per il blocco che si sta per creare.
  
       ![Questa schermata mostra la scheda Assegnare un nome al blocco, in cui è possibile immettere un nome e una descrizione per il blocco che si sta creando.](media/LegalHold3.png)

    1. **Scegliere la posizione**. Scegliere se applicare il blocco a un utente o a un intero team (il blocco non può essere applicato ai singoli canali per il momento). Nota: se un utente è in stato di blocco, tutti i messaggi sono in attesa, incluso quello che ha inviato in una chat 1:1, in una chat 1:1 o in una chat di gruppo o in una conversazione di canale (inclusi i canali privati).
    ![Ecco la sezione Scegliere le posizioni di Crea un nuovo blocco, in cui è possibile prendere decisioni sulle opzioni M365, tra cui Microsoft Teams, a cui si vuole applicare il blocco.](media/LegalHold4.png)

    2. **Creare una query**. È possibile personalizzare il blocco se si vuole una maggiore granularità nei criteri di blocco. Ad esempio, è possibile specificare parole chiave da cercare oppure aggiungere altre condizioni che dovranno essere soddisfatte per l'applicazione del blocco.
    
    3. **Rivedere le impostazioni prima** di creare il blocco.

Dopo aver creato il blocco legale, è possibile eseguire ricerche nel contenuto conservato da qualsiasi criterio di blocco. Per altre informazioni, vedere [Condurre un'indagine eDiscovery in Teams](eDiscovery-investigation.md).

> [!IMPORTANT]
> Quando un utente o un gruppo viene sospeso, tutte le copie dei messaggi verranno conservate. Ad esempio, se un utente ha pubblicato un messaggio in un canale e quindi lo ha modificato, in uno scenario di blocco vengono mantenute entrambe le copie del messaggio. Senza il blocco legale sul posto, viene mantenuto solo il messaggio più recente.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Percorsi di contenuto da inserire in blocco legale per mantenere Teams contenuto

Come guida utile, è possibile usare la tabella seguente per comprendere quale percorso di contenuto, ad esempio una cassetta postale o un sito, inserire in blocco legale per mantenere i diversi tipi di contenuto Teams contenuto.

|Scenario  |Percorso del contenuto  |
|---------|---------|
|Teams chat per un utente (ad esempio, chat 1:1, chat di gruppo 1:N e conversazioni di canale privato)     |Cassetta postale utente.         |
|Teams chat del canale (esclusi i canali privati)    |Cassetta postale del gruppo usata per il team.         |
|Teams contenuto del file (ad esempio, contenuto wiki e file)     |SharePoint sito usato dal team.         |
|Teams dei canali privati     |Sito SharePoint dedicato per canali privati.     |
|Contenuto privato dell'utente     |L'account OneDrive for Business dell'utente.         |
|Contenuto della scheda nelle chat|Cassetta postale utente per chat 1:1, chat di gruppo 1:N e conversazioni di canali privati o cassetta postale di gruppo per il contenuto della scheda nei messaggi del canale. Per altre informazioni, vedere la sezione "Conservare il contenuto della scheda" in [Creare un blocco di eDiscovery.](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)|


> [!NOTE]
> Per conservare le comunicazioni nei canali privati, è necessario mettere in blocco le cassette postali degli utenti (utenti del canale privato) e, quando si usa lo strumento eDiscovery per la ricerca, è consigliabile cercare nella cassetta postale dell'utente. Come è stato detto in precedenza, le chat dei canali privati vengono archiviate nelle cassette postali degli utenti, non nella cassetta postale di gruppo di un team.

Per altre informazioni su questo argomento per le aree non Teams in Microsoft 365, vedere Gestire i casi di [eDiscovery:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)Mettere in attesa i percorsi di contenuto.
