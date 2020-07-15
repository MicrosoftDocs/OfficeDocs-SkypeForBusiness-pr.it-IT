---
title: Condivisione di file in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Informazioni sull'esperienza di condivisione di file in Microsoft teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138352"
---
# <a name="sharing-files-in-microsoft-teams"></a>Condivisione di file in Microsoft Teams

In Microsoft teams gli utenti possono condividere contenuti con altri utenti di team all'interno e all'esterno dell'organizzazione. La condivisione in teams si basa sulle impostazioni configurate in SharePoint e OneDrive, quindi qualsiasi configurazione per SharePoint e OneDrive controllerà la condivisione anche in teams.

## <a name="overview"></a>Panoramica

Gli utenti possono condividere file da OneDrive, da team e siti a cui hanno accesso e dal proprio computer. Per condividere un file, gli utenti possono eseguire le operazioni seguenti:

- In un canale, fare clic su **Allega** (icona graffetta), selezionare **recenti**, **esplorare team e canali**, **OneDrive**o **caricare dal computer**e quindi scegliere il file che si vuole condividere. <br> 
    ![Schermata che mostra la condivisione di un file da un canale](media/share-files-channel.png)
- In una chat fare clic su **Allega** (icona graffetta), selezionare o **OneDrive** o **carica dal computer**e quindi scegliere il file che si vuole condividere. <br>
    ![Schermata che mostra la condivisione di un file da una chat](media/share-files-chat.png)
- Copiare e incollare il collegamento di condivisione nella casella di composizione.<br>
    ![Screenshot che mostra l'anteprima dei file nella casella di composizione](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>Informazioni utili sull'esperienza di condivisione di file

### <a name="permissions-of-shared-files-and-sharing-links"></a>Autorizzazioni di file condivisi e collegamenti di condivisione

Quando gli utenti condividono un file passandolo in OneDrive o in team e canali, a tutti i destinatari viene concesso l'accesso insieme alle [autorizzazioni predefinite impostate a livello di organizzazione](https://docs.microsoft.com/sharepoint/change-default-sharing-link).

Quando un utente copia e incolla un collegamento di condivisione, le autorizzazioni impostate per il collegamento di condivisione vengono rispettate e l'URL di SharePoint viene accorciato nel nome del file. In altre parole, teams USA solo il nome del file per collegarsi a un file.

Quando gli utenti condividono un file all'interno di teams, possono impostare le persone che possono accedere al file proprio come in Microsoft 365. Possono consentire l'accesso a tutti gli utenti dell'organizzazione, agli utenti con accesso esistente o a persone specifiche (che possono includere le persone in una chat di 1:1, in una chat di gruppo o in un canale).  Quando si condivide un file, l'anteprima del file è disponibile nel messaggio, insieme a tutte le azioni dei file, ad esempio **Apri online**, **Scarica**e **copia collegamento**. Per impostazione predefinita, il file viene aperto in teams. Talvolta, il collegamento di condivisione potrebbe non essere stato convertito in un'anteprima del file per il momento in cui un utente invia il messaggio. L'anteprima del file verrà generata dal sistema, ma in questo scenario il collegamento di condivisione non verrà ridotto solo al nome del file.

Quando gli utenti condividono un file in una chat o un canale, viene avvisato se alcuni o tutti i destinatari non hanno l'autorizzazione per visualizzare il file. Possono modificare le autorizzazioni per il file prima di condividerlo facendo clic sulla freccia accanto all'anteprima del file che ora viene visualizzata nel messaggio.

![Screenshot della notifica se i destinatari non dispongono delle autorizzazioni](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>Copiare un collegamento di condivisione in teams

Gli utenti possono copiare un collegamento di condivisione di SharePoint e modificare le autorizzazioni di condivisione proprio come in Microsoft 365. Possono consentire l'accesso a tutti gli utenti dell'organizzazione, agli utenti con accesso esistente o a persone specifiche. L'autorizzazione predefinita del collegamento è uguale al set di autorizzazioni predefinito a livello dell'organizzazione, a meno che le autorizzazioni a livello di sito di SharePoint non lo sostituiscano.

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>Configurare la condivisione in OneDrive e SharePoint

Per altre informazioni sulla condivisione di file in OneDrive e SharePoint, tra cui la configurazione della condivisione e la modalità di attivazione e disattivazione della condivisione, vedere:

- [Panoramica della condivisione esterna](https://docs.microsoft.com/sharepoint/external-sharing-overview) : descrive cosa succede quando gli utenti condividono, a seconda di cosa stanno condividendo e con chi.

- [Gestire le impostazioni di condivisione](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) : descrive in che modo gli amministratori globali e di SharePoint possono modificare le impostazioni di condivisione a livello di organizzazione per SharePoint e OneDrive.

- [Attivare o disattivare la condivisione esterna per un sito](https://docs.microsoft.com/sharepoint/change-external-sharing-site) : descrive in che modo gli amministratori globali e di SharePoint possono attivare o disattivare la condivisione esterna per un sito.

- [Modificare il tipo di collegamento predefinito per un sito](https://docs.microsoft.com/sharepoint/change-default-sharing-link) -descrive come impostare il tipo di collegamento predefinito in modo che sia più restrittivo.

## <a name="more-information"></a>Ulteriori informazioni

- [Come interagire con SharePoint Online e OneDrive for business con Microsoft Teams](sharepoint-onedrive-interact.md)

- [SharePoint e teams: meglio insieme](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [Condividere file e cartelle di OneDrive](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [Condividere file o cartelle di SharePoint](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
