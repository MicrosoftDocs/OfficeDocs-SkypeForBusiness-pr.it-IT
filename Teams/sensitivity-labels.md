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
ms.openlocfilehash: 407b5f09322cf00e4dfe7a29bd513caa7476623cfeac5099019cc2c3ffb6a248
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54275942"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Etichette di riservatezza per Microsoft Teams

[Le etichette di riservatezza](/microsoft-365/compliance/sensitivity-labels) consentono Teams amministratori di proteggere e regolare l'accesso a contenuti aziendali riservati creati durante la collaborazione all'interno dei team. Dopo aver configurato le etichette di riservatezza con i criteri associati nel Centro conformità [Microsoft,](/microsoft-365/compliance/go-to-the-securitycompliance-center)queste etichette possono essere applicate ai team dell'organizzazione.

Le etichette di riservatezza non sono attualmente supportate nei team di classe per i clienti Teams SKU Education. Per altre informazioni sulle licenze, vedere la [descrizione Microsoft Teams servizio.](/office365/servicedescriptions/teams-service-description)

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Qual è la differenza tra le etichette di riservatezza e Teams classificazioni?

Le etichette di riservatezza sono diverse dalle etichette di classificazione, note anche come classificazione dei gruppi di Azure AD. Le etichette di classificazione sono stringhe di testo che possono essere associate a un gruppo di Microsoft 365 ma a cui non sono associati criteri effettivi. Le etichette di classificazione vengono usate come metadati e quindi è necessario usare altri metodi, ad esempio gli strumenti interni e gli script, per applicare i criteri.

Il vantaggio dell'uso delle etichette di riservatezza è che i criteri vengono applicati automaticamente end-to-end tramite una combinazione della piattaforma gruppi di Microsoft 365, del Centro conformità e dei servizi di Teams. Le etichette di riservatezza offrono un potente supporto dell'infrastruttura per proteggere i dati sensibili dell'organizzazione e garantire la conformità ai criteri o alle normative interne.

Se attualmente si usano etichette di classificazione, vedere la documentazione seguente per altre informazioni e istruzioni su come eseguirne la migrazione alle etichette di riservatezza: Classificazione classica dei gruppi [di Azure AD.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)

## <a name="example-scenarios-for-sensitivity-labels"></a>Scenari di esempio per le etichette di riservatezza

Scenari di esempio per l'uso delle etichette di riservatezza con Teams nell'organizzazione:

- [Impostare il livello di privacy (pubblico o privato) per i team](#set-the-privacy-level-for-teams)
- [Controllare l'accesso guest ai team](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Impostare il livello di privacy per i team

È possibile creare e configurare un'etichetta di riservatezza che, se applicata durante la creazione del team, consente agli utenti di creare team con una specifica impostazione di privacy (pubblica o privata).

Ad esempio, è possibile creare e pubblicare un'etichetta di riservatezza denominata "Riservato" con l'opzione di privacy dell'etichetta configurata come **Privato.** Di conseguenza, qualsiasi team creato con questa etichetta deve essere un team privato. 

Quando un utente crea un nuovo  team e seleziona l'etichetta Riservato, l'unica opzione di privacy disponibile per l'utente è **Privato.** Altre opzioni di privacy, ad esempio Pubblico e A livello di organizzazione, non sono disponibili per l'utente:

![Screenshot dell'etichetta riservatezza](media/sensitivity-labels-confidential-example.png)

Analogamente, si crea e si pubblica un'etichetta di riservatezza denominata "Generale" con l'opzione di privacy dell'etichetta configurata come **Pubblico.** Quando un utente crea un nuovo team, può creare team pubblici o a livello di organizzazione solo quando seleziona questa etichetta:

![Screenshot dell'etichetta di riservatezza Generale](media/sensitivity-labels-general-example.png)

Quando il team viene creato, l'etichetta di riservatezza è visibile nell'angolo in alto a destra dei canali del team. 

> [!NOTE]
> Se si usano etichette gerarchiche padre-figlio, ad esempio "Riservato\Finanze", nell'intestazione del canale verrà visualizzata solo l'etichetta padre.

![Screenshot dell'etichetta di riservatezza nel canale del team](media/sensitivity-labels-channel.png)

Il proprietario di un team può modificare l'etichetta di riservatezza e l'impostazione della privacy del team in qualsiasi momento andando al team e quindi facendo clic **su Modifica team.**

![Screenshot dell'etichetta di riservatezza nelle proprietà del team](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Controllare l'accesso guest ai team

È possibile usare le etichette di riservatezza per controllare l'accesso dei guest ai team. Teams creati con un'etichetta che non consente l'accesso guest sono disponibili solo per gli utenti dell'organizzazione. Le persone esterne all'organizzazione non possono essere aggiunte al team.

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams di amministrazione

È possibile applicare etichette di riservatezza quando si crea o si modifica un team nell'Microsoft Teams di amministrazione. 

Le etichette di riservatezza sono visibili anche nelle proprietà del team e nella colonna **Classificazione** nella pagina Gestisci **team** dell'Microsoft Teams di amministrazione.

## <a name="limitations"></a>Limitazioni

Prima di usare le etichette di riservatezza per Teams, tenere presenti le limitazioni seguenti:

- **I nomi delle etichette padre non vengono visualizzati per le etichette secondarie**
    
    Teams supporta le etichette secondarie, ma non visualizza il nome dell'etichetta padre. Ad esempio, **Tutti** \\ **i dipendenti riservati** viene visualizzato come Tutti i **dipendenti**.

- **Le etichette di riservatezza non sono supportate dalle API Teams Graph, dai cmdlet di PowerShell e dai modelli**
    
    Gli utenti non saranno in grado di specificare le etichette di riservatezza durante la creazione di team direttamente tramite api Teams Graph, cmdlet Teams PowerShell e modelli Teams di protezione. Tuttavia, i Graph moderni e i cmdlet di PowerShell consentono la creazione di gruppi con etichette. In questo modo gli utenti possono prima creare gruppi con etichette usando Graph API o cmdlet di PowerShell e quindi convertire questi gruppi in Teams.

- **Supporto per i canali privati**
    
    I canali privati creati in un team ereditano l'etichetta di riservatezza applicata a un team. La stessa etichetta viene applicata automaticamente nella raccolta SharePoint per il canale privato.
    
    Tuttavia, se un utente modifica direttamente l'etichetta di riservatezza in un sito di SharePoint per un canale privato, la modifica dell'etichetta non viene riflessa nel client Teams. In questo scenario, gli utenti continuano a vedere l'etichetta di riservatezza originale applicata al team nell'intestazione del canale privato.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Come creare e configurare etichette di riservatezza per Teams

Usare le istruzioni della documentazione Microsoft 365 per creare e configurare le etichette di riservatezza per Teams: 

- [Usare le etichette di riservatezza per proteggere il contenuto in Microsoft Teams, Microsoft 365 gruppi](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)e SharePoint siti.
