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
description: Interazione tra SharePoint Online & e OneDrive for Business con Teams; archiviazione di file di chat privata & l'interazione tra il team, il canale standard e & raccolta documenti.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ff18a0645f81d1892e246ee7432d58a1c728f3ad
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757781"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams

> [!Tip]
> Per informazioni sull’interazione tra Teams e Azure Active Directory (AAD), i Gruppi di Microsoft 365, Exchange, SharePoint e OneDrive for Business, vedere la sessione: [Nozioni di base di Microsoft Teams](https://aka.ms/teams-foundations)

Ogni team in Microsoft Teams ha un sito del team in SharePoint Online e ogni canale standard di un team ottiene una cartella all'interno della raccolta documenti predefinita del sito del team. I file condivisi in una conversazione vengono aggiunti automaticamente alla raccolta documenti e le autorizzazioni e opzioni di sicurezza per i file impostate in SharePoint vengono applicate automaticamente all'interno di Teams. Per informazioni sull'impatto della modifica dell'indirizzo di un sito in SharePoint, vedere [Modificare l'indirizzo di un sito.](https://docs.microsoft.com/sharepoint/change-site-address)

> [!NOTE]
> Questo articolo si applica solo ai canali standard. L'architettura dei canali privati è diversa dai canali standard. Ogni canale privato ha una propria raccolta siti di SharePoint separata dal sito del team padre. Per altre informazioni, vedere [Canali privati in Microsoft Teams.](private-channels.md)

I file delle chat private vengono archiviati nella cartella OneDrive for Business del mittente e le autorizzazioni vengono concesse automaticamente a tutti i partecipanti durante il processo di condivisione dei file.

Se gli utenti non vengono assegnati e abilitati tramite licenze di SharePoint Online, non possono sfruttare l'archiviazione OneDrive for Business in Microsoft 365 o Office 365. La condivisione di file continuerà a funzionare nei canali standard, ma gli utenti non saranno in grado di condividere file nelle chat senza spazio di archiviazione di OneDrive for Business in Microsoft 365 o Office 365.

Archiviando i file nella raccolta documenti di SharePoint Online e in OneDrive for Business, verranno rispettate tutte le regole di conformità configurate a livello di tenant. 

> [!NOTE]
> Al momento l'integrazione con SharePoint locale non è supportata per Microsoft Teams.

Di seguito è illustrato un esempio di relazioni tra il team, il canale standard e la raccolta documenti.

Per ogni team viene creato un sito  di SharePoint e la cartella Documenti condivisi è la cartella predefinita creata per il team. Ogni canale standard, incluso **il canale** Generale (il canale predefinito per ogni team), ha una cartella in **Documenti condivisi.**

![Diagramma delle cartelle Documenti condivisi in SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> Attualmente non è possibile sostituire il sito e la raccolta documenti predefiniti di SharePoint con un'altra. In base ai dati dell'utente, l'utente ha deciso di farlo e sta valutando la possibilità di farlo. Consultare la [roadmap di Teams](https://aka.ms/teamsroadmap) o Teams [UserVoice](https://aka.ms/TeamsUserVoice) per essere sempre al corrente delle prossime funzionalità.

> [!TIP]
> Per aggiungere al team una scheda collegata a una pagina del sito di SharePoint esistente o alla raccolta documenti di SharePoint esistente:
> 1. Selezionare il segno più accanto alle schede.
> 2. Selezionare **SharePoint per una** pagina del sito di SharePoint esistente o una **raccolta documenti** per una raccolta documenti esistente.
> 3. Selezionare la pagina o la raccolta documenti appropriata.

Per ogni utente, la cartella OneDrive dei file di chat di **Microsoft Teams** viene usata per archiviare tutti i file condivisi nelle chat private con altri utenti (1:1 o 1:molti), con autorizzazioni configurate automaticamente per limitare l'accesso solo all'utente previsto.

![Diagramma della cartella OneDrive denominata File chat di Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

Per i team pubblici, viene eseguito il provisioning del sito del team di SharePoint con accesso "Tutti tranne gli utenti esterni". Il team pubblico non viene visualizzato in Teams per le persone che non sono membri di quel team. Tuttavia, possono accedere al contenuto del sito del team di SharePoint usando l'URL del sito del team di SharePoint. 

## <a name="channel-files-tab"></a>Scheda File del canale

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

La **scheda File** in Teams è molto simile alla visualizzazione documenti di SharePoint. Nella scheda **File** gli utenti possono:

- Vedere altre opzioni **nel** menu Nuovo file.
- Sincronizzare i file nell'unità locale.
- Nel menu **Tutti i documenti** passare dalla **visualizzazione** elenco all'elenco **compatto** alla **visualizzazione** riquadri.
- Identificare i file che necessitano di attenzione o che hanno malware.
- Verificare immediatamente se un file è di sola lettura o estratto.
- Estrarre e archiviare file.
- Aggiungere, rimuovere e modificare l'ordinamento dei file.
- Identificare i file che necessitano di metadati
- Scegliere una delle molte altre opzioni di filtro.
- Raggruppare i file in base alle intestazioni di colonna.
- Modificare le impostazioni di colonna (spostarsi a sinistra o a destra, nascondere) e la larghezza delle colonne.

## <a name="default-link-type-setting"></a>Impostazione tipo di collegamento predefinito

SharePoint e OneDrive hanno un'impostazione di amministrazione che consente di specificare il tipo di collegamento predefinito per i collegamenti creati per un file. Teams sta adottando lo stesso approccio riutilizzando le impostazioni che gli amministratori configurano per SharePoint e OneDrive. Altri dettagli su questo approccio sono descritti in Modificare il tipo di collegamento predefinito quando gli utenti [ottengono collegamenti per la condivisione.](https://docs.microsoft.com/sharepoint/change-default-sharing-link) 

## <a name="more-information"></a>Altre informazioni

Per altre informazioni sul funzionamento di SharePoint con Teams, vedere [SharePoint e Teams: insieme è meglio.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

Per saperne di più sull'esperienza guest in Teams, leggi [Com'è l'esperienza guest.](guest-experience.md)

