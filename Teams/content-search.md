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
description: Informazioni sull'uso di Ricerca contenuto nel portale di conformità di Microsoft Purview per cercare contenuti Microsoft Teams archiviati in Exchange Online, SharePoint Online, OneDrive for Business e OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 00de0bb3ecdcaf6dc674f08438b896abaaa49448
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922477"
---
# <a name="use-content-search-in-microsoft-teams"></a>Usare Ricerca contenuto in Microsoft Teams

> [!NOTE]
> La ricerca di contenuto di messaggi e file nei [canali privati](private-channels.md) funziona in modo diverso rispetto ai canali standard. Per altre informazioni, vedere [Ricerca di contenuto di canali privati](#content-search-of-private-channels).

La ricerca contenuto consente di eseguire query su informazioni Microsoft Teams che si estendono su Exchange, SharePoint online e OneDrive for Business.

Per altre informazioni, vedere [Ricerca di contenuto in Microsoft 365](/microsoft-365/compliance/content-search).

Ad esempio, usando **Ricerca contenuto** nella cassetta postale Specifiche di produzione e nel sito SharePoint Specifiche di produzione, è possibile eseguire ricerche in Teams conversazioni standard di canale da Exchange, caricamenti di file e modifiche da SharePoint Online e OneNote modifiche.

È anche possibile aggiungere criteri di query alla **ricerca contenuto** per limitare i risultati restituiti. Nell'esempio precedente è possibile cercare il contenuto in cui sono state usate le parole chiave "**Nuove specifiche di fabbrica".**

> [!TIP]
> Dopo aver aggiunto le condizioni di ricerca, è possibile esportare un report o il contenuto effettivo nel computer per l'analisi.

## <a name="content-search-of-private-channels"></a>Ricerca di contenuti di canali privati

I record per i messaggi inviati in un canale privato vengono recapitati nella cassetta postale di tutti i membri del canale privato, anziché in una cassetta postale di gruppo. I titoli dei record vengono formattati in modo da indicare da quale canale privato sono stati inviati.

Poiché ogni canale privato ha una propria raccolta siti SharePoint separata dal sito del team padre, i file in un canale privato vengono gestiti in modo indipendente dal team padre.

Teams non supporta la ricerca di contenuto di un singolo canale, quindi la ricerca deve essere eseguita nell'intero team. Per eseguire una ricerca di contenuto di un canale privato, eseguire una ricerca all'interno del team, della raccolta siti associata al canale privato (per includere i file) e delle cassette postali dei membri del canale privato (per includere i messaggi).

Usare la procedura seguente per identificare file e messaggi in un canale privato da includere nella ricerca di contenuti.

### <a name="include-private-channel-files-in-a-content-search"></a>Includere file di canale privati in una ricerca di contenuto

Prima di eseguire questa procedura, installare [SharePoint Online Management Shell e connettersi a SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Eseguire la procedura seguente per ottenere un elenco di tutte le raccolte siti SharePoint associate ai canali privati del team.

    ```PowerShell
    Get-SPOSite
    ```
2. Eseguire lo script di PowerShell seguente per ottenere un elenco di tutti gli URL di SharePoint raccolta siti associati ai canali privati nel team e all'ID gruppo del team padre.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. Per ogni ID del team o del gruppo, eseguire il seguente script di PowerShell per identificare tutti i siti di canale privato pertinenti.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>Includere messaggi di canale privato in una ricerca di contenuto

Prima di eseguire questa procedura, verificare che sia installata la [versione più recente del modulo Teams PowerShell](teams-powershell-overview.md).

1. Eseguire quanto segue per ottenere un elenco di canali privati nel team.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. Eseguire quanto segue per ottenere un elenco di membri del canale privato.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. Includere le cassette postali di tutti i membri di ogni canale privato nel team come parte della query di ricerca contenuto.

## <a name="related-topics"></a>Argomenti correlati

- [Casi di eDiscovery nel portale di conformità di Microsoft Purview](/Office365/SecurityCompliance/ediscovery-cases)