---
title: "Configurare i Crediti comunicazioni per la propria organizzazione"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
description: "Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. "
---

# Configurare i Crediti comunicazioni per la propria organizzazione

Per usare i numeri verdi in Skype for Business e Microsoft Teams, sono necessari Crediti comunicazioni. Inoltre, è consigliabile impostare i Crediti comunicazioni per i Piani per chiamate (nazionali e internazionali) e Audioconferenza che hanno necessità di effettuare chiamate in uscita verso **qualsiasi destinazione**. Sono inclusi molti paesi/aree geografiche, ma alcune destinazioni PSTN possono non essere incluse in un dato abbonamento Piano per chiamate e Audioconferenza. Se non vengono impostati i Crediti comunicazioni o assegnata una licenza **Crediti comunicazioni** agli utenti e vengono esauriti i minuti per la propria organizzazione (a seconda del Piano per chiamate e Audioconferenza per lo specifico paese/area geografica), quegli utenti non potranno effettuare chiamate o chiamate in uscita dalle riunioni online in audioconferenza. Per altre informazioni, compresi gli importi consigliati, consulta[Cosa sono i Crediti comunicazioni?](what-are-communications-credits.md)
  
> [!NOTE]
> Per scoprire quanto costa, [consulta i prezzi qui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## Passaggio 1: assegnare agli utenti licenze per Piani per chiamate e Audioconferenza

Quando si effettua la registrazione, si ottiene un determinato numero di minuti, a seconda del proprio paese o della propria area geografica. Il numero di minuti disponibili è indicato [Verso dove possono chiamare i miei utenti con Chiamate PSTN?](https://support.office.com/article/9fb78723-05f4-4b86-98e4-fa2a1da3ab5c). Una volta esaurito il numero di minuti, le chiamate verranno disconnesse. Per evitare ciò, impostare i Crediti comunicazioni.
  
Per farlo, **occorre assegnare agli utenti una licenza per Audioconferenza o Sistema telefonico**.
  
- Assegnare una licenza per i servizi di **Audioconferenza** agli utenti. Vedi[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    Dopo aver assegnato la licenza, è necessario impostare i servizi di audioconferenza. Per istruzioni dettagliate, vedi la sezione [Configurare le audioconferenze per Skype for Business e Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md).
    
- Assegnare un licenza ** Sistema telefonico** e un Piano per chiamate nazionali o internazionali agli utenti. Vedi[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Sebbene non sia richiesta per i Crediti comunicazioni, occorre comunque assegnare una licenza per un **Piano per chiamate nazionali** o **Piano per chiamate internazionali**. 
  
    Dopo avere assegnato le licenze, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti. Per istruzioni dettagliate, vedi la sezione [Configurare la chiamata plan di messaggistica unificata](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
Altre informazioni su [Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## Passaggio 2: configurare i Crediti comunicazioni per la propria organizzazione

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Office 365, accedi a **Fatturazione** > **Sottoscrizioni** > **Componenti aggiuntivi** > **Acquista componenti aggiuntivi**, quindi seleziona **Crediti comunicazioni** e fai clic su **Acquista ora**.
    
3. Nella pagina per gli abbonamenti **Crediti comunicazioni**, compilare i dati e fare clic su **Avanti**:
    
  - **Aggiungi fondi** Immettere l'importo da aggiungere al proprio account. Se l'opzione di ricarica automatica non è attiva, una volta esauriti i fondi, i Crediti comunicazioni saranno disabilitati (come il servizio per i numeri verdi in entrata). Per evitare di dover ricaricare fondi per i Crediti comunicazioni ogni volta che i fondi disponibili si esauriscono, si consiglia di attivare la funzionalità di autoricarica.
    
  - **Autoricarica** L'autoricarica consente di aggiungere automaticamente fondi al saldo quando scende al di sotto dell'importo configurato.
    
    È consigliabile utilizzare la funzione **Autoricarica** per evitare qualsiasi interruzione del servizio, nel caso in cui i Crediti comunicazioni arrivino a 0 (zero). Verrà inviata un'e-mail al completamento della transazione di ricarica, quando essa non va a buon fine (ad esempio una carta di credito scaduta) e anche quando i Crediti comunicazioni arrivano a 0 (zero).
    
  - **Somma di autoricarica** Nella casella **Ricarica con** indicare l'importo della ricarica da aggiungere automaticamente al proprio account quando il saldo va al di sotto dell'importo configurato.
    
  - **Importo configurato** Specificare l'importo nella casella **Quando il credito scende al di sotto di**, che indicherà quando ' *attivare*  ' l'autoricarica. Quando il credito scende al di sotto di tale importo, l'importo di ricarica specificato verrà aggiunto automaticamente al saldo del tuo account.
    
4. Immettere le informazioni di pagamento e scegliere **Esecuzione dell'ordine**.
    
    > [!NOTE]
    > I fondi verranno applicati solo ai servizi Crediti comunicazioni alle tariffe Microsoft pubblicate quando i servizi vengono utilizzati. Eventuali fondi non utilizzati entro 12 mesi dalla data di acquisto andranno persi. 
  
Ogni organizzazione farà un diverso uso dei Piani per chiamate, a seconda del volume e delle tariffe. Sarà necessario chiedere questo tipo di dati di utilizzo al provider di servizi corrente. Per queste organizzazioni, che usano già Skype for Business online come provider di servizi, è possibile ottenere i dati di utilizzo esaminandoli in **Interfaccia di amministrazione di Skype for Business** > **Report** > **Dettagli dell'utilizzo della rete PSTN**.
  
Quando si impostano i Crediti comunicazioni è necessario analizzare l'uso delle chiamate nella propria organizzazione per determinare gli importi da considerare. Per ottenere informazioni sull'uso delle chiamate, esaminare il report **Dettagli dell'utilizzo della rete PSTN**. Questo report permette di esportare i record dei dati di chiamata su Excel, per scopi di archiviazione o per creare report personalizzati. Per consultare i dati sull'utilizzo, vedere [Report di utilizzo PSTN di Skype for Business](../skype-for-business-online-reporting/skype-for-business-pstn-usage-report.md)
  
## Passaggio 3: assegnare agli utenti una licenza Crediti comunicazioni

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Office 365 accedi a **Utenti** > **Utenti attivi** > e quindi seleziona uno o più utenti dall'elenco.
    
3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.
    
4. Nella pagina **Licenze prodotto**, imposta **Crediti comunicazioni** su **Attivo** per assegnare questa licenza e fai clic su **Salva**.
    
    > [!NOTE]
    > Anche se ad alcuni utenti è assegnata una licenza **Enterprise E5**, è consigliabile comunque procedere in questo modo.
  
## Informazioni su piani e prezzi.

Per consultare piani e prezzi, consultare uno di questi link:
  
- [Piani per chiamate](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [ Piani per le audioconferenze](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Piani Sistema telefonico](https://go.microsoft.com/fwlink/?LinkId=799763)
    
È possibile consultare le informazioni anche [accedendo all'interfaccia di amministrazione di Office 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e andando su **Fatturazione** > **Sottoscrizioni** > **Aggiungi sottoscrizioni**.
  
Per consultare una tabella con la licenza o le licenze necessarie per ciascuna funzione, vedere [Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](skype-for-business-and-microsoft-teams-add-on-licensing.md).
  

