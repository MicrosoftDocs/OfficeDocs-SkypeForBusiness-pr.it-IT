---
title: Report sull'utilizzo di Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report sull'utilizzo di Teams nell'interfaccia di amministrazione di Microsoft Teams per ottenere una panoramica delle attività di Teams nell'organizzazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cca90acb474b29b89357a6c58a0df82ede963b22
ms.sourcegitcommit: 40cba40b1babdb3fbfc1a416b7eeb0118f8353df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2023
ms.locfileid: "69820331"
---
# <a name="microsoft-teams-usage-report"></a>Report sull'utilizzo di Microsoft Teams

Il report Sull'utilizzo di Teams nell'interfaccia di amministrazione di Microsoft Teams offre una panoramica dell'attività di utilizzo in Teams, incluso il numero di utenti e canali attivi, in modo da poter vedere rapidamente quanti utenti all'interno dell'organizzazione usano un particolare team per comunicare e collaborare. È possibile visualizzare le informazioni sull'utilizzo per i team, incluso il numero di utenti e canali attivi, guest e messaggi in ogni team.

Con altre informazioni aggiuntive sugli utenti interni ed esterni, è ora possibile misurare la collaborazione all'interno di [canali condivisi](/Teams/shared-channels.md) interni ed esterni in un team. Ad esempio, le metriche come i canali condivisi attivi e gli utenti attivi esterni in un team aiuteranno l'amministratore a misurare la collaborazione tra canali condivisi all'interno di un team.

## <a name="view-the-usage-report"></a>Visualizzare il report sull'utilizzo

Per visualizzare i report nell'interfaccia di amministrazione di Teams, è necessario essere un amministratore globale, un lettore globale e un lettore di report o un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Analisi & report** > **utilizzo**. Nella scheda **Visualizza report** , in **Report**, selezionare **Uso di Teams**.
2. In **Intervallo di date** selezionare un intervallo e quindi fare clic su **Esegui report**.

    ![Screenshot del report sull'utilizzo di Teams nell'interfaccia di amministrazione di Teams con callout.](../media/teams-reports-teams-usage-with-callouts2.png "Screenshot del report sull'utilizzo di Teams nell'interfaccia di amministrazione di Teams con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report Attività sull'utilizzo di Teams può essere visualizzato per le tendenze degli ultimi 7, 30, 90 e 180 giorni. |
|**2**   |Ogni report riporta la data in cui è stato generato. I report in genere riflettono una latenza di 24-48 ore dal momento dell'attività. |
|**3**   |<ul><li>L'asse X nel grafico rappresenta l'intervallo di date selezionato per il report.</li> <li> L'asse Y è il conteggio degli elementi attivi o delle attività.</li> </ul>Passare il puntatore del mouse sul punto che rappresenta un elemento o un'attività in una data specificata per visualizzare il numero di istanze dell'elemento o dell'attività in tale data in tutti i team attivi.|
|**4**   |È possibile filtrare gli elementi visualizzati nel grafico facendo clic su un elemento nella legenda. Ad esempio, fare clic su  **Utenti attivi interni**, **Guest attivi**,  **Canali attivi**, **Post** e altro ancora per visualizzare solo le informazioni pertinenti. La modifica di questa selezione non modifica le informazioni nella tabella. |
|**5**   |La tabella fornisce una suddivisione dell'utilizzo in base al team. <ul><li>**Nome team** è il nome visualizzato del team. È possibile fare clic sul nome del team per passare alla pagina delle impostazioni del team nell'interfaccia di amministrazione di Microsoft Teams. </li> <li>**L'ID team** è l'identificatore univoco del team. </li> <li>**Tipo** indica se il team è un team privato o pubblico.</li> <li>**Utenti attivi interni** è il numero di utenti attivi, inclusi gli utenti guest che eseguono un'azione nel team nel periodo di tempo specificato. <br/>Gli utenti interni e gli utenti guest risiedono nello stesso tenant, ma non sono uguali.</li><li>**Guest attivi** è il numero di guest che eseguono un'azione nel team nel periodo di tempo specificato.</li> <li>**Utenti attivi esterni** (nuovi) è il numero di utenti attivi di organizzazioni esterne che eseguono un'azione in tale team in una risorsa, ad esempio un canale condiviso in un team. <br/> Gli utenti esterni hanno la propria identità in tenant diversi e non sono uguali a un account guest.</li><li>**Canali attivi** è il numero di canali del team che ha almeno un utente attivo nel periodo di tempo specificato. Sono inclusi i canali privati, pubblici e condivisi. </li><li>**Canali condivisi attivi** (nuovi) è il numero di canali condivisi in un team che ha almeno un utente interno o esterno attivo nel periodo di tempo specificato. </li> <li>**Il totale delle riunioni organizzate** è la somma di una volta le riunioni pianificate, ricorrenti, non pianificate e non classificate organizzate in un canale di Teams durante il periodo di tempo specificato. </li><li>**Post** è il numero di tutti i messaggi nei canali nel periodo di tempo specificato.</li> <li>**Risposte** è il numero di tutti i messaggi di risposta nei canali nel periodo di tempo specificato.</li> <li>**Menzioni** è il numero di tutte le menzioni usate nei messaggi nel periodo di tempo specificato.</li><li>**Reazioni** è il numero di tutte le reazioni ai messaggi nel periodo di tempo specificato.</li><li>**Messaggi urgenti** è il numero di tutti i messaggi urgenti nel periodo di tempo specificato.</li><li>**Messaggi del canale** è il numero di messaggi univoci pubblicati dagli utenti del team nelle chat del team durante il periodo di tempo specificato.</li> </li> </ul>Si noti che se un team non esiste più, il nome viene visualizzato come "--" nella tabella. <br><br>Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella. |
|**6**   |Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.|
|**7**   |Esportare il report in un file CSV per l'analisi offline. Selezionare l'icona **Esporta in Excel** per scaricare il report nel browser.|
|**8** |I dati della serie temporale rappresentati nel grafico superiore mostrano metriche di utilizzo diverse aggregate per l'intero tenant|
|**9** |I dati tabulari rappresentati nella metà inferiore mostrano metriche di utilizzo diverse aggregate per team|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]


## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati in un report sull'utilizzo di Teams, è necessario essere un amministratore globale. Il amministratore globale può nascondere le informazioni identificabili (usando hash MD5), ad esempio il nome visualizzato, il nome del gruppo, la posta elettronica e l'ID AAD nel report e nella relativa esportazione.

1. In interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** > **impostazioni organizzazione** e nella scheda **Servizi** scegliere **Report**.
    
2. Selezionare **Report** e quindi scegliere **Visualizza nomi di utenti, gruppi e siti nascosti in tutti i report**. Questa impostazione viene applicata sia ai report sull'utilizzo in interfaccia di amministrazione di Microsoft 365 che all'interfaccia di amministrazione di Teams.
  
3. Selezionare **Salva modifiche**.

> [!NOTE]
> L'abilitazione di questa impostazione deidentificherà le informazioni relative a utenti, gruppi e siti nel [report attività utente di Teams](user-activity-report.md), nel [report sull'utilizzo dei dispositivi di Teams](device-usage-report.md) e [nel report sull'utilizzo di Teams](teams-usage-report.md). A partire dal 1° settembre 2021, questa impostazione è abilitata per impostazione predefinita per tutti gli utenti nell'ambito del nostro costante impegno per proteggere le informazioni importanti e consentire alle aziende di supportare le leggi locali sulla privacy. 
>
>Questa impostazione si applica anche ai report sull'utilizzo di Microsoft 365 in interfaccia di amministrazione di Microsoft 365, Microsoft Graph e Power BI.

## <a name="related-topics"></a>Argomenti correlati

- [Analisi e creazione dei report di Teams](teams-reporting-reference.md).
