---
title: Etichette di sensitività per Microsoft Teams
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
description: Informazioni su come usare le etichette di sensitività per proteggere i team in Microsoft teams.
ms.openlocfilehash: 3b994bd7f1aa8fbc1fde13aaf49b195a1698695a
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937528"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Etichette di sensitività per Microsoft Teams

Le [etichette di sensitività](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) consentono agli amministratori di teams di proteggere e regolare l'accesso a contenuto aziendale sensibile creato durante la collaborazione all'interno di teams. Dopo aver configurato le etichette di sensitività con i criteri associati nel [centro conformità Microsoft](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), queste etichette possono essere applicate ai team dell'organizzazione.

Le etichette di sensitività non sono attualmente supportate per i clienti che usano SKU per l'istruzione teams. Per ulteriori informazioni sulle licenze, vedere [Descrizione del servizio Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Qual è la differenza tra etichette di sensitività e etichette di classificazione di Teams?

Le etichette di sensitività sono diverse dalle etichette di classificazione, note anche come classificazione dei gruppi di Azure AD. Le etichette di classificazione sono stringhe di testo che possono essere associate a un gruppo di Microsoft 365, ma non sono associate a criteri effettivi. Si usano le etichette di classificazione come metadati e quindi si devono usare altri metodi, ad esempio strumenti interni e script, per applicare i criteri.

Il vantaggio derivante dall'uso di etichette di sensitività è che i loro criteri vengono applicati automaticamente tramite una combinazione della piattaforma Microsoft 365 groups, del centro conformità e dei servizi teams. Le etichette di sensitività includono un potente supporto per l'infrastruttura per proteggere i dati sensibili dell'organizzazione e garantire la conformità con i criteri interni o le normative.

Se attualmente si usano le etichette di classificazione, vedere la documentazione seguente per altre informazioni e istruzioni su come eseguire la migrazione a etichette di sensitività: [classificazione dei gruppi di Azure ad classica](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

## <a name="example-scenarios-for-sensitivity-labels"></a>Scenari di esempio per le etichette di sensitività

Scenari di esempio su come usare le etichette di sensitività con i team dell'organizzazione:

- [Impostare il livello di privacy (pubblico o privato) per i team](#set-the-privacy-level-for-teams)
- [Controllare l'accesso Guest ai team](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Impostare il livello di privacy per Teams

È possibile creare e configurare un'etichetta di sensitivity che, se applicata durante la creazione del team, consente agli utenti di creare team con un'impostazione privacy specifica (pubblica o privata).

Ad esempio, è possibile creare e pubblicare un'etichetta di sensitività denominata "Confidential" con l'opzione per la privacy dell'etichetta configurata come **privata**. Di conseguenza, qualsiasi team creato con questa etichetta deve essere un team privato. 

Quando un utente crea un nuovo team e seleziona l'etichetta **riservata** , l'unica opzione per la privacy disponibile per l'utente è **privata**. Altre opzioni di privacy, ad esempio pubblica e a livello di organizzazione, non sono disponibili per l'utente per selezionare:

![Screenshot dell'etichetta di sensitivity Confidential](media/sensitivity-labels-confidential-example.png)

Analogamente, è possibile creare e pubblicare un'etichetta di sensitività denominata "generale" con l'opzione per la privacy dell'etichetta configurata come **pubblica**. Quando un utente crea un nuovo team, può creare solo team pubblici o a livello di organizzazione quando seleziona questa etichetta:

![Schermata dell'etichetta di sensitività generale](media/sensitivity-labels-general-example.png)

Quando viene creato un team, l'etichetta di sensitività è visibile nell'angolo in alto a destra dei canali del team.

![Screenshot dell'etichetta di sensitivity nel canale del team](media/sensitivity-labels-channel.png)

Un proprietario del team può modificare l'etichetta di sensitività e l'impostazione di privacy del team in qualsiasi momento accedendo al team e quindi fare clic su **modifica team**.

![Screenshot dell'etichetta di sensitivity nelle proprietà del team](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Controllare l'accesso Guest ai team

Puoi usare le etichette di sensitività per controllare l'accesso Guest ai team. I team creati con un'etichetta che non consente l'accesso Guest sono disponibili solo per gli utenti dell'organizzazione. Gli utenti esterni all'organizzazione non possono essere aggiunti al team.

## <a name="microsoft-teams-admin-center"></a>Interfaccia di amministrazione di Microsoft Teams

È possibile applicare etichette di sensitività quando si crea o si modifica un team nell'interfaccia di amministrazione di Microsoft teams. 

Le etichette di sensitività sono visibili anche nelle proprietà del team e nella colonna **classificazione** nella pagina **Gestisci teams** dell'interfaccia di amministrazione di Microsoft teams.

## <a name="limitations"></a>Limitazioni

Prima di usare le etichette di sensitività per i team, tenere presenti le limitazioni seguenti:

- **I nomi di etichetta padre non vengono visualizzati per le sottoetichette**
    
    Teams supporta le sottoetichette ma non Visualizza il nome dell'etichetta padre. Ad esempio, **Confidential** \\ **tutti i dipendenti** vengono visualizzati come **tutti i dipendenti**.

- **Le etichette di sensitività non sono supportate da API del grafico team, cmdlet di PowerShell e modelli**
    
    Gli utenti non potranno applicare etichette di sensitività ai team creati direttamente tramite le API del grafico teams, i cmdlet di PowerShell teams e i modelli teams.

- **Supporto per i canali privati**
    
    I canali privati creati in un team ereditano l'etichetta di sensitività applicata a un team. La stessa etichetta viene applicata automaticamente alla raccolta siti di SharePoint per il canale privato.
    
    Tuttavia, se un utente modifica direttamente l'etichetta di sensitivity in un sito di SharePoint per un canale privato, la modifica dell'etichetta non viene applicata al client teams. In questo scenario, gli utenti continuano a vedere l'etichetta di sensitività originale applicata al team nell'intestazione del canale privato.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Come creare e configurare le etichette di sensitività per i team

Usare le istruzioni della documentazione di Microsoft 365 per creare e configurare etichette di sensitività per i team: 

- [Usare le etichette di sensitività per proteggere il contenuto in Microsoft teams, microsoft 365 Groups e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).
