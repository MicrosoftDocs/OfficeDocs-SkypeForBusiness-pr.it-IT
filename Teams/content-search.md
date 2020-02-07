---
title: Usare la ricerca contenuto in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni sulla ricerca di contenuto in Microsoft teams e su come eseguire la ricerca in base a conversazioni di canale da Exchange, upload di file e modifiche da SharePoint e OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 222b57021a259795823031d9855304d1ecf27f4f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825344"
---
<a name="use-content-search-in-microsoft-teams"></a>Usare la ricerca contenuto in Microsoft Teams
=====================================

> [!NOTE]
> La ricerca di contenuto di messaggi e file nei [canali privati](private-channels.md) funziona in modo diverso rispetto ai canali standard. Per altre informazioni, vedere [ricerca di contenuto dei canali privati](#content-search-of-private-channels).

Ricerca contenuto consente di eseguire query sulle informazioni di Microsoft teams che si estendono in Exchange, SharePoint Online e OneDrive for business.

Per altre informazioni, leggere la [ricerca di contenuto in Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).

Ad esempio, usando la **ricerca di contenuto** per le specifiche della cassetta postale di produzione e delle specifiche di produzione del sito di SharePoint, è possibile eseguire una ricerca in base alle conversazioni di canale standard di Teams da Exchange, upload di file e modifiche da SharePoint Online e modifiche di OneNote.

È anche possibile aggiungere criteri di query alla **Ricerca contenuto** per restringere i risultati restituiti. Nell'esempio precedente puoi cercare il contenuto in cui sono state usate le parole chiave "**nuove specifiche di fabbrica"** .

> [!TIP]
> Dopo aver aggiunto le condizioni di ricerca, è possibile esportare un report o i dati nel computer per l'analisi.

## <a name="content-search-of-private-channels"></a>Ricerca di contenuto dei canali privati

I record per i messaggi inviati in un canale privato vengono recapitati alla cassetta postale di tutti i membri del canale privato, invece che a una cassetta postale del gruppo. I titoli dei record sono formattati per indicare il canale privato da cui sono stati inviati.

Poiché ogni canale privato ha una propria raccolta siti di SharePoint separata dal sito del team padre, i file in un canale privato vengono gestiti indipendentemente dal team padre.

Teams non supporta la ricerca di contenuto di un singolo canale, quindi è necessario cercare tutto il team. Per eseguire una ricerca di contenuto di un canale privato, cercare in tutto il team, la raccolta siti associata al canale privato (per includere i file) e le cassette postali dei membri del canale privato (per includere i messaggi).

Seguire i passaggi seguenti per identificare i file e i messaggi in un canale privato da includere nella ricerca di contenuto.

### <a name="include-private-channel-files-in-a-content-search"></a>Includere file di canale privato in una ricerca contenuto

Prima di eseguire questa procedura, installare [SharePoint Online Management Shell e connettersi a SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Eseguire la procedura seguente per ottenere un elenco di tutte le raccolte siti di SharePoint associate a canali privati nel team.

    ```PowerShell
    Get-SPOSite
    ```
2. Eseguire lo script di PowerShell seguente per ottenere un elenco di tutti gli URL della raccolta siti di SharePoint associati a canali privati nel team e nell'ID del gruppo del team padre.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Per ogni ID team o gruppo, Esegui lo script di PowerShell seguente per identificare tutti i siti di canale privati rilevanti.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Includere messaggi di canale privato in una ricerca di contenuto

Prima di eseguire questa procedura, verificare di avere installato la [versione più recente del modulo di PowerShell teams](teams-powershell-overview.md) .

1. Eseguire la procedura seguente per ottenere un elenco di canali privati nel team.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Eseguire la procedura seguente per ottenere un elenco dei membri del canale privato.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Includere le cassette postali di tutti i membri di ogni canale privato del team come parte della query di ricerca contenuto.

## <a name="related-topics"></a>Argomenti correlati

- [casi di eDiscovery nel centro conformità & sicurezza di Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 