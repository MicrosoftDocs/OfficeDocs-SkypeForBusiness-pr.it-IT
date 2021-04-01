---
title: Analisi e creazione di report di Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: In questo articolo sono disponibili informazioni sui report di Teams disponibili nell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6d195c90dc7e959146546dde1a75fedf0764c24a
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478346"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Analisi e creazione di report di Microsoft Teams

Nell'interfaccia di amministrazione di Microsoft Teams è disponibile una nuova esperienza di analisi e creazione di report per Microsoft Teams. È possibile eseguire report diversi per ottenere informazioni dettagliate sul modo in cui gli utenti dell'organizzazione usano Teams. Ad esempio, puoi vedere quanti utenti comunicano tramite messaggi di canale e chat e i tipi di dispositivi che usano per connettersi a Teams. L'organizzazione può usare le informazioni dei report per comprendere meglio i modelli di utilizzo, prendere decisioni aziendali e informare le attività di formazione e comunicazione.

## <a name="how-to-access-the-reports"></a>Come accedere ai report

Per accedere ai report, devi essere un amministratore globale in Microsoft 365 o Office 365, un amministratore del servizio Teams o un amministratore di Skype for Business. Per altre informazioni sui ruoli di amministratore di Teams e sui report a cui ogni ruolo di amministratore può accedere, vedere Usare i ruoli di amministratore [di Teams per gestire Teams.](../using-admin-roles.md)

Passare all'interfaccia di amministrazione di Microsoft Teams, nel riquadro di spostamento sinistro, selezionare Analisi **& report** e quindi in **Report** scegliere il report da eseguire.

> [!NOTE]
> I report nell'interfaccia di amministrazione di Microsoft Teams sono separati dai report attività per Teams che fanno parte dei report di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365. Per altre informazioni sui report attività nell'interfaccia di amministrazione di Microsoft 365, vedere Report attività di Teams nell'interfaccia di amministrazione di [Microsoft 365](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Riferimento per la creazione di report di Teams

Ecco un elenco dei report di Teams disponibili nell'interfaccia di amministrazione di Microsoft Teams e una panoramica di alcune informazioni disponibili in ogni report.

Stiamo continuamente migliorando l'esperienza di creazione di report di Teams e aggiungendo caratteristiche e funzionalità. Nel corso del tempo, verranno integrate funzionalità aggiuntive nei report e verranno aggiunti nuovi report nell'interfaccia di amministrazione di Microsoft Teams.

|Report  |Cosa viene misurato? |
|---------|---------|
|[Report sull'utilizzo di Teams](teams-usage-report.md)  |  Utenti attivi<br/>Utenti attivi in team e canali<br/>Canali attivi<br/>Messaggi<br/>Impostazione della privacy dei team<br/>Guest in un team   |
|[Report sulle attività degli utenti di Teams](user-activity-report.md)  | Messaggi pubblicati da un utente in una chat del team<br/>Messaggi pubblicati da un utente in una chat privata<br/>  Chiamate 1:1 a cui un utente ha partecipato<br/> Numero di riunioni organizzate dall'utente <br/>numero di partecipanti alla riunione<br/>Tempo di condivisione audio, video e schermo delle riunioni<br/>   Data ultima attività di un utente     |
|[Report sull'uso dei dispositivi di Teams](device-usage-report.md)   |  Utenti di Windows<br/>Utenti Mac<br/>Utenti iOS<br/>Utenti di telefoni Android     |
|[Report sull'uso degli eventi live di Teams](teams-live-event-usage-report.md)   |  Visualizzazioni totali<br>Ora di inizio<br>Stato dell'evento<br>Organizzatore<br>Relatore<br>Produttore<br>Impostazione della registrazione<br>Tipo di produzione    |
|[Report degli utenti bloccati PSTN di Teams](pstn-blocked-users-report.md)   |  Nome visualizzato<br>Numero di telefono<br>Motivo<br>Tipo di azione<br>Data e ora dell'azione   |
|[Report pool di minuti PSTN di Teams](pstn-minute-pools-report.md) |  Paese o area geografica<br>Capability (licenza) <br>Totale minuti<br>Minuti usati<br>Minuti disponibili|
|[Report utilizzo PSTN di Teams - Piani per chiamate](pstn-usage-report.md#calling-plans)|  Indicatore data e ora<br>Nome utente<br>Numero di telefono<br>Tipo di chiamata <br>Chiamato a<br>A paese o area geografica <br>Chiamata da <br>Da paese o area geografica<br>Addebito<br>Valuta<br>Durata<br>Nazionale/Internazionale<br>ID chiamata<br>Tipo di numero<br>Paese o area geografica<br>ID conferenza<br>Capability (licenza)|
|[Report utilizzo PSTN di Teams - Routing diretto](pstn-usage-report.md#direct-routing)  |  Indicatore data e ora<br>Nome visualizzato<br>Indirizzo SIP<br>Numero di telefono <br>Tipo di chiamata<br>Chiamato a<br>Ora di inizio<br>Ora di invito<br>Tempo di errore<br>Ora di fine<br>Durata<br>Tipo di numero<br>Bypass multimediale<br>SBC FQDN<br>Area geografica di Azure<br>Tipo di evento<br>Codice SIP finale<br>Sottocodice Microsoft finale<br>Frase SIP finale<br>ID correlazione  |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati nelle attività degli utenti di Teams e nel report sull'utilizzo dei dispositivi di Teams, è necessario essere un amministratore globale. In questo modo si nasconderanno informazioni identificabili come il nome visualizzato, la posta elettronica e l'ID AAD nei report e nelle relative esportazioni.

1. Nell'interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** organizzazione Impostazioni e nella scheda Servizi \> scegliere **Report.** 
    
2. Selezionare **Report** e quindi scegliere **Visualizza identificatori anonimi**. Questa impostazione viene applicata sia ai report di utilizzo nell'interfaccia di amministrazione di Microsoft 365 che all'interfaccia di amministrazione di Teams.
  
3. Selezionare **Salva modifiche**.

> [!NOTE]
> Se si abilita questa impostazione, le informazioni verranno de-identificate nel [report attività](user-activity-report.md) utente di Teams e nei [report sull'utilizzo dei dispositivi di Teams.](device-usage-report.md) Non influirà sugli altri report di utilizzo disponibili nell'interfaccia di amministrazione di Teams.
