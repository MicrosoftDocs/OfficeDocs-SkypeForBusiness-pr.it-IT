---
title: Report sull'utilizzo di Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report utilizzo teams nell'interfaccia di amministrazione di Microsoft teams per ottenere una panoramica delle attività dei team nell'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3419ecb6c4ef1b976681f626fd8ec567e665d6a5
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827234"
---
# <a name="microsoft-teams-usage-report"></a>Report sull'utilizzo di Microsoft Teams

Il report sull'utilizzo di teams nell'interfaccia di amministrazione di Microsoft teams offre una panoramica delle attività di utilizzo in teams, incluso il numero di utenti e canali attivi, in modo da poter vedere rapidamente quanti utenti nell'organizzazione usano team per comunicare e collaborare. È possibile visualizzare le informazioni sull'utilizzo per i team, incluso il numero di utenti e canali attivi, gli ospiti e i messaggi in ogni team.

## <a name="view-the-report"></a>Visualizzare il report

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **analisi &** > report**sull'utilizzo**dei rapporti. Nella scheda **Visualizza report** , in **report**, selezionare **utilizzo teams**.
2. In **intervallo di date**selezionare un intervallo e quindi fare clic su **Esegui report**.

    ![Screenshot del report utilizzo teams nell'interfaccia di amministrazione di teams con callout](../media/teams-reports-teams-usage-with-callouts.png "Screenshot del report utilizzo teams nell'interfaccia di amministrazione di teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report attività di utilizzo di teams può essere visualizzato per le tendenze degli ultimi 7 giorni o 28 giorni. |
|**2**   |Ogni report riporta la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |<ul><li>L'asse X nel grafico è l'intervallo di date selezionato per il report.</li> <li> L'asse Y è il numero di elementi attivi o attività.</li> </ul>Posizionare il puntatore del mouse sul punto che rappresenta un elemento o un'attività in una data specificata per visualizzare il numero di istanze di tale elemento o attività in quella data specificata.|
|**4**   |È possibile filtrare gli elementi visualizzati nel grafico facendo clic su un elemento nella legenda. Ad esempio, fare clic su **Total users Active**, **Teams & canali Active users**, **Active Channels**o **messages** per visualizzare solo le informazioni relative a ognuna di esse. La modifica di questa selezione non modifica le informazioni nella tabella. |
|**5**   |La tabella offre una ripartizione dell'utilizzo da parte del team. <ul><li>Il **nome del team** è il nome visualizzato del team. È possibile fare clic sul nome del team per accedere alla pagina delle impostazioni del team nell'interfaccia di amministrazione di Microsoft teams. </li> <li>La **privacy** si riferisce al fatto che il team sia un team privato o un team pubblico.</li> <li>**Utenti attivi** è il numero di utenti attivi nel team nel periodo di tempo specificato.</li><li>**Guest** è il numero di Guest nel team nel periodo di tempo specificato.</li> </li> </ul>Tieni presente che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**6**   |Selezionare **modifica colonne** per aggiungere o rimuovere colonne nella tabella.|
|**7**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su **Esporta in Excel**, quindi nella scheda **download** fare clic su **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda download che mostra i report esportati da scaricare](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report in teams](teams-reporting-reference.md)
