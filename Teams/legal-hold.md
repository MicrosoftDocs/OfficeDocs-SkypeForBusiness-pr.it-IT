---
title: Applicazione di un blocco Microsoft Teams un utente o un team
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
description: Informazioni su come impostare un blocco legale Microsoft Teams un utente o un team tramite il Centro sicurezza & conformità e scoprire quali sono le esigenze di un blocco legale in base ai requisiti di dati.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f2f269d75a7bf8bd97165329d2ae6b006b940f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112302"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Applicazione di un blocco Microsoft Teams un utente o un team
==================================================

Quando esiste una ragionevole aspettativa di controversie legali, le organizzazioni devono conservare le informazioni archiviate elettronicamente (ESI), inclusi Teams messaggi di chat rilevanti per il caso. Le organizzazioni potrebbero dover conservare tutti i messaggi relativi a un argomento specifico o a determinati utenti. Questo articolo coprirà il blocco legale in Microsoft Teams (Per risolvere l'implementazione del blocco nello spazio M365, vedere Gestire i casi di [eDiscovery:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)Mettere i percorsi di contenuto in blocco .).

> [!NOTE]
> A febbraio 2020 è stato abilitato il blocco legale o il blocco dei casi sui canali privati (le chat dei canali privati vengono archiviate nelle cassette postali degli utenti, le normali chat dei canali vengono archiviate nella cassetta postale di gruppo di un team). Se esiste già un blocco legale per una cassetta postale utente, il criterio di blocco verrà applicato automaticamente ai messaggi del canale privato archiviati nella cassetta postale. Non sono necessarie altre azioni per l'attivazione di questa opzione da parte di un amministratore. È supportato anche il blocco legale dei file condivisi nei canali privati.

All'Microsoft Teams, un intero team o un utente selezionato può essere sospeso o sospeso per motivi legali. In questo modo si assicurerà che tutti i messaggi s scambiati in questi team (inclusi i canali privati) o i messaggi s scambio da questi utenti siano individuabili dai responsabili della conformità dell'organizzazione o dagli amministratori Teams aziendali.

> [!NOTE]
> L'applicazione di un blocco a un utente non comporta automaticamente il blocco di un gruppo o viceversa.

Per impostare un blocco legale per un utente o un team:

1. Passare al [Centro sicurezza & conformità](https://go.microsoft.com/fwlink/?linkid=854628). Quando si crea un nuovo caso, viene visualizzata l'opzione per mettere in blocco cassette postali o siti.

2. Passare a eDiscovery o Advanced eDiscovery e creare un caso facendo clic su "Crea un caso". Dopo aver creato il caso, aprirlo.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Teams scheda eDiscovery selezionata, con il pulsante Crea un caso.](media/LegalHold1.png)

3. Passare alla sezione "Blocchi" dal menu superiore e fare clic su "+ Crea" per creare un blocco. L'applicazione di un blocco a un utente o a un team consente di salvare tutti i messaggi s scambiati da tali utenti o messaggi. Quando si crea un nuovo caso, viene visualizzata l'opzione per mettere in blocco cassette postali o siti.

   > [!div class="mx-imgBorder"]
   > ![Immagine che mostra la scheda Blocchi selezionata e il pulsante Crea sotto.](media/LegalHold2.png)

   1. **Assegnare un nome al blocco**. Selezionare un nome descrittivo e univoco per il blocco che si sta per creare.

      > [!div class="mx-imgBorder"]
      > ![Questa schermata mostra la scheda Assegnare un nome al blocco, in cui è possibile immettere un nome e una descrizione per il blocco che si sta creando.](media/LegalHold3.png)

    2. **Scegliere la posizione**. Scegliere se applicare il blocco a un utente o a un intero team (il blocco non può essere applicato ai singoli canali per il momento). Nota: se un utente è in stato di blocco, tutti i messaggi sono in attesa, incluso quello che ha inviato in una chat 1:1, in una chat 1:1 o in una chat di gruppo o in una conversazione di canale (inclusi i canali privati).
  
       > [!div class="mx-imgBorder"]
       > ![Ecco la sezione Scegliere le posizioni di Crea un nuovo blocco, in cui è possibile prendere decisioni sulle opzioni M365, tra cui Microsoft Teams, a cui si vuole applicare il blocco.](media/LegalHold4.png)

    3. **Crea query**. È possibile personalizzare il blocco se si vuole una maggiore granularità nei criteri di blocco. Ad esempio, è possibile specificare parole chiave da cercare oppure aggiungere altre condizioni che dovranno essere soddisfatte per l'applicazione del blocco.
    
    4. **Rivedere le impostazioni prima** di pubblicarla nell'organizzazione.

Dopo aver impostato il blocco legale, è possibile individuare tutto il contenuto conservato da qualsiasi criterio di blocco dopo [l'articolo Teams eDiscovery.](eDiscovery-investigation.md)

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
|Contenuto della scheda nelle chat|Cassetta postale utente per chat 1:1, chat di gruppo 1:N e conversazioni di canale privato o cassetta postale di gruppo per il contenuto della scheda nei messaggi del canale. Per altre informazioni, vedere la sezione "Conservare il contenuto della scheda" in [Creare un blocco di eDiscovery.](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)
||||

> [!NOTE]
> Per mantenere le comunicazioni nei canali privati, è necessario mettere in blocco le cassette postali degli utenti (utenti del canale privato) e quando si usa lo strumento eDiscovery per eseguire ricerche, è consigliabile eseguire una ricerca nella cassetta postale dell'utente. Come è stato detto in precedenza, le chat dei canali privati vengono archiviate nelle cassette postali degli utenti, non nella cassetta postale di gruppo di un team.

Per altre informazioni su questo argomento per le aree non Teams in Microsoft 365, vedere Gestire i casi di [eDiscovery:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)Mettere in attesa i percorsi di contenuto.