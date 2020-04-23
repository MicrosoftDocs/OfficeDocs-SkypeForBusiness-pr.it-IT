---
title: Posizione dei dati in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: Informazioni sulla posizione di archiviazione dei dati in Microsoft teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11d95858c39a2d555a4b1a7433b0a7dce0388293
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780265"
---
# <a name="location-of-data-in-microsoft-teams"></a>Posizione dei dati in Microsoft Teams

I dati in teams si trovano nell'area geografica associata all'organizzazione di Office 365. Attualmente, teams supporta l'Australia, il Canada, la Francia, la Germania, l'India, il Giappone, il Sud Africa, la Corea del sud, la Svizzera (che include Liechtenstein), gli Emirati Arabi Uniti, il Regno Unito, le Americhe, l'APAC e le aree EMEA. 

> [!IMPORTANT]
> I team attualmente offrono la residenza dati in Australia, Canada, Francia, Germania, India, Giappone, Emirati Arabi Uniti, Regno Unito, Corea del sud, Sudafrica e Svizzera (che include Liechtenstein) solo per i nuovi inquilini.
> Un nuovo tenant viene definito come un tenant che non ha un singolo utente del tenant che accede a teams. I tenant esistenti provenienti da Australia, India, Giappone e Corea del sud continueranno ad avere i dati dei team archiviati nell'area APAC. I tenant esistenti in Canada continueranno ad avere i loro dati archiviati nelle Americhe. I residenti esistenti in Francia, Germania, Liechtenstein, Emirati Arabi Uniti, Regno Unito, Sudafrica e Svizzera avranno i loro dati archiviati nella regione EMEA.

## <a name="where-your-teams-data-is-stored"></a>Dove sono archiviati i dati del team

Per visualizzare l'area geografica contenente i dati per il tenant, accedere al**profilo dell'organizzazione****delle impostazioni** > dell'interfaccia di [Amministrazione](https://portal.office.com/adminportal/home) > di Microsoft 365. Scorrere verso il basso fino a **posizione dati**.

![Screenshot della tabella della posizione dei dati, inclusi i team nell'interfaccia di amministrazione](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Posizione dei dati di Teams a riposo

I dati dei team vengono archiviati in modo diverso a seconda del tipo di contenuto. 

![Diagramma che mostra i tipi di contenuto dei team e dove sono archiviati a riposo](media/location-of-data-storage-at-rest.png)

Per una discussione approfondita, vedere la [sessione Ignite di breakout in Microsoft teams Architecture](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) .

### <a name="core-teams-customer-data"></a>Dati dei clienti di core Teams

Se il tenant è stato provisioning in Australia, Canada, Unione europea, Francia, Germania, India, Giappone, Sud Africa, Corea del sud, Svizzera (che include Liechtenstein), Emirati Arabi Uniti, Regno Unito o Stati Uniti, Microsoft archivia i dati dei clienti seguenti in Rest only in tale posizione:

- Chat Team, conversazioni di team e Channel, immagini, messaggi della segreteria telefonica e contatti
- Contenuto del sito di SharePoint Online e i file archiviati in tale sito
- File caricati in OneDrive for business

#### <a name="chat-channel-messages-team-structure"></a>Chat, messaggi di canale, struttura del team

Ogni team in teams è supportato da un gruppo di Office 365 e dal sito di SharePoint e dalla cassetta postale di Exchange. Chat private (incluse le chat di gruppo), messaggi inviati come parte di una conversazione in un canale e la struttura di team e canali è archiviata in un servizio di chat in uso in Azure. I dati vengono archiviati anche in una cartella nascosta nelle cassette postali di utenti e gruppi per abilitare le funzionalità di protezione delle informazioni.

#### <a name="voicemail-and-contacts"></a>Segreteria telefonica e contatti

I messaggi vocali sono archiviati in Exchange. I contatti sono archiviati nell'archivio dati cloud basato su Exchange. Exchange e il cloud Store basato su Exchange offrono già la residenza dei dati in ognuno dei centri di vendita a livello mondiale di GEOS. Per tutti i team, la segreteria telefonica e i contatti vengono archiviati in paese per Australia, Canada, Francia, Germania, India, Giappone, Emirati Arabi Uniti, Regno Unito, Sud Africa, Corea del sud, Svizzera (incluso il Liechtenstein) e Stati Uniti. Per tutti gli altri paesi, i file vengono archiviati nella posizione Stati Uniti, Europa o Asia-Pacifico in base all'affinità del tenant.

#### <a name="images-and-media"></a>Immagini e elementi multimediali

Elementi multimediali usati nelle chat (ad eccezione di Giphy gif che non sono archiviate ma sono un collegamento di riferimento all'URL del servizio Giphy originale, Giphy è un servizio non Microsoft) è archiviato in un servizio multimediale basato su Azure distribuito nelle stesse posizioni del servizio chat.

#### <a name="files"></a>File

I file (inclusi OneNote e wiki) condivisi da una persona in un canale sono archiviati nel sito di SharePoint del team. I file condivisi in una chat privata o in una chat durante una riunione o una chiamata vengono caricati e archiviati in OneDrive per l'account aziendale dell'utente che condivide il file. Exchange, SharePoint e OneDrive offrono già una residenza di dati in ognuno di essi. Quindi, per i clienti esistenti, tutti i file, i blocchi appunti di OneNote, il contenuto wiki di teams e le cassette postali che fanno parte dell'esperienza teams sono già archiviati nella posizione in base all'affinità del tenant. I file sono archiviati nel paese per l'Australia, il Canada, la Francia, la Germania, l'India, il Giappone, gli Emirati Arabi Uniti, il Regno Unito, il Sud Africa, la Corea del sud e la Svizzera (che include il Liechtenstein). Per tutti gli altri paesi, i file vengono archiviati nella posizione Stati Uniti, Europa o Asia Pacifico in base all'affinità del tenant.

### <a name="datacenter-locations"></a>Posizioni del centro dati

I servizi Team descritti in questa sezione archiviano i dati in Rest nei percorsi seguenti:

|Paese o area geografica  |Posizione Datacenter |
|---------|---------|
|Australia   |New South Wales e Victoria         |
|Canada    |Quebec City e Toronto         |
|Francia    |Marsiglia e Parigi         |
|Germania    |Berlino e Francoforte      |
|India   |Chennai e Pune        |
|Giappone    |Tokyo (Saitama) e Osaka         |
|Liechtenstein   |Ginevra e Zurigo       |
|Sudafrica     |Johannesburg e Cape Town         |
|Sud Corea     |Seoul e Busan         |
|Svizzera    |Ginevra e Zurigo       |
|Emirati Arabi Uniti     |Abu Dhabi e Dubai         |
|Regno Unito     | Cardiff e Londra        |
|Americhe-Nord e Sud (AMER) |Bay, CA e Boydton, VA       |
|Asia Pacifico (APAC)  |Singapore e Hong Kong        |
|Europa, Medio Oriente e Asia (EMEA)   |Dublino e Amsterdam        |

> [!NOTE]
> Per il Liechtenstein, i dati vengono archiviati a riposo nei data center della Svizzera a Ginevra e Zurigo.

### <a name="data-stored-with-a-third-party-storage-provider"></a>Dati archiviati con un provider di archiviazione di terze parti

Le organizzazioni che consentono agli utenti di archiviare i file con un provider di archiviazione di terze parti dipendono dalla posizione di archiviazione di tali servizi e devono quindi rivedere la posizione dei dati a riposo per tali servizi separatamente.

- **Schede**: le schede consentono agli utenti di aggiungere informazioni da app e servizi a un canale. In questo modo, varia in base al tipo di tabulazione in cui vengono archiviati i dati. La scheda stessa non archivia i dati. Ad esempio, una scheda di SharePoint archivierà i dati in base alla posizione di provisioning della raccolta siti di SharePoint. Una scheda che include informazioni di un partner archivierà i dati direttamente nel sistema usato dal partner e ne presenta solo una visualizzazione.
- **Altre app partner**: Microsoft non offre il supporto per le app e i servizi dei partner che potresti usare all'interno dell'esperienza teams. Esaminare direttamente le informazioni da queste soluzioni per conoscere la posizione in cui vengono archiviati i dati.

## <a name="see-also"></a>Vedere anche

- [Microsoft teams avvia l'United Arab Emirates data Residency](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft teams avvia la residenza di dati in Corea del sud](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft teams lancia il South African data Residency](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft teams avvia France data Residency](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft teams avvia l'India data Residency, altro GEOS presto disponibile](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft teams avvia l'Australia e la Japan data Residency](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft teams avvia Canada data Residency, Australia e Giappone presto disponibile](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
