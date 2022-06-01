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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 9cbd49ed35b3bd52c7b00decf67cab0e01d0a320
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823597"
---
# <a name="set-up-communications-credits-for-your-organization"></a>Configurare i Crediti comunicazioni per la propria organizzazione

[] Per usare i numeri verdi in Skype for Business e Microsoft Teams, sono necessari Crediti comunicazioni. Inoltre, è consigliabile impostare i Crediti comunicazioni per i Piani per chiamate (nazionali e internazionali) e Audioconferenza che hanno necessità di effettuare chiamate in uscita verso **qualsiasi destinazione**. Sono inclusi molti paesi/aree geografiche, ma alcune destinazioni PSTN possono non essere incluse in un dato abbonamento Piano per chiamate e Audioconferenza. Se non vengono impostati i Crediti comunicazioni o assegnata una licenza **Crediti comunicazioni** agli utenti e vengono esauriti i minuti per la propria organizzazione (a seconda del Piano per chiamate e Audioconferenza per lo specifico paese/area geografica), quegli utenti non potranno effettuare chiamate o chiamate in uscita dalle riunioni online in audioconferenza. Puoi ottenere ulteriori informazioni, inclusi gli importi di finanziamento consigliati, leggendo [Cosa sono i Crediti comunicazioni?](what-are-communications-credits.md)
  
> [!NOTE]
> Per scoprire quanto costa, [consulta i prezzi qui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>Passaggio 1: Assegnare una licenza per un piano di Audioconferenza o per chiamate agli utenti

Quando si effettua la registrazione, si ottiene un determinato numero di minuti, a seconda del proprio paese o della propria area geografica. Puoi cercare il tuo paese o area geografica [nell'elenco di disponibilità del Paese o dell'area geografica per Audioconferenza e Piani per chiamate](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) per vedere il numero di minuti che otterrai. Una volta esaurito il numero di minuti, le chiamate verranno disconnesse. Per evitare ciò, impostare i Crediti comunicazioni.
  
A questo scopo, **è necessario assegnare una licenza Audioconferenza o Sistema telefonico** agli utenti. I Crediti comunicazioni possono essere abilitati per gli utenti a cui è assegnata una o entrambe le licenze.
  
- Assegnare una licenza per i servizi di **Audioconferenza** agli utenti. Vedere [Assegnare licenze per Microsoft Teams componenti aggiuntivi](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
    Dopo aver assegnato la licenza, è necessario impostare i servizi di audioconferenza. Per istruzioni dettagliate, vedere [Provare o acquistare Audioconferenza in Microsoft 365 o Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).
    
- Assegnare **agli utenti Sistema telefonico** e una licenza per un piano per chiamate **nazionali o nazionali e internazionali**. Vedere [Assegnare licenze per Microsoft Teams componenti aggiuntivi](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Anche se non è obbligatorio per i Crediti comunicazioni, devi comunque assegnare anche una licenza per un **piano per chiamate nazionali** o **internazionali** .
  
    Dopo avere assegnato le licenze, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti. Per istruzioni dettagliate, vedi [Configurare i piani per chiamate](set-up-calling-plans.md).
    
Per altre informazioni, vedere [Licenze per Microsoft Teams componenti aggiuntivi](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Passaggio 2: configurare i Crediti comunicazioni per la propria organizzazione

1. Accedere alla [interfaccia di amministrazione di Microsoft 365](https://portal.office.com/Adminportal) con l'account aziendale o dell'istituto di istruzione.
    
2. Nel riquadro di spostamento sinistro della interfaccia di amministrazione di Microsoft 365 passare a **Servizi** di acquisto **fatturazione** > .

3. Cerca **Crediti comunicazioni** nella categoria componenti **aggiuntivi** o cerca "Crediti comunicazioni" nella casella **di ricerca Cerca in tutte le categorie di prodotti** e seleziona **Dettagli**.
    
4. Esaminare le informazioni sul servizio e selezionare **Acquista**. Nota: un numero fisso di licenze di Crediti comunicazioni viene selezionato automaticamente in ogni ordine.

5. Nella pagina Cassa immettere le informazioni sul pagamento e immettere le informazioni necessarie:
    
   - **Aggiungi fondi** Immettere l'importo da aggiungere al proprio account. Se l'opzione di ricarica automatica non è attiva, una volta esauriti i fondi, i Crediti comunicazioni saranno disabilitati (come il servizio per i numeri verdi in entrata). Per evitare di dover ricaricare fondi per i Crediti comunicazioni ogni volta che i fondi disponibili si esauriscono, si consiglia di attivare la funzionalità di autoricarica.
    
   - **Autoricarica** L'autoricarica consente di aggiungere automaticamente fondi al saldo quando scende al di sotto dell'importo configurato.
    
     È consigliabile utilizzare la funzione **Autoricarica** per evitare qualsiasi interruzione del servizio, nel caso in cui i Crediti comunicazioni arrivino a 0 (zero). Verrà inviata un'e-mail al completamento della transazione di ricarica, quando essa non va a buon fine (ad esempio una carta di credito scaduta) e anche quando i Crediti comunicazioni arrivano a 0 (zero).
    
   - **Somma di autoricarica** Nella casella **Ricarica con** indicare l'importo della ricarica da aggiungere automaticamente al proprio account quando il saldo va al di sotto dell'importo configurato.
    
   - **Importo configurato** Specificare l'importo nella casella **Quando il credito scende al di sotto di**, che indicherà quando ' *attivare*  ' l'autoricarica. Quando il credito scende al di sotto di tale importo, l'importo di ricarica specificato verrà aggiunto automaticamente al saldo del tuo account.

      > [!NOTE]
     > I fondi verranno applicati solo ai servizi Crediti comunicazioni alle tariffe Microsoft pubblicate quando i servizi vengono utilizzati. Eventuali fondi non utilizzati entro 12 mesi dalla data di acquisto andranno persi. 
     > 
     > Quando si usa la funzione di autoricarica, la fatturazione per i Crediti comunicazioni viene generata quando viene raggiunto l'importo trigger e viene elaborata una transazione di ricarica. Gli importi di credito per le comunicazioni vengono utilizzati per primi. Per informazioni su come controllare l'utilizzo mensile, leggere [Microsoft Teams report sull'utilizzo di PSTN](/microsoftteams/teams-analytics-and-reports/pstn-usage-report).
    
6. Seleziona **Effettua ordine**.
    >[!IMPORTANT]
    >Se si è un cliente con contratti multilicenza, è consigliabile usare il contratto aziendale per il pagamento. Se vuoi eseguire questa operazione, apri un caso di supporto Premier per abilitare questa funzionalità. Se si dispone di più numeri di enterprise agreement, sarà possibile selezionare il contratto enterprise agreement che si desidera utilizzare per il pagamento. Potrai anche specificare un numero di ordine d'acquisto da associare al numero del contratto enterprise (se applicabile) una volta che il supporto lo avrà abilitato.
    
Ogni organizzazione farà un diverso uso dei Piani per chiamate, a seconda del volume e delle tariffe. Sarà necessario chiedere questo tipo di dati di utilizzo al provider di servizi corrente. Le organizzazioni che usano già Skype for Business Online o Microsoft Teams come provider di servizi possono ottenere i dati di utilizzo esaminandoli nei report  >  di utilizzo di **Analytics &** dell'interfaccia di **amministrazione di Microsoft Teams** >  e **dei report** > **sull'utilizzo di PSTN e di SMS (anteprima).**
  
Quando si configurano i Crediti comunicazioni, è necessario analizzare l'utilizzo delle chiamate da parte dell'organizzazione per determinare gli importi necessari. È possibile ottenere informazioni sull'utilizzo delle chiamate esaminando il report **sull'utilizzo di PSTN e SMS (anteprima).** Questo report consente di esportare i record dei dati delle chiamate in Excel se è necessario archiviare i dati o creare report personalizzati. Per informazioni su come visualizzare l'utilizzo, leggere [Microsoft Teams report sull'utilizzo di PSTN](/microsoftteams/teams-analytics-and-reports/pstn-usage-report).
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Passaggio 3: assegnare agli utenti una licenza Crediti comunicazioni

1. Accedere alla [interfaccia di amministrazione di Microsoft 365](https://portal.office.com/Adminportal) con l'account aziendale o dell'istituto di istruzione.
    
2. Nel riquadro di spostamento sinistro della interfaccia di amministrazione di Microsoft 365 passare a **Utenti** > **attivi** e quindi selezionare un utente dall'elenco.
    
3. Scegliere **Licenze e app**.
    
4. Imposta **Crediti comunicazioni** **su Attivato** per assegnare questa licenza e quindi seleziona **Salva**.
    
    > [!NOTE]
    > Anche se ad alcuni utenti è assegnata una licenza **Enterprise E5**, è consigliabile comunque procedere in questo modo.

    > [!TIP]
    > È possibile usare [Powershell](/powershell/module/skype/?view=skype-ps&preserve-view=true) per assegnare licenze e app a più utenti con un unico comando.
  
## <a name="want-to-know-about-plans-and-pricing"></a>Informazioni su piani e prezzi.

Per consultare piani e prezzi, consultare uno di questi link:
  
- [Piani per chiamate](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [piani di Audioconferenza](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Piani Sistema telefonico](https://go.microsoft.com/fwlink/?LinkId=799763)
    
Per visualizzare informazioni, è anche possibile [accedere al interfaccia di amministrazione di Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e passare a **Fatturazione** > **abbonamenti** > **Aggiungi abbonamenti**.
  
Per visualizzare una tabella con la licenza o le licenze necessarie per ogni funzionalità, vedere [Microsoft Teams licenze per i componenti aggiuntivi](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
## <a name="related-topics"></a>Argomenti correlati

- [Configurare Skype for Business online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [Configurare Cloud Voicemail - Guida per gli amministratori](set-up-phone-system-voicemail.md)
    
- [Configurare piani per](set-up-calling-plans.md) chiamate e [piani per chiamate per Microsoft 365 o Office 365](calling-plans-for-office-365.md)
    
- [Aggiungere fondi e gestire Credito per la comunicazione](add-funds-and-manage-communications-credits.md)
    
  
