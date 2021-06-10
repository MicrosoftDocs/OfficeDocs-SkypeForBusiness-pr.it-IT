---
title: Come SharePoint e OneDrive con Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive'interazione con Teams; Archiviazione di file di chat privata &'interazione tra team, canale standard, & raccolta documenti.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855955"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a>Come SharePoint e OneDrive con Microsoft Teams

> [!Tip]
> Guardare la sessione seguente per informazioni su come Teams interagisce con Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint e OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)

Ogni team di Microsoft Teams ha un sito del team in SharePoint e ogni canale standard di un team ottiene una cartella all'interno della raccolta documenti del sito del team predefinita. Ogni [canale privato](private-channels.md) ottiene un sito SharePoint privato.

I file condivisi in una conversazione vengono aggiunti automaticamente alla raccolta documenti e le autorizzazioni e opzioni di sicurezza per i file impostate in SharePoint vengono applicate automaticamente all'interno di Teams. Per vedere l'impatto della modifica dell'indirizzo di un sito in SharePoint, vedere [Modificare l'indirizzo di un sito.](/sharepoint/change-site-address)

I file di chat privati vengono archiviati nella cartella OneDrive del mittente e le autorizzazioni vengono concesse automaticamente a tutti i partecipanti nell'ambito del processo di condivisione file.

Se agli utenti non sono assegnate SharePoint licenze, non hanno OneDrive di archiviazione in Microsoft 365. La condivisione di file funziona nei canali standard, ma gli utenti non saranno in grado di condividere file nelle chat senza OneDrive archiviazione in Microsoft 365.

Archiviando i file nella raccolta SharePoint documenti OneDrive, verranno seguite tutte le regole di conformità configurate a livello di organizzazione. 

> [!NOTE]
> L'integrazione con SharePoint Server non è supportata per Teams.

Di seguito è riportato l'esempio di relazioni tra il team, il canale standard e la raccolta documenti.

Per ogni team viene creato SharePoint sito di lavoro e la cartella Documenti **condivisi** è la cartella predefinita creata per il team. Ogni canale standard, incluso **il canale Generale** (il canale predefinito per ogni team), ha una cartella in Documenti **condivisi.**

![Diagramma delle cartelle Documenti condivisi In SharePoint.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

Il sito SharePoint e la raccolta documenti predefiniti non possono essere sostituiti con uno diverso.

Per ogni utente, la cartella OneDrive **Microsoft Teams File chat** viene usata per archiviare tutti i file condivisi nelle chat private con altri utenti (1:1 o 1:molti), con le autorizzazioni configurate automaticamente per limitare l'accesso solo all'utente previsto.

![Diagramma della cartella OneDrive denominata Microsoft Teams chat](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

Si noti che per i team pubblici, il SharePoint del team viene eseguito il provisioning con l'accesso "Tutti tranne gli utenti esterni". Il team pubblico non viene visualizzato in Teams per le persone che non sono membri del team. Tuttavia, possono accedere al contenuto del SharePoint del team usando l'URL del sito SharePoint del team. 

## <a name="channel-files-tab"></a>Scheda File del canale

La **scheda File** in Teams simile alla visualizzazione SharePoint documenti. Nella scheda **File** gli utenti possono:

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

Tipo di collegamento di condivisione visualizzato per impostazione predefinita quando un utente ha condiviso un file nell'SharePoint di amministrazione. Per [informazioni, vedere Modificare il tipo di collegamento predefinito quando gli utenti ottengono collegamenti per la](/sharepoint/change-default-sharing-link) condivisione.

## <a name="related-topics"></a>Argomenti correlati

[SharePoint e Teams: meglio insieme.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

[Com'è l'esperienza guest](guest-experience.md)