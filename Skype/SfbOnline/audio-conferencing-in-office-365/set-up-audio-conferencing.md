---
title: Configurazione di conferenze Audio per Skype per le aziende
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: "Informazioni su come impostare dial-in o conferenze Audio per le persone in un'azienda che devono utilizzare un telefono per partecipare a conferenze telefoniche. "
ms.openlocfilehash: d57eedec13d9bd1c01ec9365fd42c0a4dfdc2d96
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229312"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>Configurazione di conferenze Audio per Skype per le aziende

A volte le persone all’interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione. Skype per le aziende include la funzionalità di audioconferenza per solo questa situazione! Le persone possono chiamare Skype per le riunioni aziendali mediante un telefono, anziché utilizzare il Skype per applicazioni aziendali in un dispositivo mobile o un PC. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Per le domande frequenti sui servizi di audioconferenza, vedere [Domande frequenti su Audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions).

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Passo 1: Verificare se l'Audioconferenza è disponibile nel tuo Paese o nella tua area geografica
<a name="__top"> </a>

Vai a [Disponibilità di audioconferenza e Piani di chiamata per Paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e seleziona il Paese o l'area geografica per ottenere informazioni sulla disponibilità del servizio di Audioconferenza, nonché informazioni relative a Sistema telefonico, Piani di chiamata, numeri a pagamento e numeri verdi, e Credito per la comunicazione. 
 
## <a name="step-2-get-and-assign-licenses"></a>Passo 2: Ottenere e assegnare licenze
 
1. Per l'Audioconferenza, è necessaria una licenza per ogni utente che configurerà le riunioni con accesso esterno. Per ulteriori le licenze che è necessario acquistare per le conferenze Audio e il relativo verrà costo, vedere [Skype per la gestione delle licenze di componente aggiuntivo Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Audioconferenze con accesso esterno è inclusa in Office 365 Enterprise E5 licenze e come componente aggiuntivo.
        
2. Dopo che acquistare le licenze di conferenze Audio, è necessario assegnarli a tali persone all'interno dell'organizzazione che desiderano programmare o condurre riunioni. Vedere [assegnare o rimuovere licenze per Office 365 per aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) è stato acquistato per gli utenti dell'organizzazione che intende pianificazione o lead riunioni.
    
3. È inoltre consigliabile assegnare licenze di Credito per la comunicazione (non costano nulla) agli stessi utenti a cui sono state assegnate le licenze nel passo precedente. Per informazioni su come impostare i titoli di coda di comunicazioni, vedere [impostare i titoli di coda di comunicazione per l'organizzazione](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> È inoltre possibile impostare [Conferenze Audio retribuzione al minuto](/microsoftteams/audio-conferencing-pay-per-minute).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Passo 3: Ottenere i numeri di servizio per i ponti per audioconferenza
<a name="__top"> </a>

Non è possibile utilizzare numeri di telefono per gli utenti per l'Audioconferenza. È necessario ottenere numeri di servizio. Per i ponti per audioconferenza è possibile ottenere numeri di servizio a pagamento o numeri verdi. Esistono tre modi per ottenere numeri di servizio a pagamento o numeri verdi: 
  
- **Utilizzare Skype per interfaccia di amministrazione di Business**. Per alcuni paesi, è possibile ottenere i numeri di servizio per i ponti di audioconferenze con il Skype per interfaccia di amministrazione di Business. Vedere [i numeri di telefono del servizio di Guida](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Porta i numeri di servizio esistente**. In porta o trasferimento esistenti numeri dal provider di servizi corrente o gestore telefonico per Office 365. Per ulteriori informazioni su come eseguire questa operazione, è possibile consultare [Trasferire numeri di telefono in Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) o [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization).  
  
- **Utilizzare un modulo di richiesta per nuovi numeri**. In alcuni casi (a seconda del paese/area geografica) non sarà in grado di ottenere i nuovi numeri servizio con il Skype per interfaccia di amministrazione di Business o sarà necessario area codici o i numeri di telefono specifico. In questo caso, dovrai scaricare un modulo e inviarcelo. Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Passo 4: Assegnare un numero di servizio al ponte per audioconferenza
<a name="__top"> </a>

Una volta che viene visualizzato il numero a tariffa e/o numeri verdi per i bridge conferenza, è necessario assegnare i numeri in modo che possono essere utilizzati negli inviti alle riunioni.  

Per assegnare un nuovo numero di telefono per il ponte per audioconferenza:

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**

 1. Vai al **Centro di amministrazione di Microsoft 365** > **Admin Center** > **Team** > **portale Legacy**.
 2. Selezionare **segreteria** > **i numeri di telefono**.
 3. Selezionare il numero di telefono e fare clic su **Assegna**.

Per ulteriori informazioni, vedere [modificare i numeri di telefono del ponte per conferenze audio](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Passo 5: Impostare le lingue predefinite e alternative per un ponte per audioconferenza
<a name="__top"> </a>

Si desidera [impostare le lingue di operatore automatico per le conferenze Audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) che utilizza l'operatore automatico di servizi di conferenza per saluti salutare i chiamanti quando si effettua la chiamata a un numero di telefono per le audioconferenze. 

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando l'interfaccia di amministrazione di team Microsoft che**:

1. Nel Dashboard di accedere alle **riunioni** > **Bridge conferenza**.
2. Selezionare il numero di telefono di ponte conferenza, fare clic su **Modifica**e quindi fare clic sulla lingua predefinita.

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per Business admin center**:

1. Vai al **Centro di amministrazione di Office 365** > **Admin Center** > **Team** > **portale Legacy**.
2. Selezionare **audioconferenze** > **bridge di Microsoft**. 
3. Selezionare il numero di telefono di ponte conferenza, selezionare **Set di lingue**e quindi fare clic sulla lingua predefinita.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Passo 6: Configurare le impostazioni del ponte per audioconferenza
<a name="__top"> </a>
    
Dopo aver impostato il ponte per audioconferenza, verifica che le impostazioni predefinite, ad esempio le notifiche di ingresso e di uscita e la lunghezza del PIN siano quelle desiderate; se non lo sono, è possibile modificarle. 

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando l'interfaccia di amministrazione di team Microsoft che**:

1. Nel Dashboard di accedere alle **riunioni** > **Bridge conferenza**.
2. Selezionare **Impostazioni Bridge**. Verrà visualizzato il riquadro **Impostazioni ponte**. 

Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**

1. Vai al **Centro di amministrazione di Microsoft 365** > **Admin Center** > **Team** > **portale Legacy**.
2. Selezionare **audioconferenze** > **Impostazioni bridge di Microsoft**. Verrà visualizzata la pagina **Impostazioni ponte Microsoft**. 

Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Passo 7: Assegnare i numeri di telefono con accesso esterno per gli utenti che conducono le riunioni

Dopo aver creato un ponte per Audioconferenza, è necessario impostare i numeri a pagamento e i numeri verdi per gli utenti.

È necessario eseguire questa operazione per tutti gli utenti dell'organizzazione che conducono o pianificano riunioni. 

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando l'interfaccia di amministrazione di team Microsoft che**:

1. Nel dashboard, fare clic su **utenti**, selezionare l'utente dall'elenco e selezionare **Modifica**.
2. Selezionare **Modifica** accanto a **Servizi di conferenza Audio**e quindi nel riquadro di **Conferenze Audio** , selezionare un numero negli elenchi numeri **numero a pagamento** e il **numero verde** .

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**

1. Vai al **Centro di amministrazione di Microsoft 365** > **Team** > **portale Legacy**.
2. Selezionare **audioconferenze** > **gli utenti**, quindi selezionare l'utente dall'elenco e fare clic su **Modifica**. 

Per ulteriori informazioni, consulta [Assegnare Microsoft come provider di servizi di audioconferenza](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Passo 8: Configurare gli inviti alla riunione (facoltativo)
<a name="__top"> </a>
 
I numeri di accesso impostate per l'utente verranno aggiunta automaticamente per gli inviti alle riunioni inviati ai partecipanti alla riunione. Tuttavia, è possibile aggiungere Guida personalizzata e collegamenti legali, un messaggio di testo e immagine piccola società se si desidera. Vedere [Personalizza convocazioni di riunione](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Argomenti correlati

[Domande ricorrenti sulle audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurare Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Numeri di telefono per i servizi di audioconferenza](phone-numbers-for-audio-conferencing.md)
  
[Impostare le opzioni per riunioni online e conferenze telefoniche](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
