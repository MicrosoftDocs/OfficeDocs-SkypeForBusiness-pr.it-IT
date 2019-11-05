---
title: Eseguire un'analisi eDiscovery del contenuto in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
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
ms.openlocfilehash: 27dac8bd72eaac581022431c3786b0f7487d137c
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968047"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Eseguire un'analisi eDiscovery del contenuto in Microsoft Teams
============================

Le grandi imprese sono spesso esposte a procedimenti legali di pena elevata che richiedono l'invio di tutte le informazioni archiviate elettronicamente (ESI).

Tutti i team 1:1 o chat di gruppo vengono inseriti nelle cassette postali degli utenti e tutti i messaggi di canale standard vengono inseriti nella cassetta postale del gruppo che rappresenta il team. I file caricati nei canali standard sono coperti dalla funzionalità eDiscovery per SharePoint Online e OneDrive for business.

> [!NOTE]
> eDiscovery i messaggi e i file nei [canali privati](private-channels.md) funzionano in modo diverso rispetto ai canali standard. Per altre informazioni, vedere [eDiscovery di canali privati](#ediscovery-of-private-channels).

1.  Per eseguire un'analisi eDiscovery con il contenuto di Microsoft teams, esaminare [il](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) passaggio 1 in questo collegamento.

2.  I dati di Microsoft teams verranno visualizzati come messaggi istantanei o conversazioni nell'output di esportazione di Excel eDiscovery ed è possibile montarlo. PST in Outlook per visualizzare i messaggi dopo l'esportazione.

    Quando si monta. PST per il team, tenere presente che tutte le conversazioni vengono mantenute nella cartella chat del team in Cronologia conversazioni. Il titolo del messaggio viene allineato al team e al canale. Dalla revisione dell'immagine seguente è possibile visualizzare il messaggio di Roberto che ha inviato un messaggio al canale standard di Project 7 del team di specifiche di manufacturing.

    ![Screenshot di una cartella della chat del team nella cassetta postale di un utente in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  Per visualizzare le chat private nella cassetta postale di un utente, esse si trovano anche all'interno della cartella chat del team in Cronologia conversazioni.

## <a name="ediscovery-of-guest-to-guest-chats"></a>eDiscovery delle chat Guest-to-Guest

Senza una cassetta postale, le chat Guest-to-Guest (chat 1xN in cui non ci sono utenti di Home tenant) non verrebbero indicizzate e, di conseguenza, non verrebbero incluse in eDiscovery. Per facilitare eDiscovery per le chat Guest-to-Guest, viene creata una cassetta postale basata sul cloud (o una cassetta postale fantasma) per archiviare i dati di 1xN. Dopo che i dati della chat di teams sono archiviati nella cassetta postale basata sul cloud, è indicizzato per la ricerca di contenuto eDiscovery e conformità.

La figura seguente mostra come funziona eDiscovery per le chat Guest-to-Guest in cui non è presente una cassetta postale.

![Guest-to-Guest-chat-con-senza-cassetta postale](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

## <a name="ediscovery-of-private-channels"></a>eDiscovery dei canali privati

I record per i messaggi inviati in un canale privato vengono recapitati alla cassetta postale di tutti i membri del canale privato, invece che a una cassetta postale del gruppo. I titoli dei record sono formattati per indicare il canale privato da cui sono stati inviati.

Poiché ogni canale privato ha una propria raccolta siti di SharePoint separata dal sito del team padre, i file in un canale privato vengono gestiti indipendentemente dal team padre.

Teams non supporta eDiscovery di un singolo canale, quindi è necessario cercare tutto il team. Per eseguire una ricerca eDiscovery del contenuto in un canale privato, cercare in tutto il team, la raccolta siti associata al canale privato (per includere i file) e le cassette postali dei membri del canale privato (per includere i messaggi).

Seguire i passaggi seguenti per identificare i file e i messaggi in un canale privato da includere nella ricerca di eDiscovery.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Includere file di canale privato in una ricerca eDiscovery

Prima di eseguire questa procedura, installare [SharePoint Online Management Shell e connettersi a SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Eseguire la procedura seguente per ottenere un elenco di tutte le raccolte siti di SharePoint associate a canali privati nel team.

    ```
    Get-SPOSite
    ```
2. Eseguire lo script di PowerShell seguente per ottenere un elenco di tutti gli URL della raccolta siti di SharePoint associati a canali privati nel team e nell'ID del gruppo del team padre.

    ```
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Per ogni ID team o gruppo, Esegui lo script di PowerShell seguente per identificare tutti i siti di canale privati rilevanti, dove $groupID è l'ID del gruppo del team.

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Includere messaggi di canale privato in una ricerca eDiscovery

Prima di eseguire questa procedura, verificare di avere installato la [versione più recente del modulo di PowerShell teams](teams-powershell-overview.md) .

1. Eseguire la procedura seguente per ottenere un elenco di canali privati nel team.

    ```
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Eseguire la procedura seguente per ottenere un elenco dei membri del canale privato.

    ```
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Includere le cassette postali di tutti i membri di ogni canale privato del team come parte della query di ricerca di eDiscovery.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell Teams](teams-powershell-overview.md)