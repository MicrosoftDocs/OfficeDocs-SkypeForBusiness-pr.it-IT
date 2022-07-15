---
title: Analisi e creazione di report di Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 02acd95084b814e6f49634972eebeedfdeeb9472
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825860"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Analisi e creazione di report di Microsoft Teams

Nell'interfaccia di amministrazione di Microsoft Teams è disponibile una nuova esperienza di analisi e creazione di report per Microsoft Teams. È possibile eseguire report diversi per ottenere informazioni approfondite sul modo in cui gli utenti dell'organizzazione usano Teams. Ad esempio, è possibile vedere quanti utenti comunicano tramite messaggi di canale e chat e i tipi di dispositivi che usano per connettersi a Teams. L'organizzazione può usare le informazioni dei report per comprendere meglio i modelli di utilizzo, prendere decisioni aziendali e informare le attività di formazione e comunicazione.

## <a name="how-to-access-the-reports"></a>Come accedere ai report

Per accedere ai report, è necessario essere un amministratore globale in Microsoft 365 o Office 365, un lettore globale in Microsoft 365 o Office 365, un amministratore del servizio Teams o un amministratore Skype for Business. Per altre informazioni sui ruoli di amministratore di Teams e sui report a cui può accedere ogni ruolo di amministratore, vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md).

Passare all'interfaccia di amministrazione di Microsoft Teams, nel riquadro di spostamento sinistro selezionare **Analisi & report** e quindi in **Visualizza report** scegliere il report da eseguire.

> [!NOTE]
> I report nell'interfaccia di amministrazione di Microsoft Teams sono separati dai report attività per Teams che fanno parte dei report di Microsoft 365 nella interfaccia di amministrazione di Microsoft 365. Per altre informazioni sui report attività nel interfaccia di amministrazione di Microsoft 365, vedere [Report attività di Teams nella interfaccia di amministrazione di Microsoft 365](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Riferimento per la creazione di report di Teams

Ecco un elenco dei report di Teams disponibili nell'interfaccia di amministrazione di Microsoft Teams e una panoramica di alcune delle informazioni disponibili in ogni report.

Stiamo migliorando continuamente l'esperienza di creazione di report di Teams e l'aggiunta di funzionalità e funzionalità. Nel corso del tempo, verranno inserite funzionalità aggiuntive nei report e aggiunti nuovi report nell'interfaccia di amministrazione di Microsoft Teams.

|Report  |Cosa viene misurato? |
|---------|---------|
|[Report sull'utilizzo di Teams](teams-usage-report.md)  |  Utenti attivi<br/>Utenti attivi in team e canali<br/>Canali attivi<br/>Messaggi<br/>Impostazione della privacy dei team<br/>Guest in un team   |
|[Report sulle attività degli utenti di Teams](user-activity-report.md)  | Messaggi pubblicati da un utente in una chat del team<br/>Messaggi pubblicati da un utente in una chat privata<br/>  Chiamate 1:1 a cui ha partecipato un utente<br/> Numero di riunioni organizzate dall'utente <br/>Numero di riunioni a cui l'utente ha partecipato<br/>Tempo di condivisione audio, video e schermo per le riunioni<br/>   Data ultima attività di un utente     |
|[Report sull'uso dei dispositivi di Teams](device-usage-report.md)   |  Utenti di Windows<br/>Utenti Mac<br/>Utenti iOS<br/>Utenti di telefoni Android     |
|[Report sull'uso degli eventi live di Teams](teams-live-event-usage-report.md)   |  Totale visualizzazioni<br>Ora di inizio<br>Stato evento<br>Organizzatore<br>Presentatore<br>Produttore<br>Impostazione della registrazione<br>Tipo di produzione    |
|[Report utenti pstn bloccati di Teams](pstn-blocked-users-report.md)   |  Nome visualizzato<br>Numero di telefono<br>Motivo<br>Tipo di azione<br>Data e ora dell'azione   |
|[Report pool di minuti PSTN di Teams](pstn-minute-pools-report.md) |  Paese o area geografica<br>Funzionalità (licenza) <br>Totale minuti<br>Minuti utilizzati<br>Minuti disponibili|
|[Report utilizzo PSTN di Teams - Piani per chiamate](pstn-usage-report.md#calling-plans)|  Indicatore data e ora<br>Nome utente<br>Numero di telefono<br>Tipo di chiamata <br>Chiamato a<br>Nel paese o nell'area geografica <br>Chiamato da <br>Da paese o area geografica<br>Carica<br>Valuta<br>Durata<br>Nazionali/Internazionali<br>ID chiamata<br>Tipo di numero<br>Paese o area geografica<br>ID conferenza<br>Funzionalità (licenza)|
|[Report sull'utilizzo PSTN di Teams - Routing diretto](pstn-usage-report.md#direct-routing)  |  Indicatore data e ora<br>Nome visualizzato<br>Indirizzo SIP<br>Numero di telefono <br>Tipo di chiamata<br>Chiamato a<br>Ora di inizio<br>Ora invito<br>Ora errore<br>Ora di fine<br>Durata<br>Tipo di numero<br>Bypass multimediale<br>SBC FQDN<br>Area geografica di Azure<br>Tipo di evento<br>Codice SIP finale<br>Sottocodice Microsoft finale<br>Frase SIP finale<br>ID correlazione  |
|[Report sulle licenze di Teams per la protezione delle informazioni](information-protection-license-report.md)  | <br>Se gli utenti hanno licenze valide per inviare i messaggi tramite notifiche di modifica</br><br>Numero totale di eventi di notifica di modifica generati da un utente<br><br>Quali app ascoltano gli eventi di notifica delle modifiche a livello di organizzazione<br>|
|[Report sull'utilizzo delle visite virtuali di Teams](/microsoft-365/frontline/virtual-visits-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)  | Numero di appuntamenti virtuali<br>Numero di appuntamenti di Bookings<br>Numero di appuntamenti integrati con EHR (Electronic Health Records) di Teams<br>Durata media di un appuntamento<br>Tempo medio di attesa della sala di attesa dei partecipanti<br>Ora di inizio<br>ID riunione<br>Tempo di attesa nella sala d'attesa<br>Durata<br>Stato<br>Tipo di prodotto<br>Partecipanti<br>SMS inviato
|[Report Appuntamenti virtuali connettore EHR di Teams](/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) | Ora di inizio<br>Durata<br>Principale (nome dell'organizzatore della riunione)<br>E-mail principale (e-mail dell'organizzatore della riunione)<br>Reparto<br>Assistenti<br>Tempo di attesa nella sala d'attesa<br>Se l'appuntamento rientra nel limite di allocazione|
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati nelle attività degli utenti di Teams e nei report sull'utilizzo dei dispositivi di Teams, è necessario essere un amministratore globale. Le informazioni identificabili, ad esempio il nome visualizzato, la posta elettronica e l'ID Microsoft Azure Active Directory, verranno nascoste nei report e nelle relative esportazioni.

1. In interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** \> **impostazioni organizzazione** e, nella scheda **Servizi**, scegliere **Report**.
    
2. Selezionare **Report** e quindi scegliere **Visualizza nomi di utenti, gruppi e siti nascosti in tutti i report**. Questa impostazione viene applicata sia ai report sull'utilizzo in interfaccia di amministrazione di Microsoft 365 che all'interfaccia di amministrazione di Teams.
  
3. Selezionare **Salva modifiche**.

> [!NOTE]
> L'abilitazione di questa impostazione deidentificerà le informazioni nel [report attività degli utenti di Teams](user-activity-report.md) e nei report [sull'utilizzo dei dispositivi di Teams](device-usage-report.md) . Non influirà su altri report sull'utilizzo disponibili nell'interfaccia di amministrazione di Teams.
> Questa impostazione si applica anche ai report sull'utilizzo di Microsoft 365 in interfaccia di amministrazione di Microsoft 365, Microsoft Graph e Power BI.
