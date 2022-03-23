---
title: Mettere in blocco Microsoft Teams un utente o un team
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
description: Informazioni su come mettere un Microsoft Teams o un team in blocco legale usando il Centro conformità Microsoft 365 e scoprire quali sono le esigenze di un blocco legale in base ai requisiti di dati.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06b3ea009e538b8796a9e55b277dc4ec12f5a3a4
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711560"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Mettere in blocco Microsoft Teams un utente o un team

Quando esiste una ragionevole aspettativa di controversie legali, le organizzazioni devono conservare le informazioni archiviate elettronicamente (ESI), inclusi Teams messaggi di chat rilevanti per il caso. Le organizzazioni potrebbero dover conservare tutti i messaggi correlati a un'indagine specifica o a una persona specifica. Questo articolo discuterà dell'uso di un blocco legale per mantenere il contenuto in Microsoft Teams. Per mantenere il contenuto in altri servizi in Microsoft 365, vedere [Creare un blocco di eDiscovery](/microsoft-365/compliance/create-ediscovery-holds).

> [!NOTE]
> A febbraio 2020 è stato attivato il blocco legale per i canali privati. Le chat del canale privato vengono archiviate nelle cassette postali degli utenti, mentre le chat dei canali standard vengono archiviate nella cassetta postale associata al team padre. Se esiste già un blocco legale per una cassetta postale utente, il criterio di blocco verrà applicato automaticamente ai messaggi del canale privato archiviati nella cassetta postale. Non sono necessarie altre azioni per l'attivazione di questa opzione da parte di un amministratore. È supportato anche il blocco legale dei file condivisi nei canali privati.

All'Microsoft Teams, un intero team o utenti selezionati può essere sospeso per motivi legali. In questo modo si assicurerà che tutti i messaggi s scambiati in tali team (inclusi i canali privati e condivisi) o i messaggi s scambiati da tali utenti siano individuabili dai responsabili della conformità o dagli amministratori Teams aziendali.

> [!NOTE]
> L'applicazione di un blocco a un utente non comporta automaticamente il blocco di un gruppo o viceversa.
> Le notifiche inviate nei feed attività non possono essere poste in blocco.

Per impostare un blocco legale per un utente o un team in un caso di eDiscovery di base:

1. Passare al [Centro conformità Microsoft 365](https://compliance.microsoft.com). Quando si crea un nuovo caso, viene visualizzata l'opzione per mettere in blocco cassette postali o siti.

2. Passare a **eDiscoveryCore** >  e creare un caso facendo clic **su Crea un caso**. Dopo aver creato il caso, aprirlo.
  
   ![Microsoft Teams scheda eDiscovery è selezionata, con il pulsante Crea un caso.](media/LegalHold1.png)

   > [!NOTE]
   > È anche possibile inserire un utente in un blocco associato a un Advanced eDiscovery caso. Per altre informazioni, vedere [Gestire i blocchi in Advanced eDiscovery](/microsoft-365/compliance/managing-holds).

3. Passare alla scheda **Blocchi** nel menu superiore e fare clic **su Crea** per creare un blocco. L'applicazione di un blocco a un utente o a un team mantiene tutti i messaggi s scambiati da tali utenti. Quando si crea un nuovo caso, viene visualizzata l'opzione per mettere in blocco cassette postali o siti.

   ![Immagine che mostra la scheda Blocchi selezionata e il pulsante Crea sotto.](media/LegalHold2.png)

   1. **Assegnare un nome al blocco**. Selezionare un nome descrittivo e univoco per il blocco che si sta per creare.
  
       ![Questa schermata mostra la scheda Assegnare un nome al blocco, in cui è possibile immettere un nome e una descrizione per il blocco che si sta creando.](media/LegalHold3.png)

   2. **Scegliere la posizione**. Scegliere se applicare il blocco a un utente o a un intero team (per il momento non è possibile applicare un blocco ai singoli canali). Se un utente è in stato di blocco, tutti i messaggi vengono mantenuti, inclusi i messaggi nelle chat 1:1, nelle chat di gruppo e nei canali privati. I messaggi nei canali standard e condivisi vengono mantenuti quando il team padre viene sospeso.

      ![Scegliere le posizioni dei dati da mettere in blocco.](media/LegalHold4.png)

   3. **Creare una query**. È possibile personalizzare il blocco se si vuole una maggiore granularità nei criteri di blocco. Ad esempio, è possibile specificare parole chiave da cercare oppure aggiungere altre condizioni che dovranno essere soddisfatte per l'applicazione del blocco.

   4. **Rivedere le impostazioni prima** di creare il blocco.

Dopo aver creato il blocco, è possibile eseguire ricerche nel contenuto mantenuto dai criteri di blocco. Per altre informazioni, vedere [Condurre un'indagine eDiscovery in Teams](eDiscovery-investigation.md).

> [!IMPORTANT]
> Quando un utente o un gruppo viene sospeso, vengono mantenute tutte le copie di conformità dei messaggi. Ad esempio, se un utente pubblica un messaggio in un canale e quindi lo modifica, vengono mantenute entrambe le copie del messaggio. Senza il blocco, viene mantenuto solo il messaggio più recente.

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>Percorsi di contenuto da mettere in blocco per mantenere Teams contenuto

Come guida utile, usare la tabella seguente per comprendere quali percorsi di contenuto, ad esempio una cassetta postale o un sito, inserire un blocco per mantenere i diversi tipi di contenuto Teams contenuto.

|Scenario  |Percorso del contenuto  |
|---------|---------|
|Messaggi di chat per un utente (ad esempio, chat 1:1, chat di gruppo 1:N e conversazioni di canale privato)     |Cassetta postale utente         |
|Messaggi di chat nei canali standard e condivisi    |Cassetta postale associata al team padre         |
|File nei canali standard(ad esempio, contenuto Wiki e file)     |SharePoint sito associato al team padre        |
|File nei canali privati e condivisi     |Sito SharePoint dedicato associato al canale
|Contenuto privato dell'utente     |Account OneDrive for Business utente       |
|Contenuto della scheda nelle chat|Cassetta postale utente per chat 1:1, chat di gruppo 1:N e conversazioni di canale privato; la cassetta postale del team padre per il contenuto della scheda nei messaggi dei canali standard e condivisi. Per altre informazioni, vedere la sezione "Conservare il contenuto della scheda" in [Creare un blocco di eDiscovery](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).|
|||

> [!NOTE]
> Per conservare il contenuto dei messaggi nei canali privati, è necessario mettere in blocco le cassette postali degli utenti (dei membri di un canale privato). e quando si usa lo strumento eDiscovery per eseguire ricerche nei messaggi del canale privato, è necessario eseguire ricerche nella cassetta postale dell'utente. Come è stato detto in precedenza, le chat dei canali privati vengono archiviate nelle cassette postali degli utenti, non nella cassetta postale del gruppo associata al team padre.
