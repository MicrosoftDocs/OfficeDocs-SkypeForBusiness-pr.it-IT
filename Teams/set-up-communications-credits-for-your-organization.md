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
- m365initiative-voice
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
ms.openlocfilehash: 98591d7603cdf63a76bef3478834f37504d8ff6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117104"
---
# <a name="set-up-communications-credits-for-your-organization"></a>Configurare i Crediti comunicazioni per la propria organizzazione

[] Per usare i numeri verdi in Skype for Business e Microsoft Teams, sono necessari Crediti comunicazioni. Inoltre, è consigliabile impostare i Crediti comunicazioni per i Piani per chiamate (nazionali e internazionali) e Audioconferenza che hanno necessità di effettuare chiamate in uscita verso **qualsiasi destinazione**. Sono inclusi molti paesi/aree geografiche, ma alcune destinazioni PSTN possono non essere incluse in un dato abbonamento Piano per chiamate e Audioconferenza. Se non vengono impostati i Crediti comunicazioni o assegnata una licenza **Crediti comunicazioni** agli utenti e vengono esauriti i minuti per la propria organizzazione (a seconda del Piano per chiamate e Audioconferenza per lo specifico paese/area geografica), quegli utenti non potranno effettuare chiamate o chiamate in uscita dalle riunioni online in audioconferenza. È possibile ottenere altre informazioni, inclusi gli importi di finanziamento consigliati, [leggendo Che cosa sono i crediti comunicazioni?](what-are-communications-credits.md)
  
> [!NOTE]
> Per scoprire quanto costa, [consulta i prezzi qui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>Passaggio 1: Assegnare una licenza per audioconferenze o piani per chiamate agli utenti

Quando si effettua la registrazione, si ottiene un determinato numero di minuti, a seconda del proprio paese o della propria area geografica. Puoi cercare il tuo paese o area geografica nell'elenco di disponibilità del Paese o dell'area geografica per [Audioconferenza](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) e Piani per le chiamate per vedere il numero di minuti che otterrà. Una volta esaurito il numero di minuti, le chiamate verranno disconnesse. Per evitare ciò, impostare i Crediti comunicazioni.
  
Per farlo, **occorre assegnare agli utenti una licenza per Audioconferenza o Sistema telefonico**.
  
- Assegnare una licenza per i servizi di **Audioconferenza** agli utenti. Vedere [Assegnare licenze per i componenti aggiuntivi di Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
    Dopo aver assegnato la licenza, è necessario impostare i servizi di audioconferenza. Per istruzioni dettagliate, vedere Provare o acquistare audioconferenze [in Microsoft 365 o Office 365.](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
- Assegna **sistema telefonico e** una licenza per piani per chiamate nazionali o **nazionali** e internazionali agli utenti. Vedere [Assegnare licenze per i componenti aggiuntivi di Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
    > [!NOTE]
    > Anche se non è necessario per i Crediti comunicazioni,  è comunque necessario assegnare anche un piano per chiamate nazionali o una **licenza** per piani per chiamate nazionali e internazionali.
  
    Dopo avere assegnato le licenze, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti. Per istruzioni dettagliate, vedere [Configurare i piani per chiamate.](set-up-calling-plans.md)
    
Per altre informazioni, vedere Licenze [per i componenti aggiuntivi](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) di Microsoft Teams
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Passaggio 2: configurare i Crediti comunicazioni per la propria organizzazione

1. Accedere all'interfaccia [di amministrazione di Microsoft 365](https://portal.office.com/Adminportal) con l'account aziendale o dell'istituto di istruzione.
    
2. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 passare a **Servizi di**  >  **acquisto fatturazione.** Scorrere verso il basso e **selezionare Componenti aggiuntivi**.

3. Selezionare **Crediti comunicazioni**.
    
4. Nella pagina **Di sottoscrizione crediti comunicazioni** immettere le informazioni e quindi fare clic su **Avanti:**
    
   - **Aggiungi fondi** Immettere l'importo da aggiungere al proprio account. Se l'opzione di ricarica automatica non è attiva, una volta esauriti i fondi, i Crediti comunicazioni saranno disabilitati (come il servizio per i numeri verdi in entrata). Per evitare di dover ricaricare fondi per i Crediti comunicazioni ogni volta che i fondi disponibili si esauriscono, si consiglia di attivare la funzionalità di autoricarica.
    
   - **Autoricarica** L'autoricarica consente di aggiungere automaticamente fondi al saldo quando scende al di sotto dell'importo configurato.
    
     È consigliabile utilizzare la funzione **Autoricarica** per evitare qualsiasi interruzione del servizio, nel caso in cui i Crediti comunicazioni arrivino a 0 (zero). Verrà inviata un'e-mail al completamento della transazione di ricarica, quando essa non va a buon fine (ad esempio una carta di credito scaduta) e anche quando i Crediti comunicazioni arrivano a 0 (zero).
    
   - **Somma di autoricarica** Nella casella **Ricarica con** indicare l'importo della ricarica da aggiungere automaticamente al proprio account quando il saldo va al di sotto dell'importo configurato.
    
   - **Importo configurato** Specificare l'importo nella casella **Quando il credito scende al di sotto di**, che indicherà quando ' *attivare*  ' l'autoricarica. Quando il credito scende al di sotto di tale importo, l'importo di ricarica specificato verrà aggiunto automaticamente al saldo del tuo account.

      > [!NOTE]
     > I fondi verranno applicati solo ai servizi Crediti comunicazioni alle tariffe Microsoft pubblicate quando i servizi vengono utilizzati. Eventuali fondi non utilizzati entro 12 mesi dalla data di acquisto andranno persi. 
     > 
     > La fatturazione mensile per i Crediti comunicazioni verrà applicata solo se è stato usato il fondo assegnato, per informazioni su come controllare l'utilizzo mensile, leggi il report sull'utilizzo [pstn di Skype for Business](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)
    
5. Immettere le informazioni di pagamento e scegliere **Esecuzione dell'ordine**.
    >[!IMPORTANT]
    >Se si è un cliente di licenze volume, è possibile scegliere il numero di contratto enterprise agreement per il pagamento. Se si dispone di più numeri di enterprise agreement, sarà possibile selezionare il contratto enterprise agreement che si desidera utilizzare per il pagamento. Sarà inoltre possibile specificare un numero d'ordine di acquisto per associare il numero di contratto enterprise agreement (se applicabile).
    
Ogni organizzazione farà un diverso uso dei Piani per chiamate, a seconda del volume e delle tariffe. Sarà necessario chiedere questo tipo di dati di utilizzo al provider di servizi corrente. Le organizzazioni che già usano Skype for Business online come provider di servizi possono ottenere i dati di utilizzo esaminando i dati nell'interfaccia di amministrazione di **Microsoft Teams** Report sui dettagli sull'utilizzo  >    >  **PSTN.**
  
Quando si configurano i Crediti comunicazioni, è necessario esaminare l'utilizzo delle chiamate per l'organizzazione per determinare gli importi necessari. Per ottenere informazioni sull'uso delle chiamate, esaminare il report **Dettagli dell'utilizzo della rete PSTN**. Questo report consente di esportare i record dei dati delle chiamate in Excel se è necessario archiviare i dati o creare report personalizzati. Per informazioni su come vedere l'utilizzo, vedere [Report sull'utilizzo PSTN.](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Passaggio 3: assegnare agli utenti una licenza Crediti comunicazioni

1. Accedere all'interfaccia [di amministrazione di Microsoft 365](https://portal.office.com/Adminportal) con l'account aziendale o dell'istituto di istruzione.
    
2. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 passare a **Utenti** utenti attivi e quindi  >  selezionare un utente nell'elenco.
    
3. Scegliere **Licenze e app.**
    
4. Impostare **Crediti comunicazioni su** **Attivato** per assegnare la licenza e quindi selezionare **Salva**.
    
    > [!NOTE]
    > Anche se ad alcuni utenti è assegnata una licenza **Enterprise E5**, è consigliabile comunque procedere in questo modo.

    > [!TIP]
    > È possibile usare [PowerShell per](/powershell/module/skype/?view=skype-ps) assegnare licenze e app a più utenti con un solo comando.
  
## <a name="want-to-know-about-plans-and-pricing"></a>Informazioni su piani e prezzi.

Per consultare piani e prezzi, consultare uno di questi link:
  
- [Piani per chiamate](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [Piani di audioconferenza](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Piani Sistema telefonico](https://go.microsoft.com/fwlink/?LinkId=799763)
    
È anche possibile visualizzare le informazioni accedendo all'interfaccia di amministrazione di [Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e accedendo a **Abbonamenti** di fatturazione  >    >  **Aggiungi abbonamenti.**
  
Per visualizzare una tabella con la licenza o le licenze necessarie per ogni funzionalità, vedere Licenze [per i componenti aggiuntivi di Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="related-topics"></a>Argomenti correlati

- [Configurare Skype for Business online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [Configurare Cloud Voicemail - Guida per gli amministratori](set-up-phone-system-voicemail.md)
    
- [Configurare piani per chiamate e](set-up-calling-plans.md) piani per chiamate per Microsoft [365 o Office 365](calling-plans-for-office-365.md)
    
- [Aggiungere fondi e gestire Credito per la comunicazione](add-funds-and-manage-communications-credits.md)
    
  
