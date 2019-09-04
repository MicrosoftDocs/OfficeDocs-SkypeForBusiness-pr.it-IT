---
title: Limiti e specifiche per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: Informazioni sui limiti, le specifiche e gli altri requisiti applicabili a Microsoft teams.
localization_priority: Priority
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82fbaa955c080446619558a7a90410200f4be604
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715900"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Limiti e specifiche per Microsoft Teams

Questo articolo descrive alcuni dei limiti, delle specifiche e di altri requisiti applicabili ai team.

## <a name="teams-and-channels"></a>Team e canali

|Funzionalità    | Limite massimo |
|-----------|---------------|
|Numero di team che un utente può creare | Soggetto a un limite di oggetti di 250&sup1;         |
|Numero di membri in un team | 5.000       |
|Numero di team a livello di organizzazione consentiti in un tenant | 5     |
|Numero di membri in un [team a livello di organizzazione](create-an-org-wide-team.md) | 5.000       |
|Numero di team che un amministratore globale può creare        |  500.000   |
|Numero di team che un tenant di Office 365 può avere    | 500.000&sup2;     |
|Numero di canali per Team    | 200 (include canali eliminati) &sup3;         |

&sup1; Qualsiasi oggetto directory in Azure Active Directory conta verso questo limite. Gli amministratori globali sono esenti da questo limite, così come le app che chiamano Microsoft Graph usando le [autorizzazioni dell'applicazione](https://docs.microsoft.com/graph/permissions-reference).

&sup2; Questo limite include team archiviati.

&sup3; i canali eliminati possono essere ripristinati entro 30 giorni. Durante questi 30 giorni, un canale eliminato continua a essere conteggiato verso il canale di 200 per limite di team. Dopo 30 giorni, un canale eliminato e il relativo contenuto vengono eliminati definitivamente e il canale non viene più conteggiato verso i canali di 200 per il limite del team.

## <a name="messaging"></a>Messaggistica

### <a name="chat"></a>Chat

Gli utenti che partecipano a conversazioni che fanno parte dell'elenco chat in teams devono avere una cassetta postale di Exchange Online (basata su cloud) per un amministratore per cercare le conversazioni di chat. Questo perché le conversazioni che fanno parte dell'elenco chat sono archiviate nelle cassette postali basate su cloud dei partecipanti alla chat. Se un partecipante alla chat non ha una cassetta postale di Exchange Online, l'amministratore non potrà cercare o inserire un blocco nelle conversazioni di chat. Ad esempio, in una distribuzione ibrida di Exchange gli utenti con cassette postali locali potrebbero essere in grado di partecipare a conversazioni che fanno parte dell'elenco chat in teams. Tuttavia, in questo caso, il contenuto di queste conversazioni non è ricercabile e non può essere messo in attesa perché gli utenti non hanno cassette postali basate su cloud. Per altre informazioni, vedere [interazione tra Exchange e Microsoft teams](exchange-teams-interact.md).

La chat di teams funziona su un backend di Microsoft Exchange, quindi i limiti della messaggistica di Exchange si applicano alla funzione chat in teams.

|Funzionalità  | Limite massimo  |
|---------|---------|
|Numero di persone in una chat privata<sup>1</sup>  | 100    |
|Numero di file allegati<sup>2</sup>  |10     |

<sup>1</sup> Se si hanno più di 20 persone in una chat, le caratteristiche della chat seguenti sono disattivate: le risposte automatiche di Outlook e i messaggi di stato di Teams; indicatore di digitazione; chiamate audio e video; condivisione leggere le conferme.

<sup>2</sup> Se il numero di allegati supera questo limite, viene visualizzato un messaggio di errore.

### <a name="emailing-a-channel"></a>Inviare tramite posta elettronica un canale

 Se gli utenti desiderano inviare un messaggio di posta elettronica a un canale in teams, usano l'indirizzo di posta elettronica del canale. Quando un messaggio di posta elettronica fa parte di un canale, chiunque può rispondere per avviare una conversazione. Ecco alcuni dei limiti applicabili per l'invio di messaggi di posta elettronica a un canale.

|Funzionalità  | Limite massimo  |
|---------|---------|
|Dimensione<sup>messaggio 1<sup> | 24 KB |
|Numero di file allegati<sup>2</sup>  |20     |
|Dimensioni di ogni allegato di file | Minore di 10 MB |
|Numero di immagini inline<sup>2</sup> |50   |

<sup>1</sup> Se il messaggio supera questo limite, viene generato un messaggio di anteprima e all'utente viene chiesto di scaricare e visualizzare la posta elettronica originale dal collegamento fornito.

<sup>2</sup> Se il numero di allegati o immagini supera questo limite, viene visualizzato un messaggio di errore.

Per altre informazioni, vedere [limiti di Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

> [!NOTE]
> Le dimensioni dei messaggi, i file allegati e i limiti delle immagini in linea sono gli stessi per tutte le licenze di Office 365.

## <a name="channel-names"></a>Nomi dei canali

I nomi dei canali non possono contenere i caratteri o le parole seguenti.

|||
|---------|---------|
|Caratteri     | ~ #% & * {} +/\:  < > ? &#124;' "..        |
|Caratteri in questi intervalli    | da 0 a 1F<br>80 a 9F        |
|Parole     | maschere, CON, CONIn $, CONOUT $, PRN, AUX, NUL, COM1 in COM9, LPT1 in LPT9, desktop. ini, &#95;VTi&#95;|

Anche i nomi dei canali non possono iniziare con un carattere di sottolineatura (_) o un punto (.) o terminare con un punto (.).

## <a name="meetings-and-calls"></a>Riunioni e chiamate

|Funzionalità     | Limite massimo |
|------------|---------------|
|Numero di persone in una riunione  | 250    |

## <a name="teams-live-events"></a>Eventi live di Teams

|Funzionalità     | Limite massimo |
|------------|---------------|
|Dimensioni del gruppo di destinatari | 10.000 partecipanti |
|Durata dell'evento | 4 ore |
|Eventi dinamici contemporanei in un tenant di Office 365 | 15 |

Per altre informazioni sugli eventi dinamici e un confronto tra eventi live di teams e Skype meeting broadcast, vai a [eventi live di teams e Skype meeting broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).

## <a name="storage"></a>Archiviazione

Ogni team di Microsoft Teams ha un sito del team in SharePoint Online e ogni canale di un team ottiene una cartella all'interno della raccolta documenti predefinita del sito del team. I file condivisi all'interno di una conversazione vengono automaticamente aggiunti alla raccolta documenti e le autorizzazioni e le opzioni di sicurezza dei file impostate in SharePoint vengono automaticamente riflesse in teams.

Se SharePoint Online non è abilitato nel tenant, gli utenti di Microsoft teams non possono sempre condividere file in teams. Gli utenti di chat privata non possono anche condividere file perché OneDrive for business (collegato alla licenza di SharePoint) è necessario per tale funzionalità.

Archiviando i file nella raccolta documenti di SharePoint Online e in OneDrive for business, verranno seguite tutte le regole di conformità configurate a livello di tenant. Per altre informazioni, vedere [come interagire con SharePoint Online e OneDrive for business con Microsoft teams](sharepoint-onedrive-interact.md).

Poiché teams viene eseguito su un backend di SharePoint Online per la condivisione di file, le limitazioni di SharePoint si applicano alla sezione file all'interno di un team. Ecco i limiti di spazio di archiviazione applicabili per SharePoint Online.

|Funzionalità                 |Office 365 Business Essentials  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|Archiviazione                 |1 TB per organizzazione più 10 GB per licenza acquistata  |1 TB per organizzazione più 10 GB per licenza acquistata  |1 TB per organizzazione più 10 GB per licenza acquistata   |1 TB per organizzazione più 10 GB per licenza acquistata |1 TB per organizzazione più 10 GB per licenza acquistata  |1 TB per organizzazione           |
|Spazio di archiviazione per i file Teams |Fino a 25 TB per raccolta siti o gruppo |Fino a 25 TB per raccolta siti o gruppo |Fino a 25 TB per raccolta siti o gruppo |Fino a 25 TB per raccolta siti o gruppo |Fino a 25 TB per raccolta siti o gruppo |Fino a 25 TB per raccolta siti o gruppo |
|Limite di caricamento file (per file)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

I canali sono appoggiati da cartelle nella raccolta siti di SharePoint Online creata per il team, quindi le schede dei file nei canali condividono i limiti di spazio di archiviazione del team a cui appartengono.

Per altre informazioni, vedere [limiti di SharePoint Online](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).

## <a name="contacts"></a>Contatti

Teams USA questi contatti:

- Contatti nell'Active Directory dell'organizzazione
- Contatti aggiunti alla cartella predefinita di Outlook dell'utente

Gli utenti di teams possono comunicare con chiunque nell'Active Directory dell'organizzazione e possono aggiungere chiunque nell'Active Directory dell'organizzazione come contatto e agli elenchi di contatti accedendo a **** > **contatti** o **chiamate**  >  di chat **Contatti**.

Gli utenti di teams possono anche aggiungere una persona che non è presente nell'Active Directory dell'organizzazione come contatto accedendo ai**contatti**delle **chiamate** > .

## <a name="browsers"></a>Browser

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>Sistemi operativi

Per informazioni sui requisiti del sistema operativo, vedere [ottenere client per Microsoft teams](get-clients.md).
