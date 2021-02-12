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
description: Informazioni su come usare il report sull'utilizzo di Teams nell'interfaccia di amministrazione di Microsoft Teams per una panoramica delle attività di Teams nell'organizzazione.
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

Il report sull'utilizzo di Teams nell'interfaccia di amministrazione di Microsoft Teams offre una panoramica dell'attività di utilizzo in Teams, incluso il numero di utenti e canali attivi, in modo da poter vedere rapidamente quanti utenti dell'organizzazione usano Teams per comunicare e collaborare. È possibile visualizzare le informazioni sull'utilizzo per i team, incluso il numero di utenti e canali attivi, guest e messaggi in ogni team.

## <a name="view-the-usage-report"></a>Visualizzare il report sull'utilizzo

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, fare clic su **Analisi & report**  >  **sull'utilizzo.** Nella scheda **Visualizza report,** in **Report,** selezionare Utilizzo **di Teams.**
2. In **Intervallo di date** selezionare un intervallo e quindi fare clic su Esegui **report.**

    ![Screenshot del report Utilizzo di Teams nell'interfaccia di amministrazione di Teams con callout](../media/teams-reports-teams-usage-with-callouts.png "Screenshot del report Utilizzo di Teams nell'interfaccia di amministrazione di Teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report Attività di utilizzo di Teams può essere visualizzato per le tendenze degli ultimi 7, 30 o 90 giorni. |
|**2**   |Ogni report riporta la data in cui è stato generato. In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |<ul><li>L'asse X nel grafico rappresenta l'intervallo di date selezionato per il report.</li> <li> L'asse Y è il conteggio degli elementi attivi o delle attività.</li> </ul>Posizionare il puntatore del mouse sul punto che rappresenta un elemento o un'attività in una data specifica per visualizzare il numero di istanze dell'elemento o dell'attività in tale data.|
|**4**   |È possibile filtrare gli elementi visualizzati nel grafico facendo clic su un elemento nella legenda. Ad esempio, fare clic su **Totale** utenti attivi, Team  **& utenti** **attivi,** Canali attivi o Messaggi per visualizzare solo le informazioni per ognuno di essi. La modifica di questa selezione non modifica le informazioni nella tabella. |
|**5**   |La tabella fornisce un'analisi dell'utilizzo in base al team. <ul><li>**Il nome** del team è il nome visualizzato del team. È possibile fare clic sul nome del team per passare alla pagina delle impostazioni del team nell'interfaccia di amministrazione di Microsoft Teams. </li> <li>**Per privacy** si intende se il team è un team privato o pubblico.</li> <li>**Utenti attivi** è il numero di utenti attivi nel team nel periodo di tempo specificato.</li><li>**Guest** è il numero di guest nel team nel periodo di tempo specificato.</li> <li>**I canali** attivi sono il numero di canali che hanno almeno un utente attivo nel periodo di tempo specificato.</li> <li>**Pubblica messaggi** è il numero di tutti i messaggi nei canali nel periodo di tempo specificato.</li> <li>**Rispondi è** il numero di tutti i messaggi di risposta nei canali nel periodo di tempo specificato.</li> <li>**Le riunioni organizzate** sono il numero di riunioni pianificate e ad hoc organizzate da un utente durante il periodo di tempo specificato. </li><li>**Messaggi urgenti** è il numero di tutti i messaggi urgenti nel periodo di tempo specificato.</li><li>**Reazioni** è il numero di tutte le reazioni ai messaggi nel periodo di tempo specificato.</li><li>**Menzioni** è il numero di tutte le menzioni usate nei messaggi nel periodo di tempo specificato.</li><li>**Messaggi del** canale è il numero di messaggi univoci che gli utenti del team hanno pubblicato in una chat del team durante il periodo di tempo specificato.</li> </li> </ul>Si noti che se un account utente non esiste più in Azure AD, il nome utente viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**6**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.|
|**7**   |È possibile esportare il report in un file CSV per l'analisi offline. Fare clic su Esporta in **Excel,** quindi nella **scheda Download** fare clic su **Scarica** per scaricare il report quando è pronto.<br><br>![Screenshot della scheda Download che mostra i report esportati da scaricare](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione di report di Teams](teams-reporting-reference.md)
