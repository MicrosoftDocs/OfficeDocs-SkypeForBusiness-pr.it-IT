---
title: Posizione dei dati in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: In questo articolo verranno fornite informazioni su dove risiedono dal punto di vista geografico i dati in Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c16065a864ac82cdf5f11c0d2c8254b648731cac
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121686"
---
# <a name="location-of-data-in-microsoft-teams"></a>Posizione dei dati in Microsoft Teams

I dati in Teams risiedono nell'area geografica associata all'organizzazione Office 365 o Microsoft 365 dell'utente. Attualmente Teams supporta le seguenti aree geografiche: Australia, Canada, Francia, Germania, India, Giappone, Sudafrica, Corea del Sud, Svizzera (che include il Liechtenstein), Emirati Arabi Uniti, Regno Unito, Americhe, regioni APAC ed EMEA. 

> [!IMPORTANT]
> Teams offre attualmente la residenza di dati in Australia, Canada, Francia, Germania, India, Giappone, Emirati Arabi Uniti, Regno Unito, Corea del sud, Sudafrica e Svizzera (che include il Liechtenstein) solo per i nuovi tenant.
> Per nuovo tenant si intende qualsiasi tenant che non abbia ancora sperimentato l'accesso di un singolo utente dal tenant a Teams. I tenant esistenti da Australia, India, Giappone e Corea del sud continueranno a mantenere i dati di Teams archiviati nell'area APAC. I tenant esistenti in Canada continueranno a mantenere i dati archiviati in America. I tenant esistenti in Francia, Germania, Liechtenstein, Emirati Arabi Uniti, Regno Unito, Sudafrica e Svizzera continueranno a mantenere i loro dati archiviati nell'area EMEA.

## <a name="where-your-teams-data-is-stored"></a>Dove vengono archiviati i dati di Teams

Per vedere quali aree geografiche ospitano i dati per il tenant, passare all'[interfaccia di amministrazione di Microsoft 365](https://portal.office.com/adminportal/home) > **Impostazioni** > **Profilo organizzazione**. Scorrere verso il basso fino a **Posizione dati**.

![Screenshot della tabella della posizione dei dati, incluso Teams nell'interfaccia di amministrazione](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Posizione dei dati inattivi di Teams

I dati di Teams vengono archiviati in modo diverso a seconda del tipo di contenuto. 

![Diagramma che mostra i tipi di contenuto di Teams e il luogo in cui sono archiviati i dati inattivi](media/location-of-data-storage-at-rest.png)

Per un maggiore approfondimento, consultare la [breakout session Ignite sull'architettura di Microsoft Teams](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071).

### <a name="core-teams-customer-data"></a>Dati dei clienti Teams principali

Se il provisioning del proprio tenant viene effettuato in Australia, Canada, Unione europea, Francia, Germania, India, Giappone, Sudafrica, Corea del sud, Svizzera (che include il Liechtenstein), Emirati Arabi Uniti, Regno Unito o Stati Uniti, Microsoft archivia i seguenti dati inattivi dei clienti solo in tale posizione:

- Le chat di Teams, le conversazioni in Teams e di canale, le immagini, i messaggi vocali e i contatti
- I contenuti del sito di SharePoint Online e i file archiviati all'interno di tale sito
- I file caricati in OneDrive for Business

#### <a name="chat-channel-messages-team-structure"></a>La chat, i messaggi di canale, la struttura del team

Ogni team di Teams è associato a un gruppo di Microsoft 365, al relativo sito di SharePoint e alle cassette postali di Exchange. Le chat private (incluse le chat di gruppo), i messaggi inviati nell'ambito di una conversazione in un canale e la struttura di team e canali sono archiviati in un servizio di chat che viene eseguito in Azure. I dati vengono archiviati anche in una cartella nascosta nelle cassette postali degli utenti e dei gruppi per abilitare le funzionalità di protezione delle informazioni.

#### <a name="voicemail-and-contacts"></a>Messaggi vocali e contatti

I messaggi vocali vengono archiviati in Exchange. I contatti vengono archiviati nell'archivio dati cloud basato su Exchange. Exchange e l'archivio cloud basato su Exchange forniscono già una residenza dei dati in ogni data center a livello mondiale. Per tutti i team, i messaggi vocali e i contatti vengono archiviati all'interno del Paese per Australia, Canada, Francia, Germania, India, Giappone, Emirati Arabi Uniti, Regno Unito, Sudafrica, Corea del Sud, Svizzera (compreso il Liechtenstein) e Stati Uniti. Per tutti gli altri Paesi, i file vengono archiviati in USA, Europe o Asia-Pacifico in base all'affinità del tenant.

#### <a name="images-and-media"></a>Immagini e contenuti multimediali

Gli elementi multimediali usati nelle chat (tranne per le GIF Giphy che non sono archiviate ma sono un collegamento di riferimento all'URL del servizio Giphy originale, Giphy è un servizio non Microsoft) vengono archiviati in un servizio multimediale basato su Azure distribuito nelle stesse posizioni del servizio di chat.

#### <a name="files"></a>File

I file (inclusi OneNote e Wiki) che qualcuno condivide in un canale vengono archiviati nel sito di SharePoint del team. I file condivisi in una chat privata o in una chat durante una riunione o una chiamata vengono caricati e archiviati in OneDrive per l'account aziendale dell'utente che condivide il file. Exchange, SharePoint e OneDrive forniscono già una residenza dei dati in ogni data center a livello mondiale. Quindi, per i clienti esistenti, tutti i file, i blocchi appunti di OneNote, il contenuto wiki di Teams e le cassette postali che fanno parte dell'esperienza di Teams sono già archiviati nella posizione in base all'affinità del tenant. I file vengono archiviati all'interno del Paese per Australia, Canada, Francia, Germania, India, Giappone, Emirati Arabi Uniti, Regno Unito, Sudafrica, Corea del Sud, Svizzera (che include il Liechtenstein). Per tutti gli altri Paesi, i file vengono archiviati in USA, Europe o Asia Pacifico in base all'affinità del tenant.

### <a name="datacenter-locations"></a>Posizione dei data center

I servizi di Teams descritti in questa sezione archiviano i dati inattivi nelle seguenti posizioni:

|Paese o area geografica  |Posizione del data center |
|---------|---------|
|Australia   |Nuovo Galles del Sud e Victoria         |
|Canada    |Québec e Toronto         |
|Francia    |Marsiglia e Parigi         |
|Germania    |Berlino e Francoforte      |
|India   |Chennai e Pune        |
|Giappone    |Tokyo (Saitama) e Osaka         |
|Liechtenstein   |Ginevra e Zurigo       |
|Sudafrica     |Città del Capo, Johannesburg         |
|Corea del Sud     |Seul e Busan         |
|Svizzera    |Ginevra e Zurigo       |
|Emirati Arabi Uniti     |Abu Dhabi e Dubai         |
|Regno Unito     | Cardiff e Londra        |
|Americhe: Nord e Sud (AMER) |Bay, CA e Boydton, VA       |
|Asia Pacifico (APAC)  |Singapore e Hong Kong        |
|Europa, Medio Oriente e Africa (EMEA)   |Dublino e Amsterdam        |

> [!NOTE]
> Per il Liechtenstein, i dati inattivi vengono archiviati nei data center in Svizzera a Ginevra e Zurigo.

### <a name="data-stored-with-a-third-party-storage-provider"></a>Dati archiviati con un provider di archiviazione di terze parti

Le organizzazioni che consentono agli utenti di archiviare file con un provider di spazio di archiviazione di terze parti dipendono dalla posizione di archiviazione di tali servizi e devono, di conseguenza, rivedere la posizione dei dati inattivi per tali servizi separatamente.

- **Schede**: le schede consentono agli utenti di aggiungere le informazioni da app e servizi a un canale. Di conseguenza, varia in base al tipo di scheda in cui sono archiviati i dati. La scheda in se stessa non archivia i dati. Una scheda SharePoint, ad esempio, archivia i dati in base alla posizione di provisioning della raccolta del sito di SharePoint. Una scheda che include informazioni da un partner archivierà i dati direttamente nel sistema usato dal partner e ne presenterà solo una visualizzazione.
- **App di altri partner**: Microsoft non offre supporto per le app e i servizi di residenza dei dati per le app e i servizi dei partner, che possono essere usati in Teams. Rivedere le informazioni da queste soluzioni direttamente per ottenere informazioni sulla posizione di archiviazione dei dati.

## <a name="see-also"></a>Vedere anche

- [Microsoft Teams avvia la residenza dei dati per gli Emirati Arabi Uniti](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft Teams avvia la residenza dei dati per la Corea del Sud](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft Teams avvia la residenza dei dati per il Sudafrica](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft Teams avvia la residenza dei dati per la Francia](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft Teams avvia la residenza dei dati per l'India, presto disponibili altre aree geografiche](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft Teams avvia la residenza dei dati per il Giappone](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft Teams avvia la residenza dei dati per il Canada, presto disponibili Australia e Giappone](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
