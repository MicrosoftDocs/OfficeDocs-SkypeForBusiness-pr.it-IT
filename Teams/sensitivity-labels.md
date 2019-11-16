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
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come definire e usare le etichette di sensitività in Microsoft teams.
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653587"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Etichette di sensitività per Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Le [etichette di sensitività](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) consentono agli amministratori di teams di regolare l'accesso a contenuto aziendale sensibile creato durante la collaborazione in teams. È possibile definire le etichette di sensitività e i criteri associati nel [centro conformità & sicurezza](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center). Queste etichette e criteri vengono applicati automaticamente ai team dell'organizzazione.  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Qual è la differenza tra etichette di sensitività e etichette di classificazione di Teams?

Le etichette di sensitività sono diverse dalle etichette di classificazione che richiedono di crearle usando PowerShell. Le etichette di classificazione sono stringhe di testo che possono essere associate a un gruppo, ma non sono associate a criteri effettivi. Le etichette di classificazione vengono usate come metadati per applicare manualmente i criteri tramite gli script e gli strumenti interni.

D'altra parte, le etichette di sensitività e i relativi criteri vengono applicati automaticamente da un lato all'altro tramite una combinazione della piattaforma groups, della Security & Compliance Center e dei servizi teams. Le etichette di sensitività includono un potente supporto per l'infrastruttura per proteggere i dati sensibili dell'organizzazione.  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a>Creare e pubblicare etichette di sensitività per Teams

Per informazioni su come abilitare, creare e pubblicare etichette di sensitività per i team, vedere [usare le etichette di sensitività con Microsoft teams, i gruppi di Office 365 e i siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

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