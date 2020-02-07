---
title: Uso dell'analisi delle chiamate per risolvere problemi di bassa qualità delle chiamate
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Usare i dettagli di analisi delle chiamate su dispositivi, reti e connettività per risolvere i problemi degli utenti con le chiamate e le riunioni di Microsoft teams e Skype for business.
ms.openlocfilehash: a9ef3265fa86349ef92c6174c6f561b006af4d1a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836766"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>Uso dell'analisi delle chiamate per risolvere problemi di bassa qualità delle chiamate

L'analisi delle chiamate consente di risolvere i problemi di chiamata o di connessione con Microsoft teams e Skype for business. Chiamata analitica Mostra informazioni dettagliate sui dispositivi, le reti e la connettività per le chiamate e le riunioni di ogni utente nell'account di Office 365. Se le informazioni relative a compilazione, sito e tenant sono state aggiunte all'analisi delle chiamate, verranno visualizzate anche per ogni chiamata e sessione. Le informazioni disponibili tramite le funzionalità di analisi delle chiamate consentono di individuare il motivo per cui un utente ha ricevuto una chiamata o un'esperienza di riunione scadente. 
  
## <a name="call-analytics-permissions"></a>Autorizzazioni di analisi delle chiamate

L'amministratore riceverà l'accesso completo a tutte le caratteristiche di Call Analytics. È inoltre possibile assegnare ruoli di Azure Active Directory per supportare il personale. Assegnare il ruolo di specialista delle comunicazioni di teams agli utenti che dovrebbero avere una visione limitata dell'analisi delle chiamate. Assegnare il ruolo di assistente tecnico comunicazioni teams agli utenti che hanno bisogno di accedere alle funzionalità complete di analisi delle chiamate. Entrambi i livelli di autorizzazione impediscono l'accesso al resto dell'interfaccia di amministrazione di Microsoft teams.

Gli specialisti del supporto delle comunicazioni gestiscono i problemi di qualità delle chiamate di base. Non analizzano i problemi relativi alle riunioni. Raccolgono invece informazioni correlate e poi escalano in un tecnico del supporto delle comunicazioni. Gli ingegneri del supporto delle comunicazioni visualizzano informazioni in registri di chiamate dettagliati nascosti dagli specialisti del supporto delle comunicazioni. La tabella seguente offre una panoramica delle informazioni disponibili per gli specialisti del supporto delle comunicazioni e per gli ingegneri del supporto delle comunicazioni quando usano le analisi delle chiamate.

Il livello di autorizzazione assegnato determina il tipo di informazioni a cui si ha accesso in Call Analytics:
  
- Amministratore del **servizio teams o amministratore di team Communications**: è possibile accedere a tutte le informazioni in Call Analytics e nell'interfaccia di amministrazione di Microsoft teams.
    
- **Specialista supporto comunicazioni teams**: viene visualizzato un set limitato di dati in Call Analytics. È possibile risolvere i problemi relativi alle chiamate, ma le riunioni vengono risolte in un team di supporto tecnico per le comunicazioni. Non si ha accesso al resto dell'interfaccia di amministrazione di Microsoft teams.
    
- **Assistente tecnico comunicazioni teams**: vengono visualizzati tutti i dati disponibili in analisi delle chiamate e possono essere utili per la risoluzione dei problemi relativi a chiamate e riunioni. Non si ha accesso al resto dell'interfaccia di amministrazione di Microsoft teams.
    
> [!NOTE]
> Il ruolo di specialista del supporto delle comunicazioni equivale al supporto di Tier 1 e il ruolo dell'ingegnere del supporto delle comunicazioni equivale al supporto di Tier 2.

Per altre informazioni sui ruoli di amministratore di teams, vedere [usare i ruoli di amministratore di Microsoft teams per gestire i team](using-admin-roles.md). Per un confronto dettagliato tra i ruoli di supporto tecnico comunicazioni di teams Specialist e teams support, vedere [configurare l'analisi delle chiamate](set-up-call-analytics.md#set-call-analytics-permissions) 
  
Vedere l'amministratore di teams e Skype for business se serve aiuto con le autorizzazioni.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>Risolvere i problemi di qualità delle chiamate con l'analisi delle chiamate

1. Accedere con le credenziali di supporto delle comunicazioni teams o di amministratore teams.

2. Nel Web browser andare a *https://admin.teams.microsoft.com*.
    
3. Nel **Dashboard**, in **ricerca utente**, iniziare a digitare il nome o l'indirizzo SIP dell'utente le cui chiamate si vuole risolvere o selezionare **Visualizza utenti** per visualizzare un elenco di utenti.
    
    ![Schermata della casella di ricerca dell'utente di analisi delle chiamate](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. Selezionare l'utente nell'elenco.

5. Selezionare **cronologia chiamate**e quindi selezionare la chiamata o la riunione che si vuole risolvere.
    
    ![Screenshot della pagina della cronologia delle chiamate per un utente.](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. Selezionare la scheda **Avanzate** e cercare gli elementi gialli e rossi che indicano la qualità della chiamata o i problemi di connessione.
    
    Nei dettagli della sessione per ogni chiamata o riunione, i problemi secondari vengono visualizzati in giallo. Ad esempio, nella schermata seguente i valori sono in giallo per jitter medio, jitter Max e percentuale media di perdita di pacchetti. Se qualcosa è giallo, è al di fuori dell'intervallo normale e può contribuire al problema, ma è improbabile che sia la causa principale del problema. Se qualcosa è rosso, è un problema significativo ed è probabilmente la causa principale della scarsa qualità delle chiamate per questa sessione. 
    
    ![Screenshot della scheda Avanzate della cronologia chiamate di un utente ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
In rari casi, la qualità dei dati dell'esperienza non viene ricevuta per le sessioni audio. Spesso questa operazione è causata dalla chiamata in calo e la connessione al client termina. In questo caso, la valutazione della sessione non è **disponibile**.
  
Per le sessioni audio in cui sono presenti dati QoE (Quality of Experience), la tabella seguente descrive i problemi principali che qualificano una sessione come **poveri**.
  
|**Problema**|**Zona**|**Descrizione**|
|:-----|:-----|:-----|
|Configurazione chiamata  <br/> |Sessione  <br/> |Il codice di errore MS-diag 20-29 indica che la configurazione delle chiamate non è riuscita. L'utente non ha potuto partecipare alla chiamata o alla riunione.  <br/> |
|Chiamata scadente della rete audio classificata  <br/> |Sessione  <br/> |Sono stati rilevati problemi di qualità della rete, ad esempio perdita di pacchetti, jitter, degradazione NMOS, RTT o rapporto nascosto. Per altre informazioni sulle condizioni usate per classificare le chiamate scadenti, vedere questo [post di Blog Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133).  <br/> |
|Dispositivo non funzionante  <br/> |Dispositivo  <br/> | Un dispositivo non funziona correttamente. I rapporti tra dispositivi non funzionanti sono: <br/>  DeviceRenderNotFunctioningEventRatio >= 0,005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0,005 <br/> |
   
## <a name="related-topics"></a>Argomenti correlati
[Configurare l'analisi delle chiamate](set-up-call-analytics.md)

[Analisi delle chiamate e Dashboard Qualità della chiamata](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
