---
title: Come interagire con SharePoint Online e OneDrive for business con Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & interazione di OneDrive for business con teams; archiviazione di file di chat privata & interazione tra team, canale standard & raccolta documenti.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fd34bf368667fcfa5776de40cad0d1444440805a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137256"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Come interagire con SharePoint Online e OneDrive for business con Microsoft Teams

> [!Tip]
> Per informazioni su come interagire con i team con Azure Active Directory (AAD), Office 365 groups, Exchange, SharePoint e OneDrive for business, vedere la sessione seguente: [fondazioni di Microsoft teams](https://aka.ms/teams-foundations)

Ogni team di Microsoft Teams ha un sito del team in SharePoint Online e ogni canale standard in un team ottiene una cartella nella raccolta documenti del sito del team predefinita. I file condivisi in una conversazione vengono aggiunti automaticamente alla raccolta documenti e le autorizzazioni e opzioni di sicurezza per i file impostate in SharePoint vengono applicate automaticamente all'interno di Teams. Per vedere l'impatto della modifica di un indirizzo del sito in SharePoint, leggere [modificare l'indirizzo del sito](https://docs.microsoft.com/sharepoint/change-site-address).

> [!NOTE]
> Questo articolo si applica solo ai canali standard. L'architettura per i canali privati è diversa dai canali standard. Ogni canale privato ha una propria raccolta siti di SharePoint separata dal sito del team padre. Per altre informazioni, vedere [canali privati in Microsoft teams](private-channels.md).

I file di chat privati sono archiviati nella cartella OneDrive for business del mittente e le autorizzazioni vengono concesse automaticamente a tutti i partecipanti nell'ambito del processo di condivisione file.

Se gli utenti non sono assegnati e abilitati con le licenze di SharePoint Online, non hanno spazio di archiviazione di OneDrive for business in Office 365. La condivisione dei file continuerà a funzionare nei canali standard, ma gli utenti non potranno condividere file in chat senza spazio di archiviazione di OneDrive for business in Office 365.

Archiviando i file nella raccolta documenti di SharePoint Online e in OneDrive for Business, verranno rispettate tutte le regole di conformità configurate a livello di tenant. 

> [!NOTE]
> L'integrazione con SharePoint locale non è supportata per Microsoft teams in questo momento.

Di seguito è riportato l'esempio di relazioni tra team, canale standard e raccolta documenti.

Per ogni team, viene creato un sito di SharePoint e la cartella **documenti condivisi** è la cartella predefinita creata per il team. Ogni canale standard, incluso il canale **generale** (il canale predefinito per ogni team) ha una cartella in **documenti condivisi**.

![Diagramma delle cartelle documenti condivisi in SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> Non è attualmente possibile sostituire il sito e la raccolta documenti predefiniti di SharePoint con un altro. Abbiamo sentito da te che vuoi, e lo stiamo considerando. Controlla la [Roadmap teams](https://aka.ms/teamsroadmap) o i [Teams UserVoice](https://aka.ms/TeamsUserVoice) per rimanere in primo piano sulle caratteristiche future.

> [!TIP]
> Per aggiungere una scheda al team che si collega a una pagina del sito di SharePoint esistente o alla raccolta documenti di SharePoint esistente:
> 1. Selezionare il segno più accanto alle schede.
> 2. Selezionare **SharePoint** per una pagina del sito di SharePoint o una **raccolta documenti** esistente per una raccolta documenti esistente.
> 3. Selezionare la pagina o la raccolta documenti appropriata.

Per ogni utente, la cartella OneDrive **file di chat di Microsoft teams** viene usata per archiviare tutti i file condivisi all'interno di chat private con altri utenti (1:1 o 1: many), con le autorizzazioni configurate automaticamente per limitare l'accesso solo all'utente previsto.

![Diagramma della cartella OneDrive denominata file di chat di Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>Scheda file di canale

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

La scheda **file** in teams è simile alla visualizzazione documenti di SharePoint. Nella scheda **file** , gli utenti possono:

- Vedere Opzioni aggiuntive nel menu **nuovo** file.
- Sincronizzare i file con l'unità locale.
- Nel menu **tutti i documenti** , passare dalla **visualizzazione elenco** a **elenco compatto** alla visualizzazione **riquadri** .
- Identificare i file che richiedono attenzione o avere malware.
- Verificare immediatamente se un file è di sola lettura o estratto.
- Estrarre e archiviare i file.
- Aggiungere il PIN, sbloccare e modificare l'ordinamento dei file.
- Identificare i file necessari per i metadati
- Scegliere tra molte altre opzioni di filtro.
- Raggruppare i file in base alle intestazioni di colonna.
- Modificare le impostazioni di colonna (spostati a sinistra o a destra, Nascondi) e larghezza colonna.

## <a name="default-link-type-setting"></a>Impostazione del tipo di collegamento predefinito

SharePoint e OneDrive hanno un'impostazione di amministratore per specificare il tipo di collegamento predefinito per i collegamenti creati per un file. Teams adotta lo stesso approccio riutilizzando le impostazioni impostate dall'amministratore per SharePoint e OneDrive. Altre informazioni su questo approccio sono descritte in [modificare il tipo di collegamento predefinito quando gli utenti ottengono collegamenti per la condivisione](https://docs.microsoft.com/sharepoint/change-default-sharing-link). 

## <a name="more-information"></a>Altre informazioni

Per altre informazioni sul funzionamento di SharePoint con i team, vedere [SharePoint e teams: meglio insieme](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).

Per altre informazioni sull'esperienza Guest in teams, leggere [l'esperienza Guest](guest-experience.md).

