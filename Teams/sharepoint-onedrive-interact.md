---
title: Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & l'interazione di OneDrive for Business con Teams; Archiviazione di file di chat privata &'interazione tra team, canale standard, & raccolta documenti.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d063cae8b87ffcacd63676da17fc000384c432c
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948624"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams

> [!Tip]
> Per informazioni sull’interazione tra Teams e Azure Active Directory (AAD), i Gruppi di Microsoft 365, Exchange, SharePoint e OneDrive for Business, vedere la sessione: [Nozioni di base di Microsoft Teams](https://aka.ms/teams-foundations)

Ogni team in Microsoft Teams ha un sito del team in SharePoint Online e ogni canale standard di un team ottiene una cartella all'interno della raccolta documenti predefinita del sito del team. I file condivisi in una conversazione vengono aggiunti automaticamente alla raccolta documenti e le autorizzazioni e opzioni di sicurezza per i file impostate in SharePoint vengono applicate automaticamente all'interno di Teams. Per vedere l'impatto della modifica dell'indirizzo di un sito in SharePoint, vedere [Modificare l'indirizzo di un sito.](/sharepoint/change-site-address)

> [!NOTE]
> Questo articolo si applica solo ai canali standard. L'architettura per i canali privati è diversa dai canali standard. Ogni canale privato ha una raccolta siti di SharePoint separata dal sito del team padre. Per altre informazioni, vedere [Canali privati in Microsoft Teams.](private-channels.md)

I file di chat privati vengono archiviati nella cartella OneDrive for Business del mittente e le autorizzazioni vengono concesse automaticamente a tutti i partecipanti nell'ambito del processo di condivisione dei file.

Se gli utenti non vengono assegnati e abilitati tramite licenze di SharePoint Online, non possono sfruttare l'archiviazione OneDrive for Business in Microsoft 365 o Office 365. La condivisione di file continuerà a funzionare nei canali standard, ma gli utenti non potranno condividere file nelle chat senza spazio di archiviazione di OneDrive for Business in Microsoft 365 o Office 365.

Archiviando i file nella raccolta documenti di SharePoint Online e in OneDrive for Business, verranno rispettate tutte le regole di conformità configurate a livello di tenant. 

> [!NOTE]
> Al momento l'integrazione con SharePoint locale non è supportata per Microsoft Teams.

Di seguito è riportato l'esempio di relazioni tra il team, il canale standard e la raccolta documenti.

Per ogni team viene creato un sito di SharePoint e la cartella Documenti **condivisi** è la cartella predefinita creata per il team. Ogni canale standard, incluso **il canale Generale** (il canale predefinito per ogni team), ha una cartella in Documenti **condivisi.**

![Diagramma delle cartelle Documenti condivisi in SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> Al momento non è possibile sostituire il sito e la raccolta documenti di SharePoint predefiniti con un altro. Abbiamo sentito da te che lo desideri, e lo stiamo valutando. Consulta la [roadmap di Teams](https://aka.ms/teamsroadmap) o Teams [UserVoice](https://aka.ms/TeamsUserVoice) per essere sempre al corrente delle funzionalità imminenti.

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

> [!TIP]
> Per aggiungere al team una scheda collegata a una pagina del sito di SharePoint esistente o alla raccolta documenti di SharePoint esistente:
> 1. Selezionare il segno più accanto alle schede.
> 2. Selezionare **SharePoint per** una pagina del sito di SharePoint esistente o una **raccolta documenti** per una raccolta documenti esistente.
> 3. Selezionare la pagina o la raccolta documenti appropriata.

Per ogni utente, la cartella OneDrive File chat di **Microsoft Teams** viene usata per archiviare tutti i file condivisi all'interno di chat private con altri utenti (1:1 o 1:molti), con le autorizzazioni configurate automaticamente per limitare l'accesso solo all'utente previsto.

![Diagramma della cartella OneDrive denominata File di chat di Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

Si noti che per i team pubblici, viene eseguito il provisioning del sito del team di SharePoint con accesso "Tutti tranne gli utenti esterni". Il team pubblico non viene visualizzato in Teams per le persone che non sono membri del team. Tuttavia, possono accedere al contenuto del sito del team di SharePoint usando l'URL del sito del team di SharePoint. 

## <a name="channel-files-tab"></a>Scheda File del canale

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

La **scheda File** in Teams è molto simile alla visualizzazione documenti di SharePoint. Nella scheda **File** gli utenti possono:

- Vedere altre opzioni **nel** menu Nuovo file.
- Sincronizzare i file con l'unità locale.
- Nel menu **Tutti i documenti** passare dalla visualizzazione **Elenco** alla visualizzazione **Elenco compatto** alla **visualizzazione** Riquadri.
- Identificare i file che necessitano di attenzione o che hanno malware.
- Verificare immediatamente se un file è di sola lettura o estratto.
- Estrarre e archiviare i file.
- Aggiungere, rimuovere e modificare l'ordinamento dei file.
- Identificare i file che necessitano di metadati
- Scegliere tra molte altre opzioni di filtro.
- Raggruppare i file in base alle intestazioni di colonna.
- Modificare le impostazioni delle colonne (spostarsi a sinistra o a destra, nascondere) e la larghezza delle colonne.

## <a name="default-link-type-setting"></a>Impostazione del tipo di collegamento predefinito

SharePoint e OneDrive hanno un'impostazione di amministratore per specificare il tipo di collegamento predefinito per i collegamenti creati per un file. Teams adotta lo stesso approccio riutilizzando le impostazioni impostate dall'amministratore per SharePoint e OneDrive. Per altre informazioni su questo approccio, vedere Modificare il tipo di collegamento predefinito quando gli utenti [ottengono collegamenti per la condivisione.](/sharepoint/change-default-sharing-link) 

## <a name="more-information"></a>Altre informazioni

Per altre informazioni sul funzionamento di SharePoint con Teams, vedere [SharePoint e Teams: meglio insieme.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

Per altre informazioni sull'esperienza degli utenti guest in Teams, vedere [Com'è l'esperienza guest.](guest-experience.md)