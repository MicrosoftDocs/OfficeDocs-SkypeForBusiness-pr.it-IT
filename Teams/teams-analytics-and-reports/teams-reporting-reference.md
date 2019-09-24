---
title: Analisi e creazione di report di Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.analyticsandreports.overview
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Informazioni sui report Team disponibili nell'interfaccia di amministrazione di Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: de405a89b74a5e772e0f3d58027592d2e6ae4289
ms.sourcegitcommit: f1c4255b52576c602d528c580941404eb547bc78
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "37131576"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Analisi e creazione di report di Microsoft Teams

Nell'interfaccia di amministrazione di Microsoft teams è disponibile una nuova esperienza di analisi e creazione di report per Microsoft teams. È possibile eseguire report diversi per ottenere informazioni approfondite sul modo in cui gli utenti dell'organizzazione usano team. Ad esempio, puoi vedere il numero di utenti che comunicano tramite il canale e i messaggi di chat e i tipi di dispositivi che usano per connettersi ai team. L'organizzazione può usare le informazioni dei report per comprendere meglio i modelli di utilizzo, contribuire a prendere decisioni aziendali e informare gli sforzi di formazione e comunicazione.

## <a name="how-to-access-the-reports"></a>Come accedere ai report

Per accedere ai report, è necessario essere un amministratore globale in Office 365, amministratore del servizio teams o amministratore di Skype for business.  Passare all'interfaccia di amministrazione di Microsoft teams, nella barra di spostamento sinistra, selezionare **analisi & report**e quindi in **report**scegliere il report che si vuole eseguire.

> [!NOTE]
> I report nell'interfaccia di amministrazione di Microsoft teams sono distinti dai report attività per i team che fanno parte dei report di Office 365 nell'interfaccia di amministrazione di Microsoft 365. Per altre informazioni sui report attività nell'interfaccia di amministrazione di Microsoft 365, vedere [report attività in teams nell'interfaccia di amministrazione di microsoft 365](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Riferimento per la creazione di report Team

Ecco un elenco dei report Team disponibili nell'interfaccia di amministrazione di Microsoft teams e una panoramica di alcune delle informazioni disponibili in ogni report.

Stiamo migliorando continuamente l'esperienza di creazione di report in teams e aggiungendo funzionalità e funzionalità. Nel corso del tempo verranno costruite funzionalità aggiuntive nei report e si aggiungono nuovi report nell'interfaccia di amministrazione di Microsoft teams.

|Report  |Cosa viene misurato? |
|---------|---------|
|[Report sull'utilizzo di Teams](teams-usage-report.md)  |  Utenti attivi<br/>Utenti attivi in team e canali<br/>Canali attivi<br/>Messaggi<br/>Impostazione della privacy di Teams<br/>Guest in un team   |
|[Report attività utente Teams](user-activity-report.md)  |  1:1 chiama un utente a cui ha partecipato<br/>Messaggi inviati da un utente in una chat del team<br/>Messaggi inviati da un utente in una chat privata<br/>Data ultima attività di un utente     |
|[Report sull'utilizzo di dispositivi Teams](device-usage-report.md)   |  Utenti di Windows:<br/>Utenti Mac<br/>utenti iOS<br/>Utenti di telefoni Android     |
|[Report sull'utilizzo dell'evento teams Live](teams-live-event-usage-report.md)   |  Visualizzazioni totali<br>Ora di inizio<br>Stato evento<br>Organizzatore<br>Relatore<br>Produttore<br>Impostazione di registrazione<br>Tipo di produzione    |
|[Report utenti bloccati PSTN di Teams](pstn-blocked-users-report.md)   |  Nome visualizzato<br>Numero di telefono<br>Motivo<br>Tipo di azione<br>Data e ora di azione   |
|[Report utilizzo PSTN teams-piani per chiamate](pstn-usage-report.md#calling-plans)|  Indicatore di data e ora<br>Nome utente<br>Numero di telefono<br>Tipo di chiamata <br>Chiamata a<br>In un paese o in un'area geografica <br>Chiamata da <br>Da paese o area geografica<br>Addebito<br>Valuta<br>Durata<br>Nazionali/internazionali<br>ID chiamata<br>Tipo di numero<br>Paese o area geografica<br>ID conferenza<br>Funzionalità (licenza)|
|[Report utilizzo PSTN teams-routing diretto](pstn-usage-report.md#direct-routing)  |  Indicatore di data e ora<br>Nome visualizzato<br>Indirizzo SIP<br>Numero di telefono <br>Tipo di chiamata<br>Chiamata a<br>Ora di inizio<br>Invitare il tempo<br>Tempo di errore<br>Ora di fine<br>Durata<br>Tipo di numero<br>Bypass multimediale<br>FQDN DI SBC<br>Area di Azure<br>Tipo di evento<br>Codice SIP finale<br>Sottocodice Microsoft finale<br>Frase SIP finale<br>ID di coorelation  |

> [!NOTE]
> I report teams mostrano i dati per utenti attivi e team attivi. Ad esempio, se un utente dell'organizzazione non è attivo in teams durante l'intervallo di date specificato per un report, i dati per l'utente non sono inclusi nel report.
