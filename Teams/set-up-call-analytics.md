---
title: Configurare l'analisi delle chiamate
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
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
- NOCSH
ms.custom:
- Reporting
description: Configurare e usare le analisi delle chiamate per identificare e risolvere i problemi di qualità delle chiamate di Skype for business e Microsoft teams.
ms.openlocfilehash: 4b4ab2b60025169351e10a5a8cc3938d146e4f2d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693941"
---
# <a name="set-up-call-analytics"></a>Configurare l'analisi delle chiamate

Per i team o per gli amministratori di Skype for business online, puoi usare la chiamata analitica per risolvere i problemi di connessione e qualità delle chiamate di Skype for business e Microsoft teams. Può risultare utile configurare le funzionalità seguenti in analisi delle chiamate:
  
- Impostare le autorizzazioni per consentire ad altri dipendenti, ad esempio gli agenti helpdesk, di usare l'analisi delle chiamate, ma impedire l'accesso al resto dell'interfaccia di amministrazione di Microsoft teams. 
    
- Aggiungere informazioni su edifici, siti e tenant per chiamare Google Analytics caricando un file di dati con estensione TSV o CSV.
    
**L'analisi delle chiamate è ora disponibile nell'interfaccia di amministrazione di Microsoft teams**. Per visualizzare tutte le informazioni sulla chiamata e i dati per un utente, usare la scheda **cronologia chiamate** . A questo scopo, è possibile cercare nella pagina del profilo dell'utente eseguendo una delle operazioni seguenti:

- Cercare l'utente dal dashboard.
  
   ![Screenshot della ricerca degli utenti nel dashboard](media/set-up-call-analytics-image-1.png)

-  Selezionare **gli utenti** nella barra di spostamento sinistra.

   ![Screenshot della barra di spostamento sinistra](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>Impostare le autorizzazioni di analisi delle chiamate
<a name="BKMK_SetCAPerms"></a>

L'amministratore ha accesso completo a tutte le caratteristiche di Call Analytics. È inoltre possibile assegnare ruoli di Azure Active Directory per supportare il personale. Assegnare il ruolo di specialista delle comunicazioni di teams agli utenti che dovrebbero avere una visione limitata dell'analisi delle chiamate. Assegnare il ruolo di assistente tecnico comunicazioni teams agli utenti che hanno bisogno di accedere alle funzionalità complete di analisi delle chiamate. Entrambi i livelli di autorizzazione impediscono l'accesso al resto dell'interfaccia di amministrazione di Microsoft teams.

> [!NOTE]
> Il ruolo di specialista del supporto delle comunicazioni equivale al supporto di Tier 1 e il ruolo dell'ingegnere del supporto delle comunicazioni equivale al supporto di Tier 2.

Per altre informazioni sui ruoli di amministratore di teams, vedere [usare i ruoli di amministratore di Microsoft teams per gestire i team](using-admin-roles.md). 
  
Gli specialisti del supporto delle comunicazioni gestiscono i problemi di qualità delle chiamate di base. Non analizzano i problemi relativi alle riunioni. Raccolgono invece informazioni correlate e poi escalano in un tecnico del supporto delle comunicazioni. Gli ingegneri del supporto delle comunicazioni visualizzano informazioni in registri di chiamate dettagliati nascosti dagli specialisti del supporto delle comunicazioni. La tabella seguente offre una panoramica delle informazioni disponibili per gli specialisti del supporto delle comunicazioni e per gli ingegneri del supporto delle comunicazioni quando usano le analisi delle chiamate.

|**Attività**|**Informazioni in Call Analytics**|**Cosa vede lo specialista supporto comunicazioni**|**Cosa vede l'ingegnere del supporto comunicazioni**|
|:-----|:-----|:-----|:-----|
|**Chiamate** <br/> |Nome chiamante  <br/> |Solo il nome dell'utente per il quale è stato cercato l'agente.  <br/> |Nome utente.  <br/> |
||Nome destinatario  <br/> |Viene visualizzato come utente interno o utente esterno.  <br/> |Nome destinatario.  <br/> |
||Numero di telefono chiamante  <br/> |L'intero numero di telefono eccetto le ultime tre cifre viene offuscato con simboli asterisco. Ad esempio, 15552823 * * *.  <br/> |L'intero numero di telefono eccetto le ultime tre cifre viene offuscato con simboli asterisco. Ad esempio, 15552823 * * *.  <br/> |
||Numero di telefono del destinatario  <br/> |L'intero numero di telefono eccetto le ultime tre cifre viene offuscato con simboli asterisco. Ad esempio, 15552823 * * *.  <br/> |L'intero numero di telefono eccetto le ultime tre cifre viene offuscato con simboli asterisco. Ad esempio, 15552823 * * *.  <br/> |
||**Scheda Dettagli** > chiamata**avanzata** <br/> |Informazioni non visualizzate.  <br/> |Tutti i dettagli visualizzati, ad esempio i nomi dei dispositivi, l'indirizzo IP, il mapping della subnet e altro ancora.  <br/> |
||**** Scheda debug**avanzata** > **** chiamata >  <br/> |Informazioni non visualizzate.  <br/> |Tutti i dettagli visualizzati, ad esempio suffisso DNS e SSID.  <br/> |
|**Riunioni** <br/> |Nomi dei partecipanti  <br/> |Solo il nome dell'utente per il quale è stato cercato l'agente. Altri partecipanti identificati come utenti interni o utenti esterni.  <br/> |Tutti i nomi visualizzati.  <br/> |
||Conteggio partecipanti  <br/> |Numero di partecipanti.  <br/> |Numero di partecipanti.  <br/> |
||Dettagli della sessione  <br/> |Dettagli della sessione mostrati con eccezioni. Solo il nome dell'utente per il quale è visualizzato l'agente cercato. Altri partecipanti identificati come utenti interni o utenti esterni. Ultime tre cifre del numero di telefono offuscato con simboli asterischi.  <br/> |Dettagli della sessione mostrati. Nomi utente e dettagli della sessione mostrati. Ultime tre cifre del numero di telefono offuscato con simboli asterischi.  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a>Configurare le autorizzazioni assegnando ruoli di amministratore
<a name="BKMK_SetUpTier"> </a>

Per informazioni su come assegnare ruoli amministrativi in Azure Active Directory, vedere [visualizzare e assegnare ruoli in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Caricare un file con estensione TSV o CSV per aggiungere informazioni su edifici, siti e tenant
<a name="BKMK_UploadFiles"> </a>

Puoi aggiungere informazioni su edifici, siti e tenant per chiamare Google Analytics caricando un file CSV o TSV. Con tutte queste informazioni, Call Analytics può eseguire il mapping degli indirizzi IP alle posizioni fisiche. L'utente o gli agenti dell'helpdesk potrebbero trovare queste informazioni utili per facilitare l'individuazione delle tendenze nei problemi di chiamata. Ad esempio, perché molti utenti nello stesso edificio hanno problemi di qualità delle chiamate simili? 

Se si è un amministratore di teams e Skype for business, è possibile usare un file di dati esistente dei team & dashboard di qualità delle chiamate Skype for business. Prima di tutto, è possibile scaricare il file dal dashboard qualità chiamata e quindi caricarlo per chiamare Analytics. 

- Per scaricare un file di dati esistente, passa a **Microsoft teams Admin Center** > **Call Quality dashboard** > **Upload Now**. Nell'elenco **upload personali** fare clic su **Scarica** accanto al file desiderato.

- Per caricare il nuovo file, accedere alle > **posizioni**dell'interfaccia di **amministrazione di Microsoft teams**e quindi selezionare **Carica dati posizione** o **Sostituisci dati posizione**.
  
Se si sta creando il file TSV o CSV da zero, vedere formato di [file di dati tenant e struttura del file di dati dell'edificio](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Argomenti correlati
<a name="BKMK_UploadFiles"> </a>

[Uso dell'analisi delle chiamate per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Analisi delle chiamate e Dashboard Qualità della chiamata](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
