---
title: Eseguire un'analisi eDiscovery del contenuto in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Informazioni su cosa fare quando è necessario preformare un eDiscovery, ad esempio quando è necessario inviare tutte le info archiviate elettronicamente per il procedimento legale.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42a9f9cc011d050e540eef3ff87d9cd839cc2819
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569889"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Eseguire un'analisi eDiscovery del contenuto in Microsoft Teams
============================

Le grandi imprese sono spesso esposte a procedimenti legali di pena elevata che richiedono l'invio di tutte le informazioni archiviate elettronicamente (ESI).

Tutti i team 1:1 o chat di gruppo vengono inseriti nelle cassette postali degli utenti e tutti i messaggi di canale vengono inseriti nella cassetta postale del gruppo che rappresenta il team. I file caricati sono coperti dalla funzionalità eDiscovery per SharePoint Online e OneDrive for business.

1.  Per eseguire un'analisi eDiscovery con il contenuto di Microsoft teams, esaminare [il](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) passaggio 1 in questo collegamento.

2.  I dati di Microsoft teams verranno visualizzati come messaggi istantanei o conversazioni nell'output di esportazione di Excel eDiscovery ed è possibile montarlo. PST in Outlook per visualizzare i messaggi dopo l'esportazione.

    Quando si monta. PST per il team, tenere presente che tutte le conversazioni vengono mantenute nella cartella chat del team in Cronologia conversazioni. Il titolo del messaggio viene allineato al team e al canale. Dalla revisione dell'immagine seguente è possibile visualizzare il messaggio di Roberto che ha inviato un messaggio al canale Project 7 del team di specifiche di manufacturing.

    ![Screenshot di una cartella della chat del team nella cassetta postale di un utente in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  Per visualizzare le chat private nella cassetta postale di un utente, esse si trovano anche all'interno della cartella chat del team in Cronologia conversazioni.

## <a name="ediscovery-of-guest-to-guest-chats"></a>eDiscovery delle chat Guest-to-Guest

Senza una cassetta postale, le chat Guest-to-Guest (chat 1xN in cui non ci sono utenti di Home tenant) non verrebbero indicizzate e, di conseguenza, non verrebbero incluse in eDiscovery. Per facilitare eDiscovery per le chat Guest-to-Guest, viene creata una cassetta postale basata sul cloud (o una cassetta postale fantasma) per archiviare i dati di 1xN. Dopo che i dati della chat di teams sono archiviati nella cassetta postale basata sul cloud, è indicizzato per la ricerca di contenuto eDiscovery e conformità.

La figura seguente mostra come funziona eDiscovery per le chat Guest-to-Guest in cui non è presente una cassetta postale.

![Guest-to-Guest-chat-con-senza-cassetta postale](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
