---
title: Mettere un utente o un team di Microsoft Teams a un blocco a fini giudiziari
author: robmazz
ms.author: robmazz
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
description: Informazioni su come mettere un utente o un team di Microsoft Teams in stato di blocco legale usando il Portale di conformità di Microsoft Purview e scoprire cosa richiede un blocco legale in base ai requisiti dei dati.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dc99518aa3580311c48966105ccc4b4ba6cf518
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808757"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Mettere un utente o un team di Microsoft Teams a un blocco a fini giudiziari

Quando esiste una ragionevole aspettativa di controversie legali, le organizzazioni devono conservare le informazioni archiviate elettronicamente, inclusi i messaggi di chat di Teams rilevanti per il caso. Le organizzazioni potrebbero dover conservare tutti i messaggi correlati a un'indagine specifica o a una persona specifica. Questo articolo discuterà dell'uso di un blocco a fini giudiziari per conservare il contenuto in Microsoft Teams. Per mantenere il contenuto in altri servizi in Microsoft 365, vedere [Creare un blocco di eDiscovery](/microsoft-365/compliance/create-ediscovery-holds).

> [!NOTE]
> Nel mese di febbraio 2020 abbiamo attivato il blocco legale per i canali privati. Le chat dei canali privati vengono archiviate nelle cassette postali degli utenti, mentre le chat di canale standard vengono archiviate nella cassetta postale associata al team padre. Se è già applicato un blocco a fini giudiziari per una cassetta postale utente, il criterio di blocco verrà ora applicato automaticamente ai messaggi del canale privato archiviati in tale cassetta postale. Non sono necessarie altre azioni per l'attivazione da parte di un amministratore. È supportata anche la conservazione a fini giudiziari dei file condivisi nei canali privati.

All'interno di Microsoft Teams, un intero team o utenti selezionati possono essere bloccati a fini giudiziari. In questo modo si assicurerà che tutti i messaggi scambiati in tali team (inclusi i canali privati e condivisi) o i messaggi scambiati da tali persone siano individuabili dai responsabili della conformità dell'organizzazione o dagli amministratori di Teams.

> [!NOTE]
> L'applicazione di un blocco a un utente non applica automaticamente un blocco a un gruppo o viceversa.
> Le notifiche inviate nei feed attività non possono essere bloccate.

Per applicare un blocco a un utente o a un team in un caso di eDiscovery (standard):

1. Vai alla [Portale di conformità di Microsoft Purview](https://compliance.microsoft.com). Quando si crea un nuovo caso, viene visualizzata l'opzione per bloccare cassette postali o siti.

2. Passare a **eDiscovery** > **Core** e creare un caso facendo clic su **Crea un caso**. Dopo aver creato il caso, aprirlo.
  
   ![È selezionata la scheda Microsoft Teams eDiscovery, con il pulsante Crea un caso.](media/LegalHold1.png)

   > [!NOTE]
   > È anche possibile applicare un blocco a un utente associato a un caso di eDiscovery (Premium). Per altre informazioni, vedere [Gestire i blocchi in eDiscovery (Premium).For more information, see Manage holds in eDiscovery (Premium)](/microsoft-365/compliance/managing-holds).

3. Passare alla scheda **Blocchi** nel menu superiore e fare clic su **Crea** per creare un blocco. L'applicazione di un blocco a un utente o a un team mantiene tutti i messaggi scambiati da tali utenti. Quando si crea un nuovo caso, viene visualizzata l'opzione per bloccare cassette postali o siti.

   ![Immagine che mostra la scheda Blocchi selezionata e il pulsante Crea sotto.](media/LegalHold2.png)

   1. **Assegna un nome al blocco**. Selezionare un nome descrittivo e univoco per il blocco che si vuole creare.
  
       ![Questa schermata mostra la scheda Assegna un nome al blocco, in cui è possibile immettere un nome e una descrizione per il blocco che si sta creando.](media/LegalHold3.png)

   2. **Scegliere la posizione**. Scegliere se applicare il blocco a un utente o a un intero team (per il momento non è possibile applicare un blocco ai singoli canali). Se un utente è bloccato, tutti i messaggi vengono conservati, inclusi i messaggi in chat 1:1, chat di gruppo e canali privati. I messaggi nei canali standard e condivisi vengono mantenuti quando viene applicato un blocco al team padre.

      ![Scegliere le posizioni di dati a cui applicare il blocco.](media/LegalHold4.png)

   3. **Creare una query**. È possibile personalizzare il blocco se si vuole una maggiore granularità nei criteri di blocco. Ad esempio, è possibile specificare le parole chiave da cercare o aggiungere altre condizioni che dovranno essere soddisfatte per rendere effettiva la sospensione.

   4. **Rivedere le impostazioni** prima di creare il blocco.

Dopo aver creato il blocco, è possibile eseguire ricerche nel contenuto conservato dal criterio di blocco. Per altre informazioni, vedere [Condurre un'indagine di eDiscovery in Teams](eDiscovery-investigation.md).

> [!IMPORTANT]
> Quando a un utente o a un gruppo viene applicato un blocco, vengono mantenute tutte le copie dei messaggi di conformità. Ad esempio, se un utente pubblica un messaggio in un canale e quindi modifica il messaggio, vengono mantenute entrambe le copie del messaggio. Senza il blocco, viene mantenuto solo il messaggio più recente.

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>Percorsi di contenuto da bloccare per conservare il contenuto di Teams

Come guida utile, usare la tabella seguente per capire quali percorsi di contenuto (ad esempio una cassetta postale o un sito) bloccare per mantenere diversi tipi di contenuto di Teams.

|Scenario  |Percorso del contenuto  |
|---------|---------|
|Messaggi in chat per un utente (ad esempio, chat 1:1, chat di gruppo 1:N e conversazioni di canale private)     |Cassetta postale utente         |
|Messaggi di chat nei canali standard e condivisi    |Cassetta postale associata al team padre         |
|File nei canali standard (ad esempio, contenuto wiki e file)     |Sito di SharePoint associato al team padre        |
|File in canali privati e condivisi     |Sito di SharePoint dedicato associato al canale
|Contenuto privato dell'utente     |Account OneDrive for Business dell'utente       |
|Contenuto della scheda nelle chat|Cassetta postale utente per chat 1:1, chat di gruppo 1:N e conversazioni di canale privato; la cassetta postale del team padre per il contenuto della scheda nei messaggi del canale standard e condiviso. Per altre informazioni, vedere la sezione "Mantenere il contenuto della scheda" in [Creare un blocco di eDiscovery](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).|
|||

> [!NOTE]
> Per conservare il contenuto dei messaggi nei canali privati, è necessario bloccare le cassette postali degli utenti (dei membri di un canale privato). e quando si usa lo strumento eDiscovery per cercare messaggi di canale privati, è necessario eseguire una ricerca nella cassetta postale dell'utente. Come indicato in precedenza, le chat del canale privato vengono archiviate nelle cassette postali degli utenti, non nella cassetta postale del gruppo associata al team padre.
