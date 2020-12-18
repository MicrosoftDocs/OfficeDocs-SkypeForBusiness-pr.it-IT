---
title: Condividere file in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Informazioni sull'esperienza di condivisione di file in Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138352"
---
# <a name="sharing-files-in-microsoft-teams"></a>Condividere file in Microsoft Teams

In Microsoft Teams, gli utenti possono condividere contenuti con altri utenti di Teams all'interno e all'esterno della propria organizzazione. La condivisione in Teams si basa sulle impostazioni configurate in SharePoint e OneDrive, quindi qualunque cosa sia stata configurata per SharePoint e OneDrive controllerà anche la condivisione in Teams.

## <a name="overview"></a>Panoramica

Gli utenti possono condividere file da OneDrive, da team e siti a cui hanno accesso e dal proprio computer. Per condividere un file, gli utenti possono eseguire le seguenti operazioni:

- In un canale, fare click su **Allega** (l’icona a forma di graffetta), selezionare **Recenti**, **Sfoglia team e canali**, **OneDrive** o **Carica dal computer locale**, quindi scegliere i file che si desidera condividere. <br> 
    ![Screenshot che mostra la condivisione di un file da un canale](media/share-files-channel.png)
- In un chat, fare click su **Allega** (l’icona a forma di graffetta), selezionare **OneDrive** o **Carica dal computer locale**, quindi scegliere i file che si desidera condividere. <br>
    ![Screenshot che mostra la condivisione di un file da una chat](media/share-files-chat.png)
- Copia e incolla il link di condivisione nella casella di composizione.<br>
    ![Screenshot che mostra l'anteprima del file nella casella di composizione](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>Quello che c’è sapere sull'esperienza di condivisione dei file

### <a name="permissions-of-shared-files-and-sharing-links"></a>Autorizzazioni di file condivisi e collegamenti di condivisione

Quando gli utenti condividono un file sfogliandolo in OneDrive o nei team e nei canali, a tutti i destinatari viene concesso l'accesso insieme all’[autorizzazione predefinita impostata a livello di organizzazione](https://docs.microsoft.com/sharepoint/change-default-sharing-link).

Quando un utente copia e incolla un collegamento di condivisione, le autorizzazioni impostate su quel collegamento di condivisione vengono rispettate e l'URL di SharePoint viene abbreviato col nome del file. In altre parole, Teams usa solo il nome del file per collegarsi a un file.

Quando gli utenti condividono un file direttamente da Teams, possono impostare chi può accedere al file proprio come fanno in Microsoft 365. Possono concedere l'accesso a chiunque, persone all’interno dell’organizzazione, persone con accesso esistente o persone specifiche (che possono includere le persone in una chat 1:1, chat di gruppo o canale).  Quando un file viene condiviso, l'anteprima del file è disponibile nel messaggio, insieme a tutte le azioni sui file come **Apri online**, **Scarica**, e **Copia link**. Per impostazione predefinita, il file si apre in Teams. A volte, il collegamento di condivisione potrebbe non essere stato convertito in un'anteprima del file nel momento in cui un utente invia il messaggio. L'anteprima del file verrà generata dal sistema, ma in questo scenario il collegamento di condivisione non verrà abbreviato col solo nome del file.

Quando gli utenti condividono un file in una chat o in un canale, vengono avvisati se alcuni o tutti i destinatari non sono autorizzati a visualizzare il file. Possono modificare le autorizzazioni sul file prima di condividerlo facendo clic sulla freccia accanto all'anteprima del file che ora appare nel messaggio.

![Screenshot della notifica se i destinatari non dispongono delle autorizzazioni](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>Copiare un collegamento di condivisione in Teams

Gli utenti possono copiare un collegamento di condivisione di SharePoint e modificare le autorizzazioni di condivisione proprio come fanno in Microsoft 365. Possono concedere l'accesso a chiunque, persone all’interno dell’organizzazione, persone con accesso esistente o persone specifiche. L'autorizzazione predefinita del collegamento è la stessa dell'autorizzazione predefinita impostata a livello di organizzazione, a meno che le autorizzazioni a livello di sito di SharePoint non la sovrascrivano.

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>Configurare la condivisione in OneDrive e SharePoint

Per ulteriori informazioni sulla condivisione di file in OneDrive e SharePoint, incluso come configurare la condivisione e come attivare e disattivare la condivisione, vedere:

- [Panoramica condivisione esterna](https://docs.microsoft.com/sharepoint/external-sharing-overview) - descrive cosa accade quando gli utenti condividono in base a cosa viene condiviso e con chi.

- [Gestire le impostazioni di condivisione](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - descrive come gli amministratori globali e di SharePoint possono modificare le impostazioni di condivisione a livello di organizzazione per SharePoint e OneDrive.

- [Attivare o disattivare la condivisione esterna per un sito](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – descrive come gli amministratori globali e di SharePoint possono attivare o disattivare la condivisione esterna per un sito.

- [Cambiare tipo di collegamento predefinito per un sito](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - descrive come impostare il tipo di collegamento predefinito in modo che sia più restrittivo.

## <a name="more-information"></a>Altre informazioni

- [Modalità di interazione di SharePoint Online e OneDrive for Business con Microsoft Teams](sharepoint-onedrive-interact.md)

- [SharePoint e Teams: migliori insieme](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [Condividere file e cartelle di OneDrive](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [Condividere file o cartelle di SharePoint](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
