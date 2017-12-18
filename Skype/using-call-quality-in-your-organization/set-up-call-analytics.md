---
title: "Configurazione di Skype for Business Call Analytics"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
description: "Set up and use Call Analytics to identify and troubleshoot Skype for Business and Microsoft Teams call quality problems."
---

# Configurazione di Skype for Business Call Analytics

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Gli amministratori Skype for Business online è possibile utilizzare chiamare Analitica di problemi Skype for Business e Microsoft Teams chiamata qualità e connessione. Può risultare utile per configurare le funzionalità seguenti in Analitica chiamata:
  
- Impostazione di autorizzazioni che permettono ad altro personale, come gli agenti helpdesk, di usare Call Analytics ma impediscono loro di accedere al resto dell'interfaccia di amministrazione di Skype for Business. 
    
- Aggiunta di informazioni a livello di edificio, sito e tenant a Call Analytics con l'invio di un file di dati .tsv o .csv.
    
> [!NOTE]
> Call Analytics è attualmente in fase di anteprima. Il testo e le immagini qui riportati possono non corrispondere alla tua esperienza di utilizzo. 
  
## Impostazione delle autorizzazioni di Call Analytics
<a name="BKMK_SetCAPerms"> </a>

Come amministratore, avrai accesso completo a tutte le funzioni di Call Analytics. Inoltre, potrai usare un modello di helpdesk in Call Analytics che include gruppi di autorizzazioni di Livello 1 e Livello 2. Gli utenti con autorizzazioni di Livello 1 possono accedere solo a una porzione limitata di Call Analytics. Gli utenti con autorizzazioni di Livello 2 possono accedere a tutte le funzionalità di Call Analytics. Nessuno dei due livelli di autorizzazione consente l'accesso al resto dell'interfaccia di amministrazione di Skype for Business. Potrai dare accesso ai due livelli aggiungendo un gruppo che contenga l'utente alla sezione Livello 1 o Livello 2 della pagina Autorizzazioni. Per i dettagli, consulta [Configurazione delle autorizzazioni a più livelli in Call Analytics](fbf7247a-84ae-46cc-9204-2c45b1c734cd.md#BKMK_SetUpTier).
  
Gli agenti di helpdesk di Livello 1 gestiscono i problemi di base sulla qualità delle chiamate. Gli agenti di Livello 1 non esaminano i problemi relativi alle riunioni, ma raccolgono le informazioni correlate e poi inoltrano il problema a un agente di Livello 2. Gli agenti di Livello 2 possono consultare informazioni in registri chiamate dettagliati non accessibili agli agenti di Livello 1. La tabella seguente offre una panoramica delle informazioni disponibili agli agenti che utilizzano Call Analytics.
  
|
|
|**Attività**|**Informazioni in Call Analytics**|**Cosa vede l'agente di Livello 1**|**Cosa vede l'agente di Livello 2**|
|:-----|:-----|:-----|:-----|
|**Chiamate** <br/> |Nome del chiamante  <br/> |Solo il nome dell'utente cercato dall'agente.  <br/> |Nome utente.  <br/> |
||Nome del destinatario  <br/> |Mostrato come Utente interno o Utente esterno.  <br/> |Nome del destinatario.  <br/> |
||Numero di telefono del chiamante  <br/> |Numero di telefono completo eccetto le ultime tre cifre, mascherate con asterischi. Per esempio: 15552823***.  <br/> |Numero di telefono completo eccetto le ultime tre cifre, mascherate con asterischi. Per esempio: 15552823***.  <br/> |
||Numero di telefono del destinatario  <br/> |Numero di telefono completo eccetto le ultime tre cifre, mascherate con asterischi. Per esempio: 15552823***.  <br/> |Numero di telefono completo eccetto le ultime tre cifre, mascherate con asterischi. Per esempio: 15552823***.  <br/> |
||Scheda **Dettagli chiamata** > **Avanzati** <br/> |Le informazioni non sono mostrate.  <br/> |Vengono mostrati tutti i dettagli, ad esempio nome di dispositivo, indirizzo IP, mappatura della subnet e altro ancora.  <br/> |
||Scheda **Dettagli chiamata** > **Avanzati** > **Debug** <br/> |Le informazioni non sono mostrate.  <br/> |Vengono mostrati tutti i dettagli, ad esempio suffisso DNS e SSID.  <br/> |
|**Riunioni** <br/> |Nomi dei partecipanti  <br/> |Solo il nome dell'utente cercato dall'agente. Tutti gli altri partecipanti identificati come Utente interno o Utente esterno.  <br/> |Vengono mostrati tutti i nomi.  <br/> |
||Numero di partecipanti  <br/> |Numero di partecipanti.  <br/> |Numero di partecipanti.  <br/> |
||Dettagli della sessione  <br/> |Vengono mostrati i dettagli della sessione, con alcune eccezioni. Viene mostrato solo il nome dell'utente cercato dall'agente. Tutti gli altri partecipanti identificati come Utente interno o Utente esterno. Le ultime tre cifre del numero di telefono sono mascherate con asterischi.  <br/> |Vengono mostrati i dettagli della sessione. Vengono mostrati i nomi degli utenti e i dettagli della sessione. Le ultime tre cifre del numero di telefono sono mascherate con asterischi.  <br/> |
   
 **Configurazione delle autorizzazioni a più livelli in Call Analytics**
  
1. Crea gruppi di sicurezza di Office 365 per il Livello 1 e il Livello 2, e aggiungi a ciascun gruppo gli utenti che desideri. Puoi anche riutilizzare gruppi di sicurezza esistenti. Per maggiori informazioni, consulta [Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).
    
2. Nell'Interfaccia di amministrazione di Office 365, accedi a **Interfacce di amministrazione** > **Skype for Business**.
    
    > [!NOTE]
    > Se questo ti porta alla vecchia interfaccia di amministrazione di Skype for Business, fai clic su **Prova la nuova interfaccia di amministrazione** per accedere alla nuova versione.
  
3. Nella nuova interfaccia di amministrazione di Skype for Business, fai clic su **Autorizzazioni**.
    
4. Aggiungi i gruppi di sicurezza di Office 365 alle caselle **Livello 1** e **Livello 2**. Puoi aggiungere più gruppi allo stesso ruolo.
    
     ![Screenshot shows the Permissions for Call Analytics page with the options for Tier 1 and Tier 2 permissions.](../images/ed5b6b05-b407-4363-8cf0-a6e79027f64b.png)
  
 Gli utenti con uno di questi livelli di autorizzazione possono accedere a Call Analytics tramite l'URL dedicato https://adminportal.services.skypeforbusiness.com.
  
## Invio di un file di dati .tsv o .csv per aggiungere informazioni a livello di edificio, sito e tenant
<a name="BKMK_UploadFiles"> </a>

Puoi aggiungere informazioni a livello di edificio, sito e tenant a Call Analytics inviando un file .tsv o .csv. Con tutte queste informazioni, Call Analytics può mappare gli indirizzi IP alle posizioni fisiche. Queste informazioni possono essere utili a te o agli agenti helpdesk per individuare tendenze nei problemi di chiamata. Ad esempio: perché tanti utenti nello stesso edificio hanno problemi simili di qualità delle chiamate? 
  
![Screenshot shows the Sites page with values for Number of sites and Number of subnets, and the Select file button to import site data by uploading a .tsv or a .csv file.](../images/b2f3a5cb-32b5-4f60-a9af-0691aa6ff1e8.png)
  
Se sei un amministratore di Skype for Business, puoi usare un file dati esistente da Call Quality Dashboard di Skype for Business online. Per prima cosa, scarica il file da Call Quality Dashboard, poi invialo a Call Analytics. Per scaricare un file di dati esistente, accedi all' **interfaccia di amministrazione Skype for Business** > **Strumenti** > **Call Quality Dashboard di Skype for Business Online** > **Carica ora**. Nell'elenco **caricamenti**, fai clic su **Scarica** accanto al file che desideri.
  
Se stai creando il file .tsv o .csv da zero, consulta [Formato del file di dati tenant e struttura del file di dati di tipo Building](turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-bu.md#BKMK_TenantDataFile).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  
## Vedere anche
<a name="MT_Footer"> </a>

#### 

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate in Skype for Business](use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality.md)
  
[Qual è la differenza tra Call Analytics e Call Quality Dashboard?](what-s-the-difference-between-call-analytics-and-call-quality-dashboard.md)

