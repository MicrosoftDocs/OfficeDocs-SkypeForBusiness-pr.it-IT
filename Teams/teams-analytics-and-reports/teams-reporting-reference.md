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
- m365initiative-meetings
description: In questo articolo vengono fornite informazioni sui report di Teams disponibili nell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1062afeebfde89835330fbc4f367e0fccbe01513
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2023
ms.locfileid: "69845923"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Analisi e creazione di report di Microsoft Teams

Nell'interfaccia di amministrazione di Microsoft Teams è disponibile una nuova esperienza di analisi e creazione di report per Microsoft Teams. È possibile eseguire report diversi per ottenere informazioni approfondite sul modo in cui gli utenti dell'organizzazione usano Teams. Ad esempio, è possibile vedere quanti utenti comunicano tramite messaggi di canale e chat e i tipi di dispositivi che usano per connettersi a Teams. L'organizzazione può usare le informazioni dei report per comprendere meglio i modelli di utilizzo, prendere decisioni aziendali e informare le attività di formazione e comunicazione.

## <a name="how-to-access-the-reports"></a>Come accedere ai report

Per accedere ai report, è necessario essere assegnati a uno dei ruoli seguenti:

- amministratore globale.
- Teams o amministratore Skype for Business.
- Lettore globale (solo dati aggregati a livello di tenant e nessun dato per utente o team).

Per altre informazioni sui ruoli di amministratore di Teams e sui report a cui può accedere ogni ruolo di amministratore, vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md).

Passare all'interfaccia di amministrazione di Microsoft Teams, nel riquadro di spostamento sinistro selezionare **Analisi & report** e quindi in **Visualizza report** scegliere il report da eseguire.

> [!NOTE]
> I report nell'interfaccia di amministrazione di Microsoft Teams sono separati dai report attività per Teams che fanno parte dei report di Microsoft 365 nella interfaccia di amministrazione di Microsoft 365. Per altre informazioni sui report attività nel interfaccia di amministrazione di Microsoft 365, vedere [Report di Microsoft 365 nell'interfaccia di amministrazione](/microsoft-365/admin/activity-reports/activity-reports).

## <a name="teams-reporting-reference"></a>Riferimento per la creazione di report di Teams

Ecco un elenco dei report di Teams disponibili nell'interfaccia di amministrazione di Microsoft Teams in diversi ambienti e una panoramica di alcune delle informazioni disponibili in ogni report.

Stiamo migliorando continuamente l'esperienza di creazione di report di Teams e l'aggiunta di funzionalità e funzionalità. Nel corso del tempo, verranno inserite funzionalità aggiuntive nei report e aggiunti nuovi report nell'interfaccia di amministrazione di Microsoft Teams.

|Report  |Pubblico |GCC |GCCH |Dod |Cosa viene misurato? |
|---------|---------|---------|---------|---------|---------|
|[Report sull'utilizzo di Teams](teams-usage-report.md)  |Sì|Sì|Sì|Sì|  Utenti attivi<br/>Utenti attivi in team e canali<br/>Canali attivi<br/>Messaggi<br/>Impostazione della privacy dei team<br/>Guest attivi in un team  <br/>Utenti esterni attivi (nei canali condivisi)<br/>Dettagli specifici del canale condiviso all'interno di un team (nuovo)|
|[Report sulle attività degli utenti di Teams](user-activity-report.md)  |Sì|Sì|Sì|Sì|Utenti interni ed esterni attivi (nei canali condivisi)<br/> Messaggi pubblicati da un utente in una chat del team<br/>Messaggi pubblicati da un utente in una chat privata<br/>  Chiamate 1:1 a cui ha partecipato un utente<br/> Numero di riunioni organizzate dall'utente <br/>Numero di riunioni a cui l'utente ha partecipato<br/>Tempo di condivisione audio, video e schermo per le riunioni<br/>   Data ultima attività di un utente  <br>Interazioni del canale condiviso di un utente (nuovo)</br>   |
|[Report sull'uso dei dispositivi di Teams](device-usage-report.md)   |Sì|Sì|Sì|Sì|  Utenti di Windows<br/>Utenti Mac<br/>Utenti iOS<br/>Utenti di telefoni Android     |
|[Report utilizzo app Teams (nuovo)](app-usage-report.md)   |Sì|Sì|No|No|  Totale utenti attivi dell'app<br/>Totale team attivi con l'app<br/>Totale app installate (nuove)<br/>Totale app inattive <br/>Utilizzo totale dell'app 1P vs 3P rispetto a LoB (nuovo)     |
|[Report sull'uso degli eventi live di Teams](teams-live-event-usage-report.md)   |Sì|Sì|No|No|  Totale visualizzazioni<br>Ora di inizio<br>Stato evento<br>Organizzatore<br>Presentatore<br>Produttore<br>Impostazione della registrazione<br>Tipo di produzione    |
|[Report utenti pstn bloccati di Teams](pstn-blocked-users-report.md)   |Sì|Sì|No|No|  Nome visualizzato<br>Numero di telefono<br>Motivo<br>Tipo di azione<br>Data e ora dell'azione   |
|[Report pool di minuti PSTN di Teams](pstn-minute-pools-report.md) |Sì|Sì|No|No|  Paese o area geografica<br>Funzionalità (licenza) <br>Totale minuti<br>Minuti utilizzati<br>Minuti disponibili|
|[Report utilizzo PSTN di Teams - Piani per chiamate](pstn-usage-report.md#calling-plans)|Sì|Sì|No|No|  Indicatore data e ora<br>Nome utente<br>Numero di telefono<br>Tipo di chiamata <br>Chiamato a<br>Nel paese o nell'area geografica <br>Chiamato da <br>Da paese o area geografica<br>Carica<br>Valuta<br>Durata<br>Nazionali/Internazionali<br>ID chiamata<br>Tipo di numero<br>Paese o area geografica<br>ID conferenza<br>Funzionalità (licenza)|
|[Report sull'utilizzo PSTN di Teams - Routing diretto](pstn-usage-report.md#direct-routing)  |Sì|Sì|No|No|  Indicatore data e ora<br>Nome visualizzato<br>Indirizzo SIP<br>Numero di telefono <br>Tipo di chiamata<br>Chiamato a<br>Ora di inizio<br>Ora invito<br>Ora errore<br>Ora di fine<br>Durata<br>Tipo di numero<br>Bypass multimediale<br>SBC FQDN<br>Area geografica di Azure<br>Tipo di evento<br>Codice SIP finale<br>Sottocodice Microsoft finale<br>Frase SIP finale<br>ID correlazione  |
|[Report sulle licenze di Teams per la protezione delle informazioni](information-protection-license-report.md)  |Sì|Sì|No|No| <br>Se gli utenti hanno licenze valide per inviare i messaggi tramite notifiche di modifica</br><br>Numero totale di eventi di notifica di modifica generati da un utente<br><br>Quali app ascoltano gli eventi di notifica delle modifiche a livello di organizzazione<br>|
|[Report sull'utilizzo di Teams Appuntamenti virtuali](/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)|Sì|Sì|No|No| Numero di appuntamenti virtuali<br>Numero di appuntamenti di Bookings<br>Numero di appuntamenti integrati con EHR (Electronic Health Records) di Teams<br>Durata media di un appuntamento<br>Tempo medio di attesa della sala di attesa dei partecipanti<br>Ora di inizio<br>ID riunione<br>Tempo di attesa nella sala d'attesa<br>Durata<br>Stato<br>Tipo di prodotto<br>Partecipanti<br>Reparto<br>SMS inviato<br>Se l'appuntamento ha usato una funzionalità di Appuntamenti virtuali avanzata|
|[Report attività di Teams Advanced Appuntamenti virtuali](/microsoft-365/frontline/advanced-virtual-appointments-activity-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |Sì|Sì|No|No|Numero di utenti che usano funzionalità di Appuntamenti virtuali avanzate<br>Numero di utenti che utilizzano notifiche SMS<br>Numero di utenti che usano la chat della sala di attesa (presto disponibile)<br>Numero di utenti che conducono appuntamenti su richiesta|
|[Report Appuntamenti virtuali connettore EHR di Teams](/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |Sì|Sì|No|No| Ora di inizio<br>Durata<br>Principale (nome dell'organizzatore della riunione)<br>E-mail principale (e-mail dell'organizzatore della riunione)<br>Reparto<br>Assistenti<br>Tempo di attesa nella sala d'attesa<br>Se l'appuntamento rientra nel limite di allocazione|
|[Report sull'utilizzo e le prestazioni di Walkie-talkie](walkie-talkie-usage-report.md) |Sì|Sì|No|No| Le metriche includono il numero di trasmissioni push-to-talk (PTT) effettuate e ricevute, l'attività del canale, la durata della trasmissione e i dettagli di dispositivo e partecipante.|
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonime le informazioni identificabili nei report sull'utilizzo, è necessario essere un amministratore globale. Il amministratore globale può nascondere le informazioni identificabili (usando hash MD5), ad esempio il nome visualizzato, il nome del gruppo, la posta elettronica e l'ID AAD nel report e nella relativa esportazione.

1. In interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** \> **impostazioni organizzazione** e, nella scheda **Servizi**, scegliere **Report**.
    
2. Selezionare **Report** e quindi scegliere **Visualizza nomi di utenti, gruppi e siti nascosti in tutti i report**. Questa impostazione viene applicata sia ai report sull'utilizzo in interfaccia di amministrazione di Microsoft 365 che all'interfaccia di amministrazione di Teams.
  
3. Selezionare **Salva modifiche**.

> [!NOTE]
> L'abilitazione di questa impostazione deidentificherà le informazioni sul nome di utenti, gruppi e siti nel [report Attività utente di Teams](user-activity-report.md), nel [report Sull'utilizzo dei dispositivi di Teams](device-usage-report.md) e nel [report sull'utilizzo di Teams](teams-usage-report.md). A partire dal 1° settembre 2021, questa impostazione è abilitata per impostazione predefinita per tutti gli utenti nell'ambito del nostro costante impegno per proteggere le informazioni importanti e consentire alle aziende di supportare le leggi locali sulla privacy. 
>
>Questa impostazione si applica anche ai report sull'utilizzo di Microsoft 365 in interfaccia di amministrazione di Microsoft 365, Microsoft Graph e Power BI.
