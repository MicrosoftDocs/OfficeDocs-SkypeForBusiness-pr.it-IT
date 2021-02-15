---
title: Etichette di riservatezza per Microsoft Teams
ms.author: mikeplum
author: cabailey
manager: laurawi
ms.reviewer: abgupta
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
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare le etichette di riservatezza per proteggere i team in Microsoft Teams.
ms.openlocfilehash: 3b994bd7f1aa8fbc1fde13aaf49b195a1698695a
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937528"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Etichette di riservatezza per Microsoft Teams

[Le etichette di riservatezza](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) consentono agli amministratori di Teams di proteggere e regolare l'accesso a contenuti aziendali riservati creati durante la collaborazione all'interno dei team. Dopo aver configurato le etichette di riservatezza con i criteri associati nel Centro conformità [Microsoft,](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)queste etichette possono essere applicate ai team dell'organizzazione.

Le etichette di riservatezza non sono attualmente supportate per i clienti che usano SKU di Teams Education. Per altre informazioni sulle licenze, vedere la descrizione [del servizio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Qual è la differenza tra le etichette di riservatezza e le etichette di classificazione dei team?

Le etichette di riservatezza sono diverse dalle etichette di classificazione, anche note come classificazione dei gruppi di Azure AD. Le etichette di classificazione sono stringhe di testo che possono essere associate a un gruppo di Microsoft 365 ma a cui non sono associati criteri effettivi. Usare le etichette di classificazione come metadati e quindi usare altri metodi, ad esempio script e strumenti interni, per applicare i criteri.

Il vantaggio di usare le etichette di riservatezza è che i criteri vengono applicati automaticamente end-to-end attraverso una combinazione della piattaforma Gruppi di Microsoft 365, del Centro conformità e dei servizi di Teams. Le etichette di riservatezza forniscono un potente supporto dell'infrastruttura per proteggere i dati sensibili dell'organizzazione e garantire la conformità alle normative o ai criteri interni.

Se attualmente si usano etichette di classificazione, vedere la documentazione seguente per altre informazioni e istruzioni su come eseguirne la migrazione alle etichette di riservatezza: classificazione classica dei gruppi [di Azure AD.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)

## <a name="example-scenarios-for-sensitivity-labels"></a>Scenari di esempio per le etichette di riservatezza

Scenari di esempio per l'uso delle etichette di riservatezza con Teams nell'organizzazione:

- [Impostare il livello di privacy (pubblico o privato) per i team](#set-the-privacy-level-for-teams)
- [Controllare l'accesso guest ai team](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Impostare il livello di privacy per i team

È possibile creare e configurare un'etichetta di riservatezza che, se applicata durante la creazione del team, consente agli utenti di creare team con una specifica impostazione di privacy (pubblica o privata).

Ad esempio, è possibile creare e pubblicare un'etichetta di riservatezza denominata "Riservato" per cui l'opzione di privacy dell'etichetta è configurata come **Privata.** Di conseguenza, qualsiasi team creato con questa etichetta deve essere un team privato. 

Quando un utente crea un nuovo  team e seleziona l'etichetta Riservato, l'unica opzione di privacy disponibile per l'utente è **Privata.** Altre opzioni sulla privacy, ad esempio Pubblico e A livello di organizzazione, non sono disponibili per l'utente di selezionare:

![Screenshot dell'etichetta riservatezza](media/sensitivity-labels-confidential-example.png)

Allo stesso modo, si crea e si pubblica un'etichetta di riservatezza denominata "Generale" con l'opzione di privacy dell'etichetta configurata come **Pubblica.** Quando un utente crea un nuovo team, può creare team pubblici o a livello di organizzazione solo quando seleziona questa etichetta:

![Screenshot dell'etichetta di riservatezza Generale](media/sensitivity-labels-general-example.png)

Quando viene creato un team, l'etichetta di riservatezza è visibile nell'angolo in alto a destra dei canali del team.

![Screenshot dell'etichetta di riservatezza nel canale del team](media/sensitivity-labels-channel.png)

Il proprietario di un team può modificare l'etichetta di riservatezza e l'impostazione di privacy del team in qualsiasi momento, andando al team e quindi facendo clic **su Modifica team.**

![Screenshot dell'etichetta di riservatezza nelle proprietà del team](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Controllare l'accesso guest ai team

È possibile usare le etichette di riservatezza per controllare l'accesso dei guest ai team. I team creati con un'etichetta che non consente l'accesso guest sono disponibili solo per gli utenti dell'organizzazione. Non è possibile aggiungere persone esterne all'organizzazione al team.

## <a name="microsoft-teams-admin-center"></a>Interfaccia di amministrazione di Microsoft Teams

È possibile applicare etichette di riservatezza quando si crea o si modifica un team nell'interfaccia di amministrazione di Microsoft Teams. 

Le etichette di riservatezza sono visibili anche nelle proprietà del team e nella colonna **Classificazione** nella pagina **Gestisci team** dell'interfaccia di amministrazione di Microsoft Teams.

## <a name="limitations"></a>Limitazioni

Prima di usare le etichette di riservatezza per Teams, tenere presenti le limitazioni seguenti:

- **I nomi delle etichette padre non vengono visualizzati per le etichette secondarie**
    
    Teams supporta le sotto label, ma non visualizza il nome dell'etichetta padre. Ad esempio, **Tutti** \\ **i dipendenti riservati viene** visualizzato come Tutti i **dipendenti.**

- **Le etichette di riservatezza non sono supportate dalle API Di Teams Graph, dai cmdlet di PowerShell e dai modelli**
    
    Gli utenti non saranno in grado di applicare etichette di riservatezza ai team creati direttamente tramite API Graph di Teams, cmdlet di Teams PowerShell e modelli di Teams.

- **Supporto per canali privati**
    
    I canali privati creati in un team ereditano l'etichetta di riservatezza applicata a un team. La stessa etichetta viene applicata automaticamente alla raccolta siti di SharePoint per il canale privato.
    
    Tuttavia, se un utente modifica direttamente l'etichetta di riservatezza in un sito di SharePoint per un canale privato, la modifica dell'etichetta non viene riflessa nel client di Teams. In questo scenario, gli utenti continuano a vedere l'etichetta di riservatezza originale applicata al team nell'intestazione del canale privato.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Come creare e configurare le etichette di riservatezza per Teams

Usare le istruzioni della documentazione di Microsoft 365 per creare e configurare etichette di riservatezza per Teams: 

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)
