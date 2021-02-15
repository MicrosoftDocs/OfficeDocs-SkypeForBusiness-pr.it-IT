---
title: Usare Ricerca contenuto in Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Informazioni sull'uso di Ricerca contenuto nel Centro conformità di Microsoft 365 per cercare contenuto di Microsoft Teams archiviato in Exchange Online, SharePoint Online, OneDrive for Business e OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f91e630b6f0666def3e64e40e68a6a3f18097152
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980440"
---
<a name="use-content-search-in-microsoft-teams"></a>Usare la ricerca di contenuto in Microsoft Teams
=====================================

> [!NOTE]
> La ricerca di contenuti di messaggi e file nei [canali privati](private-channels.md) funziona in modo diverso rispetto ai canali standard. Per altre informazioni, vedere [Ricerca di contenuti di canali privati.](#content-search-of-private-channels)

La ricerca contenuto consente di eseguire query sulle informazioni di Microsoft Teams che interessano Exchange, SharePoint Online e OneDrive for Business.

Per altre informazioni, vedere [Ricerca contenuto in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search)

Ad esempio,  usando la ricerca di contenuto per la cassetta postale Delle specifiche di produzione e il sito di SharePoint Specifiche di produzione, è possibile eseguire ricerche nelle conversazioni di canale standard di Teams da Exchange, caricare file e apportare modifiche da SharePoint Online e modifiche di OneNote.

È anche possibile aggiungere criteri di query alla **ricerca contenuto per** limitare i risultati restituiti. Nell'esempio precedente è possibile cercare il contenuto in cui sono state usate le parole chiave **"Nuove** specifiche di fabbrica".

> [!TIP]
> Dopo aver aggiunto condizioni di ricerca, è possibile esportare un report o il contenuto effettivo nel computer per l'analisi.

## <a name="content-search-of-private-channels"></a>Ricerca di contenuti di canali privati

I record per i messaggi inviati in un canale privato vengono recapitati nella cassetta postale di tutti i membri del canale privato, anziché in una cassetta postale di gruppo. I titoli dei record vengono formattati in modo da indicare da quale canale privato sono stati inviati.

Poiché ogni canale privato ha una propria raccolta siti di SharePoint separata dal sito del team padre, i file in un canale privato vengono gestiti in modo indipendente dal team padre.

Teams non supporta la ricerca di contenuto in un singolo canale, quindi è necessario cercare l'intero team. Per eseguire una ricerca di contenuto di un canale privato, eseguire una ricerca in tutto il team, nella raccolta siti associata al canale privato (per includere i file) e nelle cassette postali dei membri del canale privato (per includere i messaggi).

Usare la procedura seguente per identificare i file e i messaggi in un canale privato da includere nella ricerca di contenuto.

### <a name="include-private-channel-files-in-a-content-search"></a>Includere i file dei canali privati in una ricerca di contenuto

Prima di eseguire questa procedura, installare [SharePoint Online Management Shell e connettersi a SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. Eseguire la procedura seguente per ottenere un elenco di tutte le raccolte siti di SharePoint associate ai canali privati del team.

    ```PowerShell
    Get-SPOSite
    ```
2. Eseguire lo script di PowerShell seguente per ottenere un elenco di tutti gli URL della raccolta siti di SharePoint associati ai canali privati del team e all'ID del gruppo di team padre.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Per ogni ID team o gruppo, eseguire il seguente script di PowerShell per identificare tutti i siti dei canali privati pertinenti.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Includere messaggi di canale privato in una ricerca di contenuto

Prima di eseguire questa procedura, assicurarsi di avere installato [l'ultima versione del modulo Teams PowerShell.](teams-powershell-overview.md)

1. Esegui la procedura seguente per ottenere un elenco di canali privati nel team.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Eseguire la procedura seguente per ottenere un elenco dei membri del canale privato.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Includere le cassette postali di tutti i membri di ogni canale privato nel team come parte della query di ricerca contenuto.

## <a name="related-topics"></a>Argomenti correlati

- [Casi di eDiscovery nel Centro conformità di Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 