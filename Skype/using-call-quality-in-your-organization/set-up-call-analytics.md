---
title: Configurazione di Skype per Business chiamare Analitica
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Configurare e utilizzare chiamate Analitica per identificare e risolvere i problemi Skype per problemi di qualità chiamata Business e Teams Microsoft."
ms.openlocfilehash: 287b45cf8363c03bf6b62cd68f8e2be681996101
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-skype-for-business-call-analytics"></a>Configurazione di Skype per Business chiamare Analitica

Skype per amministrazione Business Online, è possibile utilizzare chiamate Analitica per risolvere i problemi Skype per le aziende e Microsoft Teams problemi di qualità e connessione delle chiamate. Può essere utile per configurare le seguenti funzionalità di chiamata Analitica:
  
- Impostare le autorizzazioni che consentono di altri membri del personale, ad esempio gli agenti help desk, utilizzare chiamate Analitica ma impedire loro l'accesso al contenuto del Skype per interfaccia di amministrazione di Business. 
    
- Aggiungere edificio, siti e le informazioni di tenant per chiamare Analitica caricando un file di dati tsv o csv.
    
> [!NOTE]
> Call Analytics è attualmente in fase di anteprima. Il testo e le immagini qui riportati possono non corrispondere alla tua esperienza di utilizzo. 
  
## <a name="set-call-analytics-permissions"></a>Impostare le autorizzazioni di chiamata Analitica
<a name="BKMK_SetCAPerms"></a>

Come l'amministratore è ottenere accesso completo a tutte le funzionalità di chiamata Analitica. Inoltre, è possibile utilizzare un modello di supporto tecnico di Analitica chiamata che include i gruppi di autorizzazione di livello 1 e 2 a livelli. Gli utenti con autorizzazioni di livello 1 possono accedere solo una vista limitata delle chiamate Analitica. Gli utenti che dispongono delle autorizzazioni di livello 2 possono accedere a tutte le funzionalità di chiamata Analitica. Entrambe livelli di autorizzazione impediscono l'accesso per il resto del Skype per interfaccia di amministrazione di Business. È possibile concedere l'accesso ai livelli mediante l'aggiunta di un gruppo contenente all'utente di livello 1 o la sezione di livello 2 della pagina autorizzazioni. Per ulteriori informazioni, vedere [impostare le autorizzazioni a più livelli nel chiamare Analitica](set-up-call-analytics.md#BKMK_SetUpTier).
  
Problemi di qualità delle chiamate di base di gestire gli agenti di supporto tecnico di livello 1. Gli agenti di livello 1 non analizzare i problemi relativi alle riunioni; hanno raccogliere informazioni correlate e quindi passare a un agente di livello 2. Gli agenti di livello 2 visualizzare le informazioni in registri chiamate dettagliate sono nascosta dagli agenti di livello 1. Nella tabella seguente viene fornita una panoramica delle informazioni disponibili per gli agenti mediante chiamata Analitica.


|**Attività**|**Informazioni di chiamata Analitica**|**Ciò che vede l'agente di livello 1**|**Ciò che vede l'agente di livello 2**|
|:-----|:-----|:-----|:-----|
|**Chiamate** <br/> |Nome del chiamante  <br/> |Solo il nome dell'utente per il quale l'agente di una ricerca.  <br/> |Nome dell'utente.  <br/> |
||Nome del destinatario  <br/> |Viene illustrato come utente interno o degli utenti esterni.  <br/> |Nome del destinatario.  <br/> |
||Numero di telefono chiamante  <br/> |Numero intero, ad eccezione delle ultime tre cifre vengono offuscate con simboli asterisco. Ad esempio, 15552823 * * *.  <br/> |Numero intero, ad eccezione delle ultime tre cifre vengono offuscate con simboli asterisco. Ad esempio, 15552823 * * *.  <br/> |
||Numero di telefono del destinatario  <br/> |Numero intero, ad eccezione delle ultime tre cifre vengono offuscate con simboli asterisco. Ad esempio, 15552823 * * *.  <br/> |Numero intero, ad eccezione delle ultime tre cifre vengono offuscate con simboli asterisco. Ad esempio, 15552823 * * *.  <br/> |
||**Dettagli chiamata** > scheda**Avanzate** <br/> |Informazioni non visualizzate.  <br/> |Tutti i dettagli indicati, ad esempio i nomi dei dispositivi, indirizzo IP, mapping subnet e altro ancora.  <br/> |
||**Dettagli chiamata** > **Avanzate** > scheda**Debug** <br/> |Informazioni non visualizzate.  <br/> |Tutti i dettagli indicati, ad esempio il suffisso DNS e SSID.  <br/> |
|**Riunioni** <br/> |Nomi dei partecipanti  <br/> |Solo il nome dell'utente per il quale l'agente di una ricerca. Gli altri partecipanti identificati come utente interno o degli utenti esterni.  <br/> |Tutti i nomi visualizzati.  <br/> |
||Numero partecipanti  <br/> |Numero di partecipanti.  <br/> |Numero di partecipanti.  <br/> |
||Dettagli sessione  <br/> |Dettagli visualizzati con le eccezioni. Viene visualizzato solo il nome dell'utente per il quale l'agente di una ricerca. Gli altri partecipanti identificati come utente interno o degli utenti esterni. Ultimi tre cifre del numero di telefono offuscati con simboli asterisco.  <br/> |Dettagli riportati. I nomi utente e i dettagli di sessione riportati. Ultimi tre cifre del numero di telefono offuscati con simboli asterisco.  <br/> |
   
 **Impostare le autorizzazioni a più livelli nel chiamare Analitica** 
 <a name="BKMK_SetUpTier"> </a>
  
1. Creare gruppi di protezione di Office 365 per livello 1 e 2 a livelli e aggiungere le persone che si desidera che a ogni gruppo. È inoltre possibile riutilizzare i gruppi di protezione esistente. Per ulteriori informazioni, vedere [creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).
    
2. Nell'interfaccia di amministrazione di Office 365 andare a **Admin Center** > **Skype per le aziende**.
    
    > [!NOTE]
    > Se inserita nella precedente Skype per interfaccia di amministrazione di Business, passare alla nuova versione facendo clic sul pulsante **implementati provare la nuova interfaccia di amministrazione**. 
  
3. In nuovo Skype per interfaccia di amministrazione di Business, fare clic su **autorizzazioni**.
    
4. Aggiungere i gruppi di protezione di Office 365 per le caselle di **livello 1** e **2 a livelli** . È possibile aggiungere più gruppi a ogni ruolo.
    
     ![Schermata che mostra la pagina autorizzazioni per chiamare Analitica con le opzioni per le autorizzazioni di livello 1 e 2 a livelli.](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 Gli utenti con uno di questi livelli di autorizzazione visualizzare chiamare Analitica tramite dedicato URL *https://adminportal.services.skypeforbusiness.com*.
  
## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Caricare un file CSV o TSV per aggiungere creazione, del sito e titolari delle informazioni
<a name="BKMK_UploadFiles"> </a>

È possibile aggiungere edificio, siti e le informazioni di tenant per chiamare Analitica caricando un file CSV o tsv. Con queste informazioni, chiamare Analitica possibile mappare gli indirizzi IP a posizioni fisiche. Si o dell'help desk agenti potrebbero risultare queste informazioni utili per individuare tendenze in problemi di chiamata. Ad esempio perché sono simili a quelle molti utenti nello stesso edificio con chiamata problemi di qualità? 
  
![Schermata che mostra la pagina siti con i valori per numero di siti e il numero di subnet e il pulsante selezionare il file per caricamento un tsv o un file CSV per importare i dati del sito.](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Se si è Skype per amministratore aziendale, è possibile utilizzare un file di dati dal Skype per Business Online i Dashboard qualità delle chiamate. Innanzitutto scaricare il file dal Dashboard di qualità delle chiamate e quindi caricarlo nel chiamare Analitica. Per scaricare un file di dati, passare a **Skype per Business Admin center** > **Strumenti** > **Skype per chiamare Online Business per i Dashboard qualità** > **caricare ora**. Nell'elenco **il caricamento** , fare clic su **Download** accanto al file desiderato.
  
Se si sta creando il file con estensione csv o TSV da zero, vedere [file di dati Tenant formato e la struttura dei file dei dati predefinito](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile).
  
## <a name="related-topics"></a>Argomenti correlati
<a name="BKMK_UploadFiles"> </a>

[Utilizzo delle chiamate Analitica per la risoluzione dei Skype insufficiente per le aziende qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Che cos'è la differenza tra Analitica delle chiamate e chiamate Dashboard qualità?](difference-between-call-analytics-and-call-quality-dashboard.md)