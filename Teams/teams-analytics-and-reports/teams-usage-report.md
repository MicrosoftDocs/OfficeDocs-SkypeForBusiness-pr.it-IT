---
title: Report sull'utilizzo di Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report utilizzo teams nell'interfaccia di amministrazione di Microsoft teams per ottenere una panoramica delle attività dei team nell'organizzazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 993c1b124737a0f335e9c9b1e720af72fcc88a8e
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122256"
---
# <a name="microsoft-teams-usage-report"></a>Report sull'utilizzo di Microsoft Teams

Il report sull'utilizzo di teams nell'interfaccia di amministrazione di Microsoft teams offre una panoramica delle attività di utilizzo in teams, incluso il numero di utenti e canali attivi, in modo da poter vedere rapidamente quanti utenti nell'organizzazione usano team per comunicare e collaborare. È possibile visualizzare le informazioni sull'utilizzo per i team, incluso il numero di utenti e canali attivi, gli ospiti e i messaggi in ogni team.

## <a name="view-the-usage-report"></a>Visualizzare il report sull'utilizzo

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **analisi &** report  >  **sull'utilizzo** dei rapporti. Nella scheda **Visualizza report** , in **report**, selezionare **utilizzo teams**.
2. In **intervallo di date** selezionare un intervallo e quindi fare clic su **Esegui report**.

    ![Screenshot del report utilizzo teams nell'interfaccia di amministrazione di teams con callout](../media/teams-reports-teams-usage-with-callouts.png "Screenshot del report utilizzo teams nell'interfaccia di amministrazione di teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report attività di utilizzo di teams può essere visualizzato per le tendenze degli ultimi 7 giorni, 30 o 90 giorni. |
|**2**   |Ogni report riporta la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |<ul><li>L'asse X nel grafico è l'intervallo di date selezionato per il report.</li> <li> L'asse Y è il numero di elementi attivi o attività.</li> </ul>Posizionare il puntatore del mouse sul punto che rappresenta un elemento o un'attività in una data specificata per visualizzare il numero di istanze di tale elemento o attività in quella data specificata.|
|**4**   |È possibile filtrare gli elementi visualizzati nel grafico facendo clic su un elemento nella legenda. Ad esempio, fare clic su  **Total users Active**, **Teams & canali Active users**,  **Active Channels** o **messages** per visualizzare solo le informazioni relative a ognuna di esse. La modifica di questa selezione non modifica le informazioni nella tabella. |
|**5**   |La tabella offre una ripartizione dell'utilizzo da parte del team. <ul><li>Il **nome del team** è il nome visualizzato del team. È possibile fare clic sul nome del team per accedere alla pagina delle impostazioni del team nell'interfaccia di amministrazione di Microsoft teams. </li> <li>La **privacy** si riferisce al fatto che il team sia un team privato o un team pubblico.</li> <li>**Utenti attivi** è il numero di utenti attivi nel team nel periodo di tempo specificato.</li><li>**Guest** è il numero di Guest nel team nel periodo di tempo specificato.</li> <li>**Canali attivi** è il numero di canali che hanno almeno un utente attivo nel periodo di tempo specificato.</li> <li>**Post messages** è il numero di tutti i messaggi post nei canali nel periodo di tempo specificato.</li> <li>**Messaggi di risposta** è il numero di tutti i messaggi di risposta nei canali nel periodo di tempo specificato.</li> <li>**Riunioni organizzate** è il numero di riunioni pianificate e ad hoc che un utente ha organizzato durante il periodo di tempo specificato. </li><li>**Messaggi urgenti** è il numero di tutti i messaggi urgenti nel periodo di tempo specificato.</li><li>**Reazioni** è il numero di tutte le reazioni ai messaggi nel periodo di tempo specificato.</li><li>**Menzioni** indica il numero di menzioni usate nei messaggi nel periodo di tempo specificato.</li><li>**Messaggi di canale** è il numero di messaggi univoci che gli utenti del team hanno postato in una chat del team durante il periodo di tempo specificato.</li> </li> </ul>Tieni presente che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**6**   |Selezionare **modifica colonne** per aggiungere o rimuovere colonne nella tabella.|
|**7**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su **Esporta in Excel**, quindi nella scheda **download** fare clic su **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda download che mostra i report esportati da scaricare](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report in teams](teams-reporting-reference.md)
