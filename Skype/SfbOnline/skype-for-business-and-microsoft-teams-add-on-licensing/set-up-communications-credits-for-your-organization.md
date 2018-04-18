---
title: Configurare i Crediti comunicazioni per la propria organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: ce0503eea868e7fd4c2cef3afeb5394ad034b1c2
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-communications-credits-for-your-organization"></a>Configurare i Crediti comunicazioni per la propria organizzazione

[] Per usare i numeri verdi in Skype for Business e Microsoft Teams, sono necessari Crediti comunicazioni. Inoltre, è consigliabile impostare i Crediti comunicazioni per i Piani per chiamate (nazionali e internazionali) e Audioconferenza che hanno necessità di effettuare chiamate in uscita verso **qualsiasi destinazione**. Sono inclusi molti paesi/aree geografiche, ma alcune destinazioni PSTN possono non essere incluse in un dato abbonamento Piano per chiamate e Audioconferenza. Se non vengono impostati i Crediti comunicazioni o assegnata una licenza **Crediti comunicazioni** agli utenti e vengono esauriti i minuti per la propria organizzazione (a seconda del Piano per chiamate e Audioconferenza per lo specifico paese/area geografica), quegli utenti non potranno effettuare chiamate o chiamate in uscita dalle riunioni online in audioconferenza. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)
  
> [!NOTE]
> Per scoprire quanto costa, [consulta i prezzi qui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a>Passaggio 1: assegnare agli utenti licenze per Piani per chiamate e Audioconferenza

Quando si effettua la registrazione, si ottiene un determinato numero di minuti, a seconda del proprio paese o della propria area geografica. You can see the number of minutes you will get search for the country or region [here].(../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)). Una volta esaurito il numero di minuti, le chiamate verranno disconnesse. Per evitare ciò, impostare i Crediti comunicazioni.
  
Per farlo, **occorre assegnare agli utenti una licenza per Audioconferenza o Sistema telefonico**.
  
- Assegnare una licenza per i servizi di **Audioconferenza** agli utenti. Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    Dopo aver assegnato la licenza, è necessario impostare i servizi di audioconferenza. For step-by-step instructions, see [Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md).
    
- Assign **Phone System** and a domestic or domestic and international Calling Plan license to your users. Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or an **Domestic and International Calling Plan** license.
  
    Dopo avere assegnato le licenze, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti. For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
For more information, see [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Passaggio 2: configurare i Crediti comunicazioni per la propria organizzazione

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add-ons** > **Buy add-ons**, and then choose **Communications Credits** > **Buy now**.
    
3. On the **Communications Credits** subscription page, fill in your information, and then click **Next**:
    
  - **Aggiungi fondi** Immettere l'importo da aggiungere al proprio account. Se l'opzione di ricarica automatica non è attiva, una volta esauriti i fondi, i Crediti comunicazioni saranno disabilitati (come il servizio per i numeri verdi in entrata). Per evitare di dover ricaricare fondi per i Crediti comunicazioni ogni volta che i fondi disponibili si esauriscono, si consiglia di attivare la funzionalità di autoricarica.
    
  - **Autoricarica** L'autoricarica consente di aggiungere automaticamente fondi al saldo quando scende al di sotto dell'importo configurato.
    
    È consigliabile utilizzare la funzione **Autoricarica** per evitare qualsiasi interruzione del servizio, nel caso in cui i Crediti comunicazioni arrivino a 0 (zero). Verrà inviata un'e-mail al completamento della transazione di ricarica, quando essa non va a buon fine (ad esempio una carta di credito scaduta) e anche quando i Crediti comunicazioni arrivano a 0 (zero).
    
  - **Somma di autoricarica** Nella casella **Ricarica con** indicare l'importo della ricarica da aggiungere automaticamente al proprio account quando il saldo va al di sotto dell'importo configurato.
    
  - **Importo configurato** Specificare l'importo nella casella **Quando il credito scende al di sotto di**, che indicherà quando ' *attivare*  ' l'autoricarica. Quando il credito scende al di sotto di tale importo, l'importo di ricarica specificato verrà aggiunto automaticamente al saldo del tuo account.

      > [!NOTE]
    > I fondi verranno applicati solo ai servizi Crediti comunicazioni alle tariffe Microsoft pubblicate quando i servizi vengono utilizzati. Eventuali fondi non utilizzati entro 12 mesi dalla data di acquisto andranno persi. 
    
4. Immettere le informazioni di pagamento e scegliere **Esecuzione dell'ordine**.
    >[!IMPORTANT]
    >If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).
    
Ogni organizzazione farà un diverso uso dei Piani per chiamate, a seconda del volume e delle tariffe. Sarà necessario chiedere questo tipo di dati di utilizzo al provider di servizi corrente. Per queste organizzazioni, che usano già Skype for Business online come provider di servizi, è possibile ottenere i dati di utilizzo esaminandoli in **Interfaccia di amministrazione di Skype for Business** > **Report** > **Dettagli dell'utilizzo della rete PSTN**.
  
Quando si impostano i Crediti comunicazioni è necessario analizzare l'uso delle chiamate nella propria organizzazione per determinare gli importi da considerare. Per ottenere informazioni sull'uso delle chiamate, esaminare il report **Dettagli dell'utilizzo della rete PSTN**. Questo report permette di esportare i record dei dati di chiamata su Excel, per scopi di archiviazione o per creare report personalizzati. To see usage, see [Skype for Business PSTN usage report](../skype-for-business-online-reporting/pstn-usage-report.md)
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Passaggio 3: assegnare agli utenti una licenza Crediti comunicazioni

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Office 365 accedi a **Utenti** > **Utenti attivi** > e quindi seleziona uno o più utenti dall'elenco.
    
3. Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.
    
4. On the **Product licenses** page, toggle ** Communications Credits** to **On** to assign this license, and then click **Save**.
    
    > [!NOTE]
    > Anche se ad alcuni utenti è assegnata una licenza **Enterprise E5**, è consigliabile comunque procedere in questo modo.
  
## <a name="want-to-know-about-plans-and-pricing"></a>Informazioni su piani e prezzi.

Per consultare piani e prezzi, consultare uno di questi link:
  
- [Piani per chiamate](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [Audio Conferencing Plans](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Piani Sistema telefonico](https://go.microsoft.com/fwlink/?LinkId=799763)
    
È possibile consultare le informazioni anche [accedendo all'interfaccia di amministrazione di Office 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e andando su **Fatturazione** > **Sottoscrizioni** > **Aggiungi sottoscrizioni**.
  
To see a table with the license or licenses you will need for each feature, see [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="related-topics"></a>See also

- [Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [Impostare la segreteria telefonica del Sistema telefonico - Guida per gli amministratori](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md)
    
- [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)
    
- [Aggiungere fondi e gestire Crediti comunicazioni](add-funds-and-manage-communications-credits.md)
    
- [Configure the Cloud Connector](https://technet.microsoft.com/en-us/library/mt605228.aspx) and [Download the Cloud Connector](https://aka.ms/CloudConnectorInstaller)

  
 