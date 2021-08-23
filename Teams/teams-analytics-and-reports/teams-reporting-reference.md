---
title: Microsoft Teams analisi e creazione di report
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
description: In questo articolo sono disponibili informazioni sui report Teams disponibili nell'interfaccia Microsoft Teams amministrazione.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 61e40646318105d633b14d44a2eb8bfe41f13fa8
ms.sourcegitcommit: 9062b2c81c582ddc878c825ba1b22a6c23ca4b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2021
ms.locfileid: "58399105"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Microsoft Teams analisi e creazione di report

Una nuova esperienza di analisi e creazione di report per Microsoft Teams è disponibile nell'interfaccia Microsoft Teams di amministrazione. È possibile eseguire report diversi per ottenere informazioni dettagliate sul modo in cui gli utenti dell'organizzazione usano Teams. Ad esempio, è possibile vedere quanti utenti comunicano tramite i messaggi di canale e chat e i tipi di dispositivi che usano per connettersi a Teams. L'organizzazione può usare le informazioni dei report per comprendere meglio i modelli di utilizzo, prendere decisioni aziendali e informare gli sforzi di formazione e comunicazione.

## <a name="how-to-access-the-reports"></a>Come accedere ai report

Per accedere ai report, è necessario essere un amministratore globale di Microsoft 365 o Office 365, un lettore globale in Microsoft 365 o Office 365, un amministratore del servizio Teams o un Skype for Business amministratore. Per altre informazioni sui Teams di amministratore e sui report a cui ogni ruolo di amministratore può accedere, vedere Usare i ruoli di amministratore di Teams per [gestire](../using-admin-roles.md)Teams .

Passare all'interfaccia Microsoft Teams, nel riquadro di spostamento sinistro, selezionare Report di analisi & e **quindi in** **Report** scegliere il report da eseguire.

> [!NOTE]
> I report nell'interfaccia di amministrazione di Microsoft Teams sono separati dai report attività per Teams che fanno parte dei report Microsoft 365 nel interfaccia di amministrazione di Microsoft 365. Per altre informazioni sui report attività nel interfaccia di amministrazione di Microsoft 365, vedere Teams [report attività nel interfaccia di amministrazione di Microsoft 365](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams di riferimento per la creazione di report

Ecco un elenco dei report Teams disponibili nell'interfaccia di amministrazione di Microsoft Teams e una panoramica di alcune informazioni disponibili in ogni report.

Stiamo continuamente migliorando l'esperienza Teams creazione di report e l'aggiunta di caratteristiche e funzionalità. Nel corso del tempo, verranno integrate funzionalità aggiuntive nei report e verranno aggiunti nuovi report nell'interfaccia di amministrazione Microsoft Teams di amministrazione.

|Report  |Cosa viene misurato? |
|---------|---------|
|[Report sull'utilizzo di Teams](teams-usage-report.md)  |  Utenti attivi<br/>Utenti attivi in team e canali<br/>Canali attivi<br/>Messaggi<br/>Impostazione della privacy dei team<br/>Guest in un team   |
|[Report sulle attività degli utenti di Teams](user-activity-report.md)  | Messaggi pubblicati da un utente in una chat del team<br/>Messaggi pubblicati da un utente in una chat privata<br/>  Chiamate 1:1 a cui un utente ha partecipato<br/> Numero di riunioni organizzate dall'utente <br/>numero di partecipanti alla riunione<br/>Tempo di condivisione audio, video e schermo delle riunioni<br/>   Data ultima attività di un utente     |
|[Report sull'uso dei dispositivi di Teams](device-usage-report.md)   |  Utenti di Windows<br/>Utenti Mac<br/>Utenti iOS<br/>Utenti di telefoni Android     |
|[Report sull'uso degli eventi live di Teams](teams-live-event-usage-report.md)   |  Visualizzazioni totali<br>Ora di inizio<br>Stato dell'evento<br>Organizzatore<br>Relatore<br>Produttore<br>Impostazione della registrazione<br>Tipo di produzione    |
|[Teams Report utenti bloccati PSTN](pstn-blocked-users-report.md)   |  Nome visualizzato<br>Telefono numero<br>Motivo<br>Tipo di azione<br>Data e ora dell'azione   |
|[Teams Report pool di minuti PSTN](pstn-minute-pools-report.md) |  Paese o area geografica<br>Capability (licenza) <br>Totale minuti<br>Minuti usati<br>Minuti disponibili|
|[Teams Report sull'utilizzo PSTN - Piani per chiamate](pstn-usage-report.md#calling-plans)|  Indicatore data e ora<br>Nome utente<br>Telefono numero<br>Tipo di chiamata <br>Chiamato a<br>A paese o area geografica <br>Chiamata da <br>Da paese o area geografica<br>Addebito<br>Valuta<br>Durata<br>Nazionale/Internazionale<br>ID chiamata<br>Tipo di numero<br>Paese o area geografica<br>ID conferenza<br>Capability (licenza)|
|[Teams Report utilizzo PSTN - Routing diretto](pstn-usage-report.md#direct-routing)  |  Indicatore data e ora<br>Nome visualizzato<br>Indirizzo SIP<br>Telefono numero <br>Tipo di chiamata<br>Chiamato a<br>Ora di inizio<br>Ora di invito<br>Tempo di errore<br>Ora di fine<br>Durata<br>Tipo di numero<br>Bypass multimediale<br>SBC FQDN<br>Area geografica di Azure<br>Tipo di evento<br>Codice SIP finale<br>Sottocodice Microsoft finale<br>Frase SIP finale<br>ID correlazione  |
|[Teams report sulle licenze di protezione delle informazioni - Routing diretto](information-protection-license-report.md)  | <br>Se gli utenti hanno licenze valide per inviare i messaggi tramite notifiche di modifica</br><br>Numero totale di eventi di notifica delle modifiche attivati da un utente</br><br>Quali app ascoltano gli eventi di notifica delle modifiche a livello di organizzazione</br>|


[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati Teams'attività degli utenti e Teams di utilizzo dei dispositivi, è necessario essere un amministratore globale. In questo modo si nasconderanno informazioni identificabili come il nome visualizzato, la posta elettronica e l'ID AAD nei report e nelle relative esportazioni.

1. In interfaccia di amministrazione di Microsoft 365 passare alla  scheda Impostazioni Org Impostazioni e nella scheda Servizi \> scegliere **Report.** 
    
2. Selezionare **Report** e quindi scegliere **Visualizza identificatori anonimi**. Questa impostazione viene applicata sia ai report di utilizzo in interfaccia di amministrazione di Microsoft 365 che all'Teams di amministrazione.
  
3. Selezionare **Salva modifiche**.

> [!NOTE]
> Se si abilita questa impostazione, le informazioni verranno de-identificate Teams [report attività utente](user-activity-report.md) e Teams report [sull'utilizzo dei](device-usage-report.md) dispositivi. Non influisce sugli altri report di utilizzo disponibili nell'Teams di amministrazione.
