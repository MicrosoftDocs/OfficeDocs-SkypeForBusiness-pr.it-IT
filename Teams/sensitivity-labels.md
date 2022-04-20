---
title: Etichette di riservatezza per Microsoft Teams
ms.author: cabailey
author: cabailey
manager: laurawi
ms.reviewer: shubjain
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come usare le etichette di riservatezza per proteggere i team in Microsoft Teams.
ms.openlocfilehash: fab5ad4e3be3da5afc6ee373aa6bebe2afae819e
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922697"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Etichette di riservatezza per Microsoft Teams

[Le etichette di riservatezza](/microsoft-365/compliance/sensitivity-labels) consentono agli amministratori Teams di proteggere e regolare l'accesso a contenuti aziendali sensibili creati durante la collaborazione all'interno dei team. Dopo aver configurato le etichette di riservatezza con i criteri associati nel [portale di conformità di Microsoft Purview](/microsoft-365/compliance/go-to-the-securitycompliance-center), queste etichette possono essere applicate ai team dell'organizzazione.

Le etichette di riservatezza non sono attualmente supportate nei team di classe per i clienti che usano SKU di Teams Education. Per altre informazioni sulle licenze, vedere [Microsoft Teams descrizione del servizio](/office365/servicedescriptions/teams-service-description).

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification"></a>Qual è la differenza tra le etichette di riservatezza e la classificazione Teams?

Le etichette di riservatezza sono diverse da Teams classificazione, nota anche come classificazione dei gruppi Azure AD. Le classificazioni sono stringhe di testo che possono essere associate a un gruppo di Microsoft 365 ma a cui non sono associati criteri effettivi. Usare la classificazione come metadati e quindi usare altri metodi, ad esempio gli strumenti interni e gli script, per applicare i criteri.

Il vantaggio dell'uso delle etichette di riservatezza è che i criteri vengono applicati automaticamente end-to-end tramite una combinazione della piattaforma Gruppi di Microsoft 365, del centro conformità e dei servizi di Teams. Le etichette di riservatezza offrono un potente supporto dell'infrastruttura per proteggere i dati sensibili dell'organizzazione e garantire la conformità ai criteri o alle normative interne.

Se attualmente si usa Teams classificazione, vedere la documentazione seguente per altre informazioni e istruzioni su come convertire questi valori in etichette di riservatezza: [classificazione dei gruppi di Azure AD classica](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

## <a name="example-scenarios-for-sensitivity-labels"></a>Scenari di esempio per le etichette di riservatezza

Scenari di esempio per l'uso delle etichette di riservatezza con Teams dell'organizzazione:

- [Impostare il livello di privacy (pubblico o privato) per i team](#set-the-privacy-level-for-teams)
- [Controllare l'accesso guest ai team](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Impostare il livello di privacy per i team

È possibile creare e configurare un'etichetta di riservatezza che, se applicata durante la creazione del team, consente agli utenti di creare team con un'impostazione di privacy specifica (pubblica o privata).

Ad esempio, si crea e si pubblica un'etichetta di riservatezza denominata "Riservato" con l'opzione di privacy dell'etichetta configurata come **Privato**. Di conseguenza, qualsiasi team creato con questa etichetta deve essere un team privato. 

Quando un utente crea un nuovo team e seleziona l'etichetta **Riservato** , l'unica opzione di privacy disponibile per l'utente è **Privato**. Altre opzioni di privacy, ad esempio Pubblica e a livello di organizzazione, non sono disponibili per l'utente per selezionare:

![Screenshot dell'etichetta riservatezza riservata.](media/sensitivity-labels-confidential-example.png)

Analogamente, si crea e si pubblica un'etichetta di riservatezza denominata "Generale" con l'opzione di privacy dell'etichetta configurata come **Pubblica**. Quando un utente crea un nuovo team, può creare team pubblici o a livello di organizzazione solo quando seleziona questa etichetta:

![Screenshot dell'etichetta di riservatezza generale.](media/sensitivity-labels-general-example.png)

Quando viene creato il team, l'etichetta di riservatezza è visibile agli utenti nell'angolo in alto a destra dei canali del team. 

![Screenshot dell'etichetta di riservatezza nel canale del team.](media/sensitivity-labels-channel.png)

Un proprietario del team può modificare l'etichetta di riservatezza e l'impostazione di privacy del team in qualsiasi momento accedendo al team e quindi facendo clic su **Modifica team**.

![Screenshot dell'etichetta di riservatezza nelle proprietà del team.](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Controllare l'accesso guest ai team

È possibile usare le etichette di riservatezza per controllare l'accesso guest ai team. Teams creato con un'etichetta che non consente l'accesso guest sono disponibili solo per gli utenti dell'organizzazione. Le persone esterne all'organizzazione non possono essere aggiunte al team.

## <a name="microsoft-teams-admin-center"></a>interfaccia di amministrazione di Microsoft Teams

È possibile applicare etichette di riservatezza quando si crea o si modifica un team nell'interfaccia di amministrazione di Microsoft Teams. 

Le etichette di riservatezza sono visibili anche nelle proprietà del team e nella colonna **Classificazione** nella pagina **Gestisci team** dell'interfaccia di amministrazione di Microsoft Teams.

## <a name="limitations"></a>Limitazioni

Prima di usare le etichette di riservatezza per Teams, tenere presente le limitazioni seguenti:

- **Le etichette di riservatezza non sono supportate dalle API Teams Graph e dai cmdlet di PowerShell**
    
    Gli utenti non potranno specificare le etichette di riservatezza durante la creazione di team direttamente tramite API Teams Graph o Teams cmdlet di PowerShell. Tuttavia, i gruppi moderni Graph API e i cmdlet di PowerShell consentono la creazione di gruppi con etichette di riservatezza. Questo significa che è possibile creare gruppi con etichette di riservatezza usando questi metodi e quindi convertire questi gruppi in team.

- **Supporto per i canali privati**
    
    I canali privati creati in un team ereditano l'etichetta di riservatezza applicata a un team. La stessa etichetta viene applicata automaticamente alla raccolta siti SharePoint per il canale privato.
    
    Tuttavia, se un utente modifica direttamente l'etichetta di riservatezza in un sito di SharePoint per un canale privato, la modifica dell'etichetta non si riflette nel client Teams. In questo scenario, gli utenti continuano a vedere l'etichetta di riservatezza originale applicata al team nell'intestazione del canale privato.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Come creare e configurare etichette di riservatezza per Teams

Usare le istruzioni della documentazione di Microsoft 365 per creare e configurare etichette di riservatezza per Teams: 

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi Microsoft 365 e siti di SharePoint](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).
