---
title: analisi Microsoft Teams e creazione di report
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: In questo articolo vengono fornite informazioni sui report di Teams disponibili nell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6a3cbf42c65d054befac8ad4e1f25d8be65f286
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853037"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>analisi Microsoft Teams e creazione di report

Nell'interfaccia di amministrazione di Microsoft Teams è disponibile una nuova esperienza di analisi e creazione di report per Microsoft Teams. È possibile eseguire report diversi per ottenere informazioni approfondite sul modo in cui gli utenti dell'organizzazione usano Teams. Ad esempio, puoi vedere quanti utenti comunicano tramite messaggi di canale e chat e i tipi di dispositivi che usano per connettersi a Teams. L'organizzazione può usare le informazioni dei report per comprendere meglio i modelli di utilizzo, prendere decisioni aziendali e informare le attività di formazione e comunicazione.

## <a name="how-to-access-the-reports"></a>Come accedere ai report

Per accedere ai report, è necessario essere un amministratore globale di Microsoft 365 o Office 365, un lettore globale in Microsoft 365 o Office 365, un amministratore del servizio Teams o un amministratore Skype for Business. Per altre informazioni sui ruoli di amministratore Teams e sui report a cui può accedere ogni ruolo di amministratore, vedere [Usare Teams ruoli di amministratore per gestire Teams](../using-admin-roles.md).

Passare all'interfaccia di amministrazione di Microsoft Teams, nel riquadro di spostamento sinistro selezionare **Analisi & report** e quindi in **Visualizza report** scegliere il report da eseguire.

> [!NOTE]
> I report nell'interfaccia di amministrazione di Microsoft Teams sono separati dai report attività per Teams che fanno parte dei report di Microsoft 365 nel interfaccia di amministrazione di Microsoft 365. Per altre informazioni sui report attività nel interfaccia di amministrazione di Microsoft 365, vedere [Teams report attività nel interfaccia di amministrazione di Microsoft 365](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams riferimento per la creazione di report

Ecco un elenco dei report di Teams disponibili nell'interfaccia di amministrazione di Microsoft Teams e una panoramica di alcune informazioni disponibili in ogni report.

Stiamo migliorando continuamente l'esperienza di creazione di report di Teams e l'aggiunta di caratteristiche e funzionalità. Nel corso del tempo verranno inserite funzionalità aggiuntive nei report e verranno aggiunti nuovi report nell'interfaccia di amministrazione di Microsoft Teams.

|Report  |Cosa viene misurato? |
|---------|---------|
|[Report sull'utilizzo di Teams](teams-usage-report.md)  |  Utenti attivi<br/>Utenti attivi in team e canali<br/>Canali attivi<br/>Messaggi<br/>Impostazione della privacy dei team<br/>Guest in un team   |
|[Report sulle attività degli utenti di Teams](user-activity-report.md)  | Messaggi pubblicati da un utente in una chat del team<br/>Messaggi pubblicati da un utente in una chat privata<br/>  Chiamate 1:1 a cui ha partecipato un utente<br/> Numero di riunioni organizzate dall'utente <br/>Numero di riunioni a cui l'utente ha partecipato<br/>Tempo di condivisione audio, video e schermo per le riunioni<br/>   Data ultima attività di un utente     |
|[Report sull'uso dei dispositivi di Teams](device-usage-report.md)   |  Utenti di Windows<br/>Utenti Mac<br/>Utenti iOS<br/>Utenti di telefoni Android     |
|[Report sull'uso degli eventi live di Teams](teams-live-event-usage-report.md)   |  Totale visualizzazioni<br>Ora di inizio<br>Stato evento<br>Organizzatore<br>Presentatore<br>Produttore<br>Impostazione della registrazione<br>Tipo di produzione    |
|[Report utenti bloccati PSTN Teams](pstn-blocked-users-report.md)   |  Nome visualizzato<br>Telefono numero<br>Motivo<br>Tipo di azione<br>Data e ora dell'azione   |
|[report pool di minuti PSTN Teams](pstn-minute-pools-report.md) |  Paese o area geografica<br>Funzionalità (licenza) <br>Totale minuti<br>Minuti utilizzati<br>Minuti disponibili|
|[Teams report utilizzo PSTN - Piani per chiamate](pstn-usage-report.md#calling-plans)|  Indicatore data e ora<br>Nome utente<br>Telefono numero<br>Tipo di chiamata <br>Chiamato a<br>Nel paese o nell'area geografica <br>Chiamato da <br>Da paese o area geografica<br>Carica<br>Valuta<br>Durata<br>Nazionali/Internazionali<br>ID chiamata<br>Tipo di numero<br>Paese o area geografica<br>ID conferenza<br>Funzionalità (licenza)|
|[Teams report sull'utilizzo di PSTN - Routing diretto](pstn-usage-report.md#direct-routing)  |  Indicatore data e ora<br>Nome visualizzato<br>Indirizzo SIP<br>Telefono numero <br>Tipo di chiamata<br>Chiamato a<br>Ora di inizio<br>Ora invito<br>Ora errore<br>Ora di fine<br>Durata<br>Tipo di numero<br>Bypass multimediale<br>SBC FQDN<br>Area geografica di Azure<br>Tipo di evento<br>Codice SIP finale<br>Sottocodice Microsoft finale<br>Frase SIP finale<br>ID correlazione  |
|[Teams report sulla licenza per la protezione delle informazioni](information-protection-license-report.md)  | <br>Se gli utenti hanno licenze valide per inviare i messaggi tramite notifiche di modifica</br><br>Numero totale di eventi di notifica di modifica generati da un utente<br><br>Quali app ascoltano gli eventi di notifica delle modifiche a livello di organizzazione<br>|
|[report sull'utilizzo delle visite virtuali Teams](virtual-visits-usage-report.md)  | Numero di appuntamenti virtuali<br>Numero di appuntamenti Bookings<br>Numero di appuntamenti integrati con Teams EHR (Electronic Health Records)<br>Durata media di un appuntamento<br>Tempo medio di attesa della sala di attesa dei partecipanti<br>Ora di inizio<br>ID riunione<br>Tempo di attesa nella sala d'attesa<br>Durata<br>Stato<br>Tipo di prodotto<br>Partecipanti<br>SMS inviato
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati in Teams'attività degli utenti e Teams report sull'utilizzo dei dispositivi, è necessario essere un amministratore globale. Le informazioni identificabili, ad esempio il nome visualizzato, la posta elettronica e l'ID Microsoft Azure Active Directory, verranno nascoste nei report e nelle relative esportazioni.

1. In interfaccia di amministrazione di Microsoft 365 passare alla **Impostazioni organizzazione** **Impostazioni** \> e scegliere **Report** nella scheda **Servizi**.
    
2. Selezionare **Report** e quindi scegliere **Visualizza nomi di utenti, gruppi e siti nascosti in tutti i report**. Questa impostazione viene applicata sia ai report sull'utilizzo in interfaccia di amministrazione di Microsoft 365 che all'interfaccia di amministrazione di Teams.
  
3. Selezionare **Salva modifiche**.

> [!NOTE]
> L'abilitazione di questa impostazione deidentificerà le informazioni in [Teams report attività utente](user-activity-report.md) e [Teams report sull'utilizzo dei dispositivi](device-usage-report.md). Non influirà sugli altri report sull'utilizzo disponibili nell Teams interfaccia di amministrazione.
> Questa impostazione si applica anche ai report di utilizzo di Microsoft 365 in interfaccia di amministrazione di Microsoft 365, Microsoft Graph e Power BI.
