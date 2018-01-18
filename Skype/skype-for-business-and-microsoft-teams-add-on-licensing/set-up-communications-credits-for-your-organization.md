---
title: Configurare i Crediti comunicazioni per la propria organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 62d8516a2efb7f3a48e301492e602ec957927f37
ms.sourcegitcommit: 35cbf92f5cf295c82d67e9c093e3cea7c5c012eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/04/2018
---
# <a name="set-up-communications-credits-for-your-organization"></a>Configurare i Crediti comunicazioni per la propria organizzazione

È necessario configurare Communications crediti se si desidera utilizzare numeri verdi con Skype per le aziende e Teams Microsoft. Inoltre, è consigliabile impostare backup crediti Communications per la chiamata a piani (nazionali o internazionali) e conferenze Audio utenti hanno bisogno la possibilità di effettuare chiamate in uscita a **qualsiasi destinazione**. Sono incluse numerose paesi, ma alcune destinazioni non possono essere inclusi in sottoscrizioni pianificare la chiamata o di conferenza Audio. Se non configurare Communications titoli di coda di fatturazione e assegna una licenza **Crediti Communications** per gli utenti e si esegue fuori minuti per l'organizzazione (a seconda del piano di chiamata o conferenze Audio piano nel paese/area geografica), gli utenti non sarà in grado di effettuare chiamate o effettuare chiamate in uscita dalle riunioni di conferenze Audio. È possibile ottenere ulteriori informazioni, tra cui consigliato fondi importi, leggendo [che cosa sono i titoli di coda Communications?](what-are-communications-credits.md)
  
> [!NOTE]
> Per scoprire quanto costa, [consulta i prezzi qui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a>Passaggio 1: assegnare agli utenti licenze per Piani per chiamate e Audioconferenza

Quando iscrizione, si ottiene un certo numero di minuti in base al proprio paese. È possibile visualizzare il numero di minuti che si otterrà una ricerca per il paese o regione [qui]. (.. / country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)). Dopo aver utilizzato i minuti, le chiamate vengono disconnesse. Per evitare ciò, è necessario impostare i titoli di coda di comunicazioni.
  
Per farlo, **occorre assegnare agli utenti una licenza per Audioconferenza o Sistema telefonico**.
  
- Assegnare una licenza di **Conferenze Audio** per gli utenti. Vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    Dopo aver assegnato la licenza, è necessario impostare i servizi di audioconferenza. Per istruzioni dettagliate, vedi la sezione [Configurare le audioconferenze per Skype for Business e Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing.md).
    
- Assegnare agli utenti **Sistema telefonico** e una licenza di chiamata pianificare interno o nazionale e internazionale. Vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Anche se non è necessario per crediti Communications, è necessario anche assegnare un **Interno pianificare la chiamata** o una licenza **nazionali e internazionali chiamata pianificare** .
  
    Dopo aver assegnato questi licenze, è necessario ottenere i numeri di telefono per l'organizzazione e quindi assegna tali numeri per le persone all'interno dell'organizzazione. Per istruzioni dettagliate, vedere [impostare le tariffe di chiamate](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
Per ulteriori informazioni, vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Passaggio 2: configurare i Crediti comunicazioni per la propria organizzazione

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Office 365, passare alla **fatturazione** > **sottoscrizioni** > **i componenti aggiuntivi** > **acquistare componenti aggiuntivi**e quindi fare clic su **Communications crediti** > **Acquista**.
    
3. Nella pagina sottoscrizione **Crediti Communications** , immettere le informazioni e quindi fare clic su **Avanti**:
    
  - **Aggiungi fondi** Immettere l'importo da aggiungere al proprio account. Se l'opzione di ricarica automatica non è attiva, una volta esauriti i fondi, i Crediti comunicazioni saranno disabilitati (come il servizio per i numeri verdi in entrata). Per evitare di dover ricaricare fondi per i Crediti comunicazioni ogni volta che i fondi disponibili si esauriscono, si consiglia di attivare la funzionalità di autoricarica.
    
  - **Autoricarica** L'autoricarica consente di aggiungere automaticamente fondi al saldo quando scende al di sotto dell'importo configurato.
    
    È consigliabile utilizzare la funzione **Autoricarica** per evitare qualsiasi interruzione del servizio, nel caso in cui i Crediti comunicazioni arrivino a 0 (zero). Verrà inviata un'e-mail al completamento della transazione di ricarica, quando essa non va a buon fine (ad esempio una carta di credito scaduta) e anche quando i Crediti comunicazioni arrivano a 0 (zero).
    
  - **Somma di autoricarica** Nella casella **Ricarica con** indicare l'importo della ricarica da aggiungere automaticamente al proprio account quando il saldo va al di sotto dell'importo configurato.
    
  - **Importo configurato** Specificare l'importo nella casella **Quando il credito scende al di sotto di**, che indicherà quando ' *attivare*  ' l'autoricarica. Quando il credito scende al di sotto di tale importo, l'importo di ricarica specificato verrà aggiunto automaticamente al saldo del tuo account.

      > [!NOTE]
    > I fondi verranno applicati solo ai servizi Crediti comunicazioni alle tariffe Microsoft pubblicate quando i servizi vengono utilizzati. Eventuali fondi non utilizzati entro 12 mesi dalla data di acquisto andranno persi. 
    
4. Immettere le informazioni di pagamento e scegliere **Esecuzione dell'ordine**.
    >[!IMPORTANT]
    >Se si è un cliente di licenze volume, è possibile scegliere il numero di contratto enterprise per il pagamento. Se si dispone di più numeri di enterprise agreement, sarà possibile selezionare il contratto enterprise agreement si desidera utilizzare per il pagamento. Sarà inoltre possibile consente di specificare un numero di ordine di acquisto per associare il numero di contratto enterprise (se applicabile).
    
Ogni organizzazione farà un diverso uso dei Piani per chiamate, a seconda del volume e delle tariffe. Sarà necessario chiedere questo tipo di dati di utilizzo al provider di servizi corrente. Per queste organizzazioni, che usano già Skype for Business online come provider di servizi, è possibile ottenere i dati di utilizzo esaminandoli in **Interfaccia di amministrazione di Skype for Business** > **Report** > **Dettagli dell'utilizzo della rete PSTN**.
  
Durante l'impostazione dei titoli di coda di comunicazioni, è necessario analizzare l'utilizzo di chiamata per l'organizzazione determinare gli importi che è necessario inserire in. È possibile ottenere informazioni sull'utilizzo di chiamata dall'esame del rapporto **dettagli sull'utilizzo PSTN** . In questo report consente di esportare i record di dati di chiamata in Excel se si desidera esportare i dati per l'archiviazione o creare report personalizzati. Per visualizzare dati di utilizzo, vedere [Skype per i report di utilizzo PSTN Business](../skype-for-business-online-reporting/pstn-usage-report.md)
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Passaggio 3: assegnare agli utenti una licenza Crediti comunicazioni

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Office 365 accedi a **Utenti** > **Utenti attivi** > e quindi seleziona uno o più utenti dall'elenco.
    
3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.
    
4. Nella pagina **licenze per i prodotti** , attivare e disattivare * * Communications crediti * * di **su** per assegnare la licenza e quindi fare clic su **Salva**.
    
    > [!NOTE]
    > Anche se ad alcuni utenti è assegnata una licenza **Enterprise E5**, è consigliabile comunque procedere in questo modo.
  
## <a name="want-to-know-about-plans-and-pricing"></a>Informazioni su piani e prezzi.

Per consultare piani e prezzi, consultare uno di questi link:
  
- [Piani per chiamate](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [Piani di audioconferenze con accesso esterno](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Piani Sistema telefonico](https://go.microsoft.com/fwlink/?LinkId=799763)
    
È possibile consultare le informazioni anche [accedendo all'interfaccia di amministrazione di Office 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e andando su **Fatturazione** > **Sottoscrizioni** > **Aggiungi sottoscrizioni**.
  
Per una tabella con la licenza o licenze che necessarie per ogni caratteristica, vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="related-topics"></a>Argomenti correlati

- [Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [Configurare le audioconferenze per Skype for Business e Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
    
- [Impostare la segreteria telefonica del Sistema telefonico - Guida per gli amministratori](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md)
    
- [Impostare le tariffe di chiamate](../what-are-calling-plans-in-office-365/set-up-calling-plans.md) e [La chiamata a piani per Office 365](calling-plans-for-office-365.md)
    
- [Aggiungere i fondi e gestire Communications titoli di coda](add-funds-and-manage-communications-credits.md)
    
- [Configurare il connettore Cloud](https://technet.microsoft.com/en-us/library/mt605228.aspx) e [scaricare il connettore Cloud](https://aka.ms/CloudConnectorInstaller)
