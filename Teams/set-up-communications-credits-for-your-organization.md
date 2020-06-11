---
title: Configurare i Crediti comunicazioni per la propria organizzazione
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: f124cd09c0baa604b09345394d9a53ae254bbb6f
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691242"
---
# <a name="set-up-communications-credits-for-your-organization"></a>Configurare i Crediti comunicazioni per la propria organizzazione

Per usare i numeri verdi con Skype for business e Microsoft teams, sarà necessario configurare i crediti per le comunicazioni. Ti consigliamo inoltre di configurare i crediti per le comunicazioni per i piani di chiamata (nazionali o internazionali) e per gli utenti di servizi di audioconferenza che hanno la possibilità di effettuare chiamate in uscita a **qualsiasi destinazione**. Sono inclusi molti paesi/aree geografiche, ma alcune destinazioni potrebbero non essere incluse negli abbonamenti al piano chiamante o ai servizi di audioconferenza. Se non si configurano i crediti per le comunicazioni e si assegna una licenza per i **crediti di comunicazione** agli utenti e si esauriscono i minuti per l'organizzazione (a seconda del piano di chiamata o del piano di audioconferenza nel proprio paese/area geografica), gli utenti non potranno effettuare chiamate o effettuare la chiamata dalle riunioni di audioconferenza. È possibile ottenere altre informazioni, inclusi gli importi dei finanziamenti consigliati, leggendo [i crediti per le comunicazioni?](what-are-communications-credits.md)
  
> [!NOTE]
> Per scoprire quanto costa, [consulta i prezzi qui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>Passaggio 1: assegnare una licenza per i servizi di audioconferenza o per i piani di chiamata agli utenti

Quando ti iscrivi, Ottieni un certo numero di minuti a seconda del paese/area geografica. È possibile cercare il proprio paese o l'area geografica nell'elenco di disponibilità per i servizi di [audioconferenza e le chiamate in piano](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) per visualizzare il numero di minuti che si otterranno. Dopo aver usato questi minuti, le chiamate verranno disconnesse. Per evitare che ciò accada, è necessario configurare i crediti per le comunicazioni.
  
Per farlo, **occorre assegnare agli utenti una licenza per Audioconferenza o Sistema telefonico**.
  
- Assegnare una licenza per i servizi di **audioconferenza** agli utenti. Vedere [assegnare licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/assign-teams-add-on-licenses.md).
    
    Dopo aver assegnato la licenza, è necessario impostare i servizi di audioconferenza. Per istruzioni dettagliate, vedere [provare o acquistare servizi di audioconferenza in Microsoft 365 o Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).
    
- Assegnare un **sistema telefonico** e una licenza per un piano per chiamate **nazionali o nazionali e internazionali** agli utenti. Vedere [assegnare licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/assign-teams-add-on-licenses.md).
    
    > [!NOTE]
    > Anche se non è necessario per i crediti per le comunicazioni, è comunque necessario assegnare anche un **piano per chiamate nazionali** o una licenza per il **piano di chiamate nazionali e internazionali** .
  
    Dopo aver assegnato queste licenze, sarà necessario ottenere i numeri di telefono per l'organizzazione e quindi assegnare tali numeri alle persone dell'organizzazione. Per istruzioni dettagliate, vedere [configurare i piani](set-up-calling-plans.md)per le chiamate.
    
Per altre informazioni, vedere [licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Passaggio 2: configurare i Crediti comunicazioni per la propria organizzazione

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com/Adminportal) con l'account di lavoro o dell'Istituto di istruzione.
    
2. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365, vedere Servizi di acquisto di **fatturazione**  >  **Purchase Services**. Scorrere verso il basso e selezionare **componenti**aggiuntivi.

3. Selezionare **crediti per comunicazioni**.
    
4. Nella pagina di sottoscrizione **crediti comunicazioni** immettere le informazioni e quindi fare clic su **Avanti**:
    
   - **Aggiungi fondi** Immettere l'importo da aggiungere al proprio account. Se l'opzione di ricarica automatica non è attiva, una volta esauriti i fondi, i Crediti comunicazioni saranno disabilitati (come il servizio per i numeri verdi in entrata). Per evitare di dover ricaricare fondi per i Crediti comunicazioni ogni volta che i fondi disponibili si esauriscono, si consiglia di attivare la funzionalità di autoricarica.
    
   - **Autoricarica** L'autoricarica consente di aggiungere automaticamente fondi al saldo quando scende al di sotto dell'importo configurato.
    
     È consigliabile utilizzare la funzione **Autoricarica** per evitare qualsiasi interruzione del servizio, nel caso in cui i Crediti comunicazioni arrivino a 0 (zero). Verrà inviata un'e-mail al completamento della transazione di ricarica, quando essa non va a buon fine (ad esempio una carta di credito scaduta) e anche quando i Crediti comunicazioni arrivano a 0 (zero).
    
   - **Somma di autoricarica** Nella casella **Ricarica con** indicare l'importo della ricarica da aggiungere automaticamente al proprio account quando il saldo va al di sotto dell'importo configurato.
    
   - **Importo configurato** Specificare l'importo nella casella **Quando il credito scende al di sotto di**, che indicherà quando ' *attivare*  ' l'autoricarica. Quando il credito scende al di sotto di tale importo, l'importo di ricarica specificato verrà aggiunto automaticamente al saldo del tuo account.

      > [!NOTE]
     > I fondi verranno applicati solo ai servizi Crediti comunicazioni alle tariffe Microsoft pubblicate quando i servizi vengono utilizzati. Eventuali fondi non utilizzati entro 12 mesi dalla data di acquisto andranno persi. 
     > 
     > La fatturazione mensile per i crediti di comunicazione verrà applicata solo se è stato usato il fondo assegnato, per informazioni su come controllare l'utilizzo mensile, leggere il [report sull'utilizzo PSTN di Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)
    
5. Immettere le informazioni di pagamento e scegliere **Esecuzione dell'ordine**.
    >[!IMPORTANT]
    >Se si è un cliente di licenze volume, è possibile scegliere il numero di contratto enterprise agreement per il pagamento. Se si dispone di più numeri di enterprise agreement, sarà possibile selezionare il contratto enterprise agreement che si desidera utilizzare per il pagamento. Sarà inoltre possibile specificare un numero d'ordine di acquisto per associare il numero di contratto enterprise agreement (se applicabile).
    
Ogni organizzazione farà un diverso uso dei Piani per chiamate, a seconda del volume e delle tariffe. Sarà necessario chiedere questo tipo di dati di utilizzo al provider di servizi corrente. Le organizzazioni che usano già Skype for business online già come provider di servizi possono ottenere i dati di utilizzo per rivederla nell'interfaccia di **amministrazione di Microsoft teams**segnala i  >  **Reports**  >  **Dettagli sull'utilizzo PSTN** .
  
Quando si configurano i crediti per le comunicazioni, è necessario esaminare l'uso delle chiamate per l'organizzazione per determinare gli importi necessari. Per ottenere informazioni sull'uso delle chiamate, esaminare il report **Dettagli dell'utilizzo della rete PSTN**. Questo report consente di esportare i record di dati delle chiamate in Excel se è necessario archiviare i dati o creare report personalizzati. Per informazioni su come visualizzare l'utilizzo, leggere [report sull'utilizzo PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Passaggio 3: assegnare agli utenti una licenza Crediti comunicazioni

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com/Adminportal) con l'account di lavoro o dell'Istituto di istruzione.
    
2. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365, accedere a utenti attivi degli **utenti**  >  **Active users**e quindi selezionare un utente nell'elenco.
    
3. Scegliere **licenze e app**.
    
4. Attivare o disattivare i **crediti di comunicazione** **su** attivato per assegnare la licenza e quindi selezionare **Salva**.
    
    > [!NOTE]
    > Anche se ad alcuni utenti è assegnata una licenza **Enterprise E5**, è consigliabile comunque procedere in questo modo.

    > [!TIP]
    > Puoi usare [PowerShell](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps) per assegnare licenze e app a più utenti con un solo comando.
  
## <a name="want-to-know-about-plans-and-pricing"></a>Informazioni su piani e prezzi.

Per consultare piani e prezzi, consultare uno di questi link:
  
- [Piani per chiamate](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [Piani per i servizi di audioconferenza](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Piani Sistema telefonico](https://go.microsoft.com/fwlink/?LinkId=799763)
    
Per visualizzare le informazioni, è anche possibile [accedere all'interfaccia di amministrazione di Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e **Billing**  >  **Subscriptions**  >  **aggiungere abbonamenti**agli abbonamenti alla fatturazione.
  
Per visualizzare una tabella con la licenza o le licenze necessarie per ogni funzionalità, vedere licenze per i [componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
## <a name="related-topics"></a>Argomenti correlati

- [Configurare Skype for Business online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [Configurare Cloud Voicemail - Guida per gli amministratori](set-up-phone-system-voicemail.md)
    
- [Configurare piani di chiamata](set-up-calling-plans.md) e [piani di chiamata per Microsoft 365 o Office 365](calling-plans-for-office-365.md)
    
- [Aggiungere fondi e gestire Credito per la comunicazione](add-funds-and-manage-communications-credits.md)
    
  
 
