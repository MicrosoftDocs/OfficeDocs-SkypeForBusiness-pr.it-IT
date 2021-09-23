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
ms.openlocfilehash: 135049e80d6a8c0e008886ca924cca64b5943695
ms.sourcegitcommit: 9fd9cfe3683503f3c35ad5591324396e2532caef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2021
ms.locfileid: "59496693"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Etichette di riservatezza per Microsoft Teams

[Le etichette di riservatezza](/microsoft-365/compliance/sensitivity-labels) consentono Teams amministratori di proteggere e regolare l'accesso a contenuti aziendali riservati creati durante la collaborazione all'interno dei team. Dopo aver configurato le etichette di riservatezza con i criteri associati nel Centro conformità [Microsoft,](/microsoft-365/compliance/go-to-the-securitycompliance-center)queste etichette possono essere applicate ai team dell'organizzazione.

Le etichette di riservatezza non sono attualmente supportate nei team di classe per i clienti Teams SKU Education. Per altre informazioni sulle licenze, vedere la [descrizione Microsoft Teams servizio.](/office365/servicedescriptions/teams-service-description)

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification"></a>Qual è la differenza tra le etichette di riservatezza e Teams classificazione?

Le etichette di riservatezza sono diverse dalla Teams, nota anche come classificazione dei gruppi di Azure AD. Le classificazioni sono stringhe di testo che possono essere associate a un gruppo Microsoft 365 ma a cui non sono associati criteri effettivi. Si usa la classificazione come metadati e quindi è necessario usare altri metodi, ad esempio strumenti interni e script, per applicare i criteri.

Il vantaggio dell'uso delle etichette di riservatezza è che i criteri vengono applicati automaticamente end-to-end tramite una combinazione della piattaforma gruppi di Microsoft 365, del Centro conformità e dei servizi di Teams. Le etichette di riservatezza offrono un potente supporto dell'infrastruttura per proteggere i dati sensibili dell'organizzazione e garantire la conformità ai criteri o alle normative interne.

Se attualmente si usa la classificazione Teams, vedere la documentazione seguente per altre informazioni e istruzioni su come convertire questi valori in etichette di riservatezza: classificazione classica dei gruppi di [Azure AD.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)

## <a name="example-scenarios-for-sensitivity-labels"></a>Scenari di esempio per le etichette di riservatezza

Scenari di esempio per l'uso delle etichette di riservatezza con Teams nell'organizzazione:

- [Impostare il livello di privacy (pubblico o privato) per i team](#set-the-privacy-level-for-teams)
- [Controllare l'accesso guest ai team](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Impostare il livello di privacy per i team

È possibile creare e configurare un'etichetta di riservatezza che, se applicata durante la creazione del team, consente agli utenti di creare team con una specifica impostazione di privacy (pubblica o privata).

Ad esempio, è possibile creare e pubblicare un'etichetta di riservatezza denominata "Riservato" con l'opzione di privacy dell'etichetta configurata come **Privato.** Di conseguenza, qualsiasi team creato con questa etichetta deve essere un team privato. 

Quando un utente crea un nuovo  team e seleziona l'etichetta Riservato, l'unica opzione di privacy disponibile per l'utente è **Privato.** Altre opzioni di privacy, ad esempio Pubblico e A livello di organizzazione, non sono disponibili per l'utente:

![Screenshot dell'etichetta riservatezza.](media/sensitivity-labels-confidential-example.png)

Analogamente, si crea e si pubblica un'etichetta di riservatezza denominata "Generale" con l'opzione di privacy dell'etichetta configurata come **Pubblico.** Quando un utente crea un nuovo team, può creare team pubblici o a livello di organizzazione solo quando seleziona questa etichetta:

![Screenshot dell'etichetta di riservatezza Generale.](media/sensitivity-labels-general-example.png)

Quando il team viene creato, l'etichetta di riservatezza è visibile agli utenti nell'angolo in alto a destra dei canali del team. 

![Screenshot dell'etichetta di riservatezza nel canale del team.](media/sensitivity-labels-channel.png)

Il proprietario di un team può modificare l'etichetta di riservatezza e l'impostazione della privacy del team in qualsiasi momento andando al team e quindi facendo clic **su Modifica team.**

![Screenshot dell'etichetta di riservatezza nelle proprietà del team.](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Controllare l'accesso guest ai team

È possibile usare le etichette di riservatezza per controllare l'accesso dei guest ai team. Teams creati con un'etichetta che non consente l'accesso guest sono disponibili solo per gli utenti dell'organizzazione. Le persone esterne all'organizzazione non possono essere aggiunte al team.

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams di amministrazione

È possibile applicare etichette di riservatezza quando si crea o si modifica un team nell'Microsoft Teams di amministrazione. 

Le etichette di riservatezza sono visibili anche nelle proprietà del team e nella colonna **Classificazione** nella pagina Gestisci **team** dell'Microsoft Teams di amministrazione.

## <a name="limitations"></a>Limitazioni

Prima di usare le etichette di riservatezza per Teams, tenere presenti le limitazioni seguenti:

- **Le etichette di riservatezza non sono supportate dalle API Teams Graph, dai cmdlet di PowerShell e dai modelli**
    
    Gli utenti non saranno in grado di specificare le etichette di riservatezza durante la creazione di team direttamente tramite api Teams Graph, cmdlet Teams PowerShell e Teams modelli. Tuttavia, i Graph moderni e i cmdlet di PowerShell consentono la creazione di gruppi con etichette. In questo modo gli utenti possono prima creare gruppi con etichette usando le API di Graph o i cmdlet di PowerShell e quindi convertire questi gruppi in Teams.

- **Supporto per i canali privati**
    
    I canali privati creati in un team ereditano l'etichetta di riservatezza applicata a un team. La stessa etichetta viene applicata automaticamente nella raccolta siti SharePoint per il canale privato.
    
    Tuttavia, se un utente modifica direttamente l'etichetta di riservatezza in un sito di SharePoint per un canale privato, tale modifica non viene riflessa nel client Teams. In questo scenario, gli utenti continuano a vedere l'etichetta di riservatezza originale applicata al team nell'intestazione del canale privato.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Come creare e configurare etichette di riservatezza per Teams

Usare le istruzioni della documentazione Microsoft 365 per creare e configurare le etichette di riservatezza per Teams: 

- Usare le etichette di riservatezza per proteggere il contenuto [in Microsoft Teams, Microsoft 365 gruppi e SharePoint siti.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)
