---
title: Configurare i servizi di audioconferenza per Skype for business
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: "Informazioni su come configurare le conferenze telefoniche con accesso esterno o audio per gli utenti dell'azienda che hanno bisogno di usare un telefono per partecipare alle conferenze telefoniche. "
ms.openlocfilehash: 37bdc3208934d6ef9a7d97b896988b705735c869
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2019
ms.locfileid: "34343839"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>Configurare i servizi di audioconferenza per Skype for business

A volte le persone all’interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione. Skype for business include la funzionalità per i servizi di audioconferenza solo per questa situazione. Gli utenti possono chiamare riunioni Skype for business usando un telefono, invece di usare l'app Skype for business in un dispositivo mobile o un PC. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Per le domande frequenti sui servizi di audioconferenza, vedere [Domande frequenti su Audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions).

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Passo 1: Verificare se l'Audioconferenza è disponibile nel tuo Paese o nella tua area geografica
<a name="__top"> </a>

Vai a [Disponibilità di audioconferenza e Piani di chiamata per Paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e seleziona il Paese o l'area geografica per ottenere informazioni sulla disponibilità del servizio di Audioconferenza, nonché informazioni relative a Sistema telefonico, Piani di chiamata, numeri a pagamento e numeri verdi, e Credito per la comunicazione. 
 
## <a name="step-2-get-and-assign-licenses"></a>Passo 2: Ottenere e assegnare licenze
 
1. Per l'Audioconferenza, è necessaria una licenza per ogni utente che configurerà le riunioni con accesso esterno. Per informazioni sulle licenze che è necessario acquistare per i servizi di audioconferenza e sul costo, vedere licenze per i [componenti aggiuntivi Skype for business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > I servizi di audioconferenza sono inclusi nelle licenze di Office 365 Enterprise E5 e come componente aggiuntivo.
        
2. Dopo aver acquistato le licenze per i servizi di audioconferenza, è necessario assegnarle alle persone dell'organizzazione che hanno intenzione di pianificare o condurre riunioni. Vedere [assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) acquistate agli utenti dell'organizzazione che hanno intenzione di pianificare o condurre riunioni.
    
3. È inoltre consigliabile assegnare licenze di Credito per la comunicazione (non costano nulla) agli stessi utenti a cui sono state assegnate le licenze nel passo precedente. Per informazioni su come configurare i crediti per le comunicazioni, vedere [configurare i crediti per le comunicazioni per l'organizzazione](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> È anche possibile configurare servizi [di audioconferenza pay-per-minute](/microsoftteams/audio-conferencing-pay-per-minute).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Passo 3: Ottenere i numeri di servizio per i ponti per audioconferenza
<a name="__top"> </a>

Non è possibile utilizzare numeri di telefono per gli utenti per l'Audioconferenza. È necessario ottenere numeri di servizio. Per i ponti per audioconferenza è possibile ottenere numeri di servizio a pagamento o numeri verdi. Esistono tre modi per ottenere numeri di servizio a pagamento o numeri verdi: 
  
- **Usare l'interfaccia di amministrazione di Skype for business**. Per alcuni paesi/aree geografiche è possibile ottenere i numeri di servizio per i ponti di conferenza usando l'interfaccia di amministrazione di Skype for business. Vedere [recupero di numeri di telefono del servizio](/microsoftteams/getting-service-phone-numbers).
    
- **Trasferire i numeri di servizio esistenti**. Per convertire o trasferire i numeri esistenti dal provider di servizi o dal gestore di telefonia corrente a Office 365. Per ulteriori informazioni su come eseguire questa operazione, è possibile consultare [Trasferire numeri di telefono in Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) o [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization).  
  
- **Usare un modulo di richiesta per i nuovi numeri**. A volte, a seconda del paese o dell'area geografica, non potrai ottenere i nuovi numeri di servizio usando l'interfaccia di amministrazione di Skype for business oppure avrai bisogno di numeri di telefono o codici di area specifici. In questo caso, dovrai scaricare un modulo e inviarcelo. Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Passo 4: Assegnare un numero di servizio al ponte per audioconferenza
<a name="__top"> </a>

Dopo aver ottenuto i numeri di telefono a pagamento e/o il numero verde per il Bridge di conferenza, è necessario assegnare i numeri in modo che possano essere usati per gli inviti alle riunioni.  

Per assegnare un nuovo numero di telefono per il ponte per audioconferenza:

![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **con l'interfaccia di amministrazione di Skype for business:**

 1. **** > Accedere al**portale legacy**di interfaccia di amministrazione di **Microsoft 365 Admin Center** > **Teams** > .
 2. Selezionare **** > **numeri di telefono**vocali.
 3. Selezionare il numero di telefono e fare clic su **assegna**.

Per altre informazioni, vedere [modificare i numeri di telefono nel Bridge di audioconferenza](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Passo 5: Impostare le lingue predefinite e alternative per un ponte per audioconferenza
<a name="__top"> </a>

Si vogliono quindi impostare le [lingue dell'operatore automatico per](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) i servizi di audioconferenza che l'operatore automatico di conferenza USA per salutare i chiamanti quando effettuano la chiamata a un numero di telefono per i servizi di audioconferenza. 

![Icona che mostra il logo](../images/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**:

1. Nel dashboard accedere a**Bridge conferenza** **riunioni** > .
2. Selezionare il numero di telefono del Bridge di conferenza, fare clic su **modifica**e quindi scegliere la lingua predefinita.

![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **con l'interfaccia di amministrazione di Skype for business**:

1. **** > Accedere al**portale legacy**di interfaccia di amministrazione di **Office 365 Admin Center** > **Teams** > .
2. Selezionare **audioconferenza** > **Microsoft Bridge**. 
3. Selezionare il numero di telefono del Bridge di conferenza, selezionare **imposta lingue**e quindi scegliere la lingua predefinita.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Passo 6: Configurare le impostazioni del ponte per audioconferenza
<a name="__top"> </a>
    
Dopo aver impostato il ponte per audioconferenza, verifica che le impostazioni predefinite, ad esempio le notifiche di ingresso e di uscita e la lunghezza del PIN siano quelle desiderate; se non lo sono, è possibile modificarle. 

![Icona che mostra il logo](../images/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**:

1. Nel dashboard accedere a**Bridge conferenza** **riunioni** > .
2. Selezionare **Impostazioni Bridge**. Verrà visualizzato il riquadro **Impostazioni ponte**. 

Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **con l'interfaccia di amministrazione di Skype for business:**

1. **** > Accedere al**portale legacy**di interfaccia di amministrazione di **Microsoft 365 Admin Center** > **Teams** > .
2. Selezionare **** > **impostazioni di Microsoft Bridge**per audioconferenza. Verrà visualizzata la pagina **Impostazioni ponte Microsoft**. 

Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Passo 7: Assegnare i numeri di telefono con accesso esterno per gli utenti che conducono le riunioni

Dopo aver creato un ponte per Audioconferenza, è necessario impostare i numeri a pagamento e i numeri verdi per gli utenti.

È necessario eseguire questa operazione per tutti gli utenti dell'organizzazione che conducono o pianificano riunioni. 

![Icona che mostra il logo](../images/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**:

1. Nel dashboard fare clic su **utenti**, selezionare l'utente nell'elenco e quindi selezionare **modifica**.
2. Selezionare **modifica** accanto a servizi di **audioconferenza**e quindi nel riquadro **audioconferenza** scegliere un numero nell'elenco a **pagamento** e numero **verde** .

![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **con l'interfaccia di amministrazione di Skype for business:**

1. Accedere al**portale legacy**di **Microsoft 365 Admin Center** > **Teams** > .
2. Selezionare **** > **utenti**di servizi di audioconferenza e quindi selezionare l'utente nell'elenco e fare clic su **modifica**. 

Per ulteriori informazioni, consulta [Assegnare Microsoft come provider di servizi di audioconferenza](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Passo 8: Configurare gli inviti alla riunione (facoltativo)
<a name="__top"> </a>
 
I numeri di accesso esterno impostati per l'utente verranno aggiunti automaticamente agli inviti alla riunione inviati ai partecipanti alla riunione. È tuttavia possibile aggiungere una guida e collegamenti legali personalizzati, un messaggio di testo e un elemento grafico aziendale di piccole dimensioni, se si vuole. Vedere [personalizzare](../set-up-skype-for-business-online/customize-meeting-invitations.md)gli inviti alle riunioni.
   
## <a name="related-topics"></a>Argomenti correlati

[Domande ricorrenti sulle audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurare Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Numeri di telefono per i servizi di audioconferenza](phone-numbers-for-audio-conferencing.md)
  
[Impostare le opzioni per riunioni online e conferenze telefoniche](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
