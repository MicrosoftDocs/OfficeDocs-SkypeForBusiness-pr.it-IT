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
ms.openlocfilehash: 51885d80e698d0f47308c45110af83063e7bd7ba
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031392"
---
# <a name="set-up-communications-credits-for-your-organization"></a>Configurare i Crediti comunicazioni per la propria organizzazione

Devi impostare i Crediti comunicazioni se desideri utilizzare numeri verde con Skype for Business e Microsoft Teams. Inoltre, è consigliabile impostare i Crediti comunicazioni per i Piani per chiamate (nazionali o internazionali) e per gli utenti di audioconferenza che hanno bisogno di effettuare chiamate in uscita verso **qualsiasi destinazione.** Sono inclusi molti paesi/aree geografiche, ma alcune destinazioni potrebbero non essere incluse nel tuo Piano per chiamate o Audioconferenza. Se non viene impostata la fatturazione dei Crediti comunicazioni e assegnata una licenza Crediti comunicazioni agli utenti e vengono eseguiti minuti per l'organizzazione **(a** seconda del piano per chiamate o audioconferenza del proprio paese/area geografica), tali utenti non potranno effettuare chiamate o chiamate in uscita dalle riunioni in audioconferenza. Per ulteriori informazioni, compresi gli importi consigliati per il pagamento, leggi [Cosa sono i Crediti comunicazioni?](what-are-communications-credits.md)
  
> [!NOTE]
> Per scoprire quanto costa, [consulta i prezzi qui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>Passaggio 1: Assegnare agli utenti una licenza per audioconferenze o piani per chiamate

Al momento dell'iscrizione, si ottiene un determinato numero di minuti, a seconda del paese o dell'area geografica. Puoi cercare il tuo paese [](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization) o area geografica nell'elenco di disponibilità per audioconferenze e piani per chiamate per vedere il numero di minuti che vuoi ricevere. Dopo aver utilizzato questi minuti, le chiamate verranno disconnesse. Per evitare ciò, è necessario impostare i Crediti comunicazioni.
  
Per farlo, **occorre assegnare agli utenti una licenza per Audioconferenza o Sistema telefonico**.
  
- Assegnare una licenza per i servizi **di audioconferenza** agli utenti. Vedi [Assegnare le licenze per i componenti aggiuntivi di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
    
    Dopo aver assegnato la licenza, è necessario impostare i servizi di audioconferenza. Per istruzioni dettagliate, vedere Provare o acquistare audioconferenze [in Microsoft 365 o Office 365.](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
- Assegnare **agli utenti** una **licenza Sistema telefonico e** un Piano per chiamate nazionali o nazionali e internazionali. Vedi [Assegnare le licenze per i componenti aggiuntivi di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
    
    > [!NOTE]
    > Anche se non è necessario per i Crediti comunicazioni,  è comunque necessario assegnare anche una licenza per un Piano per chiamate **nazionali** o internazionali.
  
    Dopo aver assegnato queste licenze, dovrai recuperare i numeri di telefono per l'organizzazione e assegnarli agli utenti. Per istruzioni dettagliate, consulta [Configurare i Piani per chiamate.](set-up-calling-plans.md)
    
Per altre informazioni, vedere [l'articolo sulle licenze per i componenti aggiuntivi di Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Passaggio 2: configurare i Crediti comunicazioni per la propria organizzazione

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com/Adminportal) con l'account aziendale o dell'istituto di istruzione.
    
2. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 passare a **Acquisto**  >  **di servizi di fatturazione.** Scorrere verso il basso **e selezionare Componenti aggiuntivi.**

3. Seleziona **Crediti comunicazioni.**
    
4. Nella pagina **dell'abbonamento ai Crediti** comunicazioni, inserisci le informazioni e quindi fai clic su **Avanti:**
    
   - **Aggiungi fondi** Immettere l'importo da aggiungere al proprio account. Se l'opzione di ricarica automatica non è attiva, una volta esauriti i fondi, i Crediti comunicazioni saranno disabilitati (come il servizio per i numeri verdi in entrata). Per evitare di dover ricaricare fondi per i Crediti comunicazioni ogni volta che i fondi disponibili si esauriscono, si consiglia di attivare la funzionalità di autoricarica.
    
   - **Autoricarica** L'autoricarica consente di aggiungere automaticamente fondi al saldo quando scende al di sotto dell'importo configurato.
    
     È consigliabile utilizzare la funzione **Autoricarica** per evitare qualsiasi interruzione del servizio, nel caso in cui i Crediti comunicazioni arrivino a 0 (zero). Verrà inviata un'e-mail al completamento della transazione di ricarica, quando essa non va a buon fine (ad esempio una carta di credito scaduta) e anche quando i Crediti comunicazioni arrivano a 0 (zero).
    
   - **Somma di autoricarica** Nella casella **Ricarica con** indicare l'importo della ricarica da aggiungere automaticamente al proprio account quando il saldo va al di sotto dell'importo configurato.
    
   - **Importo configurato** Specificare l'importo nella casella **Quando il credito scende al di sotto di**, che indicherà quando ' *attivare*  ' l'autoricarica. Quando il credito scende al di sotto di tale importo, l'importo di ricarica specificato verrà aggiunto automaticamente al saldo del tuo account.

      > [!NOTE]
     > I fondi verranno applicati solo ai servizi Crediti comunicazioni alle tariffe Microsoft pubblicate quando i servizi vengono utilizzati. Eventuali fondi non utilizzati entro 12 mesi dalla data di acquisto andranno persi. 
     > 
     > La fatturazione mensile per i Crediti comunicazioni verrà applicata solo se è stato utilizzato il fondo assegnato, per sapere come controllare l'utilizzo mensile, leggi il report di utilizzo [PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) di Skype for Business
    
5. Immettere le informazioni di pagamento e scegliere **Esecuzione dell'ordine**.
    >[!IMPORTANT]
    >Se si è un cliente di licenze volume, è possibile scegliere il numero di contratto enterprise agreement per il pagamento. Se si dispone di più numeri di enterprise agreement, sarà possibile selezionare il contratto enterprise agreement che si desidera utilizzare per il pagamento. Sarà inoltre possibile specificare un numero d'ordine di acquisto per associare il numero di contratto enterprise agreement (se applicabile).
    
Ogni organizzazione farà un diverso uso dei Piani per chiamate, a seconda del volume e delle tariffe. Sarà necessario chiedere questo tipo di dati di utilizzo al provider di servizi corrente. Le organizzazioni che usano già Skype for Business online come provider di servizi possono recuperare i dati di utilizzo esaminando i dati nel report dei dettagli sull'utilizzo di PSTN dell'interfaccia di amministrazione di **Microsoft**  >    >   Teams.
  
Quando si impostano i Crediti comunicazioni, è necessario analizzare l'uso delle chiamate nella propria organizzazione per determinare gli importi necessari. Per ottenere informazioni sull'uso delle chiamate, esaminare il report **Dettagli dell'utilizzo della rete PSTN**. Questo report consente di esportare i record dei dati delle chiamate in Excel se è necessario archiviare i dati o creare report personalizzati. Per informazioni su come visualizzare l'utilizzo, leggere il [report sull'utilizzo di PSTN.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Passaggio 3: assegnare agli utenti una licenza Crediti comunicazioni

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://portal.office.com/Adminportal) con l'account aziendale o dell'istituto di istruzione.
    
2. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 passare a Utenti attivi e quindi selezionare un utente  >  nell'elenco.
    
3. Scegliere **Licenze e app.**
    
4. Attiva **i Crediti comunicazioni** **per** assegnare questa licenza, quindi seleziona **Salva.**
    
    > [!NOTE]
    > Anche se ad alcuni utenti è assegnata una licenza **Enterprise E5**, è consigliabile comunque procedere in questo modo.

    > [!TIP]
    > È possibile usare [PowerShell per](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps) assegnare licenze e app a più utenti con un unico comando.
  
## <a name="want-to-know-about-plans-and-pricing"></a>Informazioni su piani e prezzi.

Per consultare piani e prezzi, consultare uno di questi link:
  
- [Piani per chiamate](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [Piani per audioconferenze](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Piani Sistema telefonico](https://go.microsoft.com/fwlink/?LinkId=799763)
    
Per visualizzare le informazioni, è anche possibile accedere all'interfaccia di amministrazione di [Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e andare **ad** Aggiungi abbonamenti  >  **fatturazione.**  >  
  
Per visualizzare una tabella con la licenza o le licenze necessarie per ogni funzionalità, vedere Licenze per i componenti aggiuntivi [di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
## <a name="related-topics"></a>Argomenti correlati

- [Configurare Skype for Business online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [Configurare Cloud Voicemail - Guida per gli amministratori](set-up-phone-system-voicemail.md)
    
- [Configurare piani per chiamate](set-up-calling-plans.md) e [piani per chiamate per Microsoft 365 o Office 365](calling-plans-for-office-365.md)
    
- [Aggiungere fondi e gestire Credito per la comunicazione](add-funds-and-manage-communications-credits.md)
    
  
 
