---
title: Etichette di sensitività per Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
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
description: Informazioni su come definire e usare le etichette di sensitività in Microsoft teams.
ms.openlocfilehash: e9f007fd174027443191cd7d2dbb8f8321c7424f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888735"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Etichette di sensitività per Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Le [etichette di sensitività](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) consentono agli amministratori di teams di regolare l'accesso a contenuto aziendale sensibile creato durante la collaborazione in teams. È possibile definire le etichette di sensitività e i criteri associati nel [centro conformità & sicurezza](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center). Queste etichette e criteri vengono applicati automaticamente ai team dell'organizzazione.  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Qual è la differenza tra etichette di sensitività e etichette di classificazione di Teams?

Le etichette di sensitività sono diverse dalle etichette di classificazione che richiedono di crearle usando PowerShell. Le etichette di classificazione sono stringhe di testo che possono essere associate a un gruppo, ma non sono associate a criteri effettivi. Le etichette di classificazione vengono usate come metadati per applicare manualmente i criteri tramite gli script e gli strumenti interni.

D'altra parte, le etichette di sensitività e i relativi criteri vengono applicati automaticamente da un lato all'altro tramite una combinazione della piattaforma groups, della Security & Compliance Center e dei servizi teams. Le etichette di sensitività includono un potente supporto per l'infrastruttura per proteggere i dati sensibili dell'organizzazione.  

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>Creare, gestire e pubblicare etichette di sensitività per i team

Per informazioni su come abilitare, creare e pubblicare etichette di sensitività per i team, vedere [usare le etichette di sensitività con Microsoft teams, i gruppi di Office 365 e i siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

>[!IMPORTANT]
>La creazione, l'aggiornamento e l'eliminazione di etichette di sensibilità richiedono un'accurata sequenziazione con le etichette di pubblicazione agli utenti. Qualsiasi deviazione nella sequenza può causare errori permanenti per la creazione di team per tutti gli utenti. Pertanto, è fondamentale eseguire le operazioni seguenti quando si <a href="#createpublishlabels">creano e si pubblicano etichette</a>, si <a href="#modifydeletelabels">modificano ed eliminano le etichette pubblicate</a>e si <a href="#manageerrors">gestiscono gli errori di creazione del team</a>.

**Creare e pubblicare etichette** <a name="createpublishlabels"></a>

Quando un'etichetta viene creata e pubblicata nel centro conformità & sicurezza, può richiedere fino a 24 ore affinché l'etichetta diventi visibile nell'interfaccia di creazione di teams. Eseguire la procedura seguente per pubblicare l'etichetta per tutti gli utenti del tenant:
1. Creare l'etichetta e pubblicarla per alcuni account utente selezionati nel tenant.
2. Quando l'etichetta viene pubblicata, attendere 24 ore.
3. Dopo 24 ore, provare a creare un team con l'etichetta utilizzando uno degli account utente che hanno accesso all'etichetta.
4. Se il team ha creato correttamente il passaggio 3, procedere e pubblicare l'etichetta per gli utenti rimanenti nel tenant.

**Modificare ed eliminare le etichette pubblicate** <a name="modifydeletelabels"></a>

L'eliminazione o la modifica dell'etichetta mentre è associata ai criteri di sensitività può causare errori di creazione del team in tutto il tenant. Di conseguenza, prima di eliminare o modificare un'etichetta, devi prima dissociarla dai criteri associati. Eseguire la procedura seguente  
per eliminare o modificare un'etichetta:
1. Rimuovere l'etichetta da tutti i criteri che usano l'etichetta. In alternativa, puoi anche eliminare i criteri stessi.
2. Quando l'etichetta viene rimossa dai criteri o i criteri vengono eliminati, attendere 48 ore prima di procedere ulteriormente.
3. Dopo 48 ore, avviare l'interfaccia di creazione del team e verificare che l'etichetta non sia più visibile per gli utenti del tenant.
4. A questo punto è possibile eliminare o modificare in modo sicuro l'etichetta.

**Gestire gli errori** <a name="manageerrors"></a> di creazione del team

Se la creazione del team inizia a non riuscire in qualsiasi momento durante l'anteprima pubblica, sono disponibili due opzioni:
 - Assicurarsi che le etichette di sensitività non siano obbligatorie per gli utenti durante la creazione del team.
 - Disattivare le etichette di sensitività usando gli script in [Enable this Preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).

Tieni presente che l'impostazione EnableMIPLabels deve essere impostata su false come indicato di seguito:

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a>Uso di etichette di sensitività con teams

Ecco alcuni esempi di scenari in cui è possibile usare le etichette di sensitività con i team dell'organizzazione.

### <a name="privacy-setting-of-teams"></a>Impostazione della privacy di Teams

È possibile creare un'etichetta di sensitivity che, se applicata durante la creazione del team, consente agli utenti di creare team con un'impostazione di privacy (pubblica o privata) specifica.

Ad esempio, è possibile creare un'etichetta denominata "Confidential" nel centro conformità & sicurezza e configurare teams in modo che qualsiasi team creato con questa etichetta debba essere un team privato. Quando un utente crea un nuovo team e seleziona l'etichetta **riservata** , l'unica opzione per la privacy disponibile per l'utente è **privata**. Altre opzioni di privacy, ad esempio pubblica e a livello di organizzazione, sono disabilitate per l'utente.

![Screenshot dell'etichetta di sensitivity Confidential](media/sensitivity-labels-confidential-example.png)

Allo stesso modo, se l'utente seleziona **generale** quando crea un nuovo team, può creare solo team pubblici o a livello di organizzazione.

![Schermata dell'etichetta di sensitività generale](media/sensitivity-labels-general-example.png)

Quando il team viene creato, l'etichetta di sensitività è visibile nell'angolo in alto a destra dei canali del team.

![Screenshot dell'etichetta di sensitivity nel canale del team](media/sensitivity-labels-channel.png)

Un proprietario del team può modificare l'etichetta di sensitività e l'impostazione di privacy del team in qualsiasi momento accedendo al team e quindi facendo clic su **modifica team**.

![Screenshot dell'etichetta di sensitivity nel canale del team](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>Accesso Guest ai team

Puoi specificare se un team creato con una specifica etichetta consente l'accesso guest. I team creati con un'etichetta che non consente l'accesso Guest sono disponibili solo per gli utenti dell'organizzazione. Gli utenti esterni all'organizzazione non possono essere aggiunti al team.

## <a name="known-issues"></a>Problemi noti

**Supporto per le etichette di sensitività nell'interfaccia di amministrazione di Microsoft Teams**

Attualmente, le etichette di sensitività non sono supportate nell'interfaccia di amministrazione di Microsoft teams. Se si usano le etichette di sensitività, non sarà possibile impostare le etichette di sensibilità quando si crea o si modifica un team. Anche le etichette di sensitività non sono visibili nelle proprietà del team e non saranno visibili nella colonna **classificazione** nell'interfaccia di amministrazione di Microsoft teams.

**Supporto per le etichette di sensitività nelle API del grafico teams, cmdlet e modelli di PowerShell**

Attualmente gli utenti non potranno applicare etichette di sensitività ai team creati direttamente tramite API grafico, cmdlet di PowerShell e modelli.

**Modifica di etichette di sensitività direttamente in una raccolta siti di SharePoint per canali privati**

I canali privati creati in un team ereditano l'etichetta di sensitività applicata a un team. Inoltre, la stessa etichetta viene applicata automaticamente alla raccolta siti di SharePoint per il canale privato.

Se un utente aggiorna direttamente l'etichetta di sensitivity in una raccolta siti di SharePoint per un canale privato, tale etichetta non viene aggiornata nel client teams. In questo scenario, gli utenti continueranno a vedere l'etichetta di sensitività applicata a un team nell'intestazione del canale privato.

**Tempi di propagazione per le modifiche applicate alle etichette di sensitività all'esterno dell'app Teams**

Le modifiche apportate alle etichette di sensitività all'esterno dell'app teams possono richiedere fino a 24 ore per riflettere nell'app teams. Questo vale per tutte le modifiche apportate per abilitare o disabilitare le etichette per un tenant, le modifiche apportate ai nomi delle etichette, alle impostazioni e ai criteri.

Inoltre, le modifiche apportate a un'etichetta direttamente a un gruppo o a una raccolta siti di SharePoint che il team può richiedere fino a 24 ore per propagarsi all'app teams.
