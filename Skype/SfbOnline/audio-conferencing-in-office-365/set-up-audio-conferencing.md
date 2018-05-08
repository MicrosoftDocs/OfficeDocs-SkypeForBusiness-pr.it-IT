---
title: Configurare le audioconferenze per Skype for Business e Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: "Informazioni su come configurare servizi di conferenza telefonica o audio per le persone nell'azienda che desiderano partecipare a conferenze telefoniche mediante un telefono. "
ms.openlocfilehash: 303b22f43a756fcade575dd63ae9bba205e6cbda
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurare le audioconferenze per Skype for Business e Microsoft Teams

A volte le persone all’interno dell'organizzazione devono utilizzare un telefono per accedere a una riunione. Skype per le aziende e Teams Microsoft includono la funzionalità di audioconferenza per solo questa situazione! Le persone possono chiamare Skype per le riunioni aziendali o Microsoft Teams mediante un telefono, anziché utilizzare il Skype per applicazioni aziendali o Microsoft Teams su un dispositivo mobile o PC. 
  
È sufficiente configurare conferenze Audio per gli utenti che prevedono di programmare o condurre riunioni. I partecipanti alla riunione che effettua la chiamata non è necessario alcun licenze assegnate loro o altre impostazioni.
  
Per le domande frequenti sui servizi di conferenza Audio, vedere [domande frequenti di conferenze Audio](audio-conferencing-common-questions.md).
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Passaggio 1: Scoprire se l'audioconferenza è disponibile nel paese/area geografica
<a name="__top"> </a>


Passare alla [disponibilità paese e alle aree per le conferenze Audio e la chiamata a piani](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e selezionare il paese o l'area per ottenere informazioni sulla disponibilità sui servizi di conferenza Audio, nonché informazioni relative a pagamento sistema telefonico, la chiamata a piani e numero verde i numeri e titoli di coda di comunicazioni. 
 
## <a name="step-2-get-and-assign-licenses"></a>Passaggio 2: Ottenere e assegnare licenze
 
1. Per le conferenze Audio, è necessaria una licenza per ogni utente verrà impostare dial-in riunioni. Per ulteriori le licenze che è necessario acquistare per le conferenze Audio e il relativo verrà costo, vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. Dopo che acquistare le licenze di conferenze Audio, si verrà ned per assegnarli a tali persone all'interno dell'organizzazione che desiderano programmare o condurre riunioni. Vedere [assegnare o rimuovere licenze per Office 365 per aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) è stato acquistato per gli utenti dell'organizzazione che intende pianificazione o lead riunioni.
    
3. È inoltre consigliabile da assegnazione licenze crediti Communications (che non alcun costo) agli utenti stessi è assegnate licenze per il passaggio precedente. Per informazioni su come impostare i titoli di coda di comunicazioni, vedere [impostare i titoli di coda di comunicazione per l'organizzazione](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> È inoltre possibile impostare conferenze Audio retribuzione al minuto. Andare [qui](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md) per ulteriori informazioni su come utilizzarle.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Passaggio 3: Ottenere i numeri di servizio per i ponti di audioconferenze
<a name="__top"> </a>

Per le conferenze Audio, è possibile utilizzare i numeri di telefono per gli utenti. è necessario ottenere numeri di servizio. È possibile ottenere tariffe o numeri verdi assistenza per i ponti di audioconferenze. Esistono tre modi per get a pagamento e numeri verdi servizio: 
  
- **Utilizzare il Skype per l'interfaccia di amministrazione di Business.** Per alcuni paesi, è possibile ottenere numeri di servizio per i ponti di audioconferenze con il Skype per interfaccia di amministrazione di Business, vedere [Getting numeri di telefono del servizio](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Porte i numeri di servizio esistente.** In porta o trasferimento esistenti numeri dal provider di servizi corrente o gestore telefonico per Office 365. È possibile visualizzare [trasferire i numeri di telefono a Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) o [numeri di telefono di gestione dell'organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per ulteriori informazioni che consentono di eseguire questa operazione.  
  
- **Utilizzare un modulo di richiesta per nuovi numeri.** In alcuni casi (a seconda del paese/area geografica) non sarà in grado di ottenere i nuovi numeri servizio con il Skype per interfaccia di amministrazione di Business o sarà necessario area codici o i numeri di telefono specifico. In questo caso, dovrai scaricare un modulo e inviarcelo. Per ulteriori informazioni, vedere [Manage i numeri di telefono per l'organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) . 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Passaggio 4: Assegnare un numero di servizio di ponte per conferenze
<a name="__top"> </a>

Una volta che viene visualizzato il numero a tariffa e/o numeri verdi per i bridge conferenza, è necessario assegnare i numeri in modo che possono essere utilizzati in inviti della riunione.  

Per assegnare un nuovo numero di telefono per il ponte per conferenze audio, visitare il **Centro di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **vocale** > **i numeri di telefono**, selezionare il telefono numero e fare clic su **Assegna**.

Per ulteriori informazioni, vedere [assegnare un nuovo numero di telefono per il ponte per conferenze audio](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Passaggio 5: Impostare i criteri predefiniti e lingue alternative per un ponte per conferenze
<a name="__top"> </a>

Si desidera [impostare le lingue di operatore automatico per le conferenze Audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) che utilizza l'operatore automatico di servizi di conferenza per saluti salutare un chiamante quando si effettua la chiamata a un numero di telefono per le audioconferenze. 

Vai al **Centro di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **audioconferenze** > **Impostazioni bridge Microsoft**, selezionare il numero di telefono di ponte per conferenze e quindi Fare clic su **Imposta lingue**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Passaggio 6: Le impostazioni delle conferenze bridge
<a name="__top"> </a>
    
Dopo aver impostato i bridge conferenza, verificare che le impostazioni predefinite, ad esempio lunghezza del PIN e le notifiche di ingresso/uscita siano quelle che si desidera utilizzare; Se non si trovino, è possibile modificarli. 

Consente di passare all' **interfaccia di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **audioconferenze** > **Impostazioni bridge di Microsoft**. Verrà aperta la pagina **impostazioni di bridge di Microsoft** . Per ulteriori informazioni, vedere [modificare le impostazioni per un ponte per conferenze Audio](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-the-audio-conferencing-provider-and-dial-in-phone-numbers"></a>Passaggio 7: Assegnare i numeri di telefono provider dial-in e audioconferenze con accesso esterno

È necessario assicurarsi che Microsoft viene assegnato come provider e impostare il numero a pagamento e numeri verdi per tali contemporaneamente.

Assegnare agli utenti dell'organizzazione che condurre o pianificare riunioni accedendo **all'interfaccia di amministrazione di Office 365**Microsoft come provider > **Skype per le aziende** > **audioconferenze** > **utenti**e quindi selezionare l'utente dall'elenco e fare clic su **Modifica**. Se sono necessarie ulteriori informazioni, vedere [Microsoft assegnare come provider di servizi di conferenza audio](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).

Quando si imposta il provider, è inoltre possibile impostare il numero a tariffa e numeri verdi che verranno aggiunto alla riunione invia un invito di quell'utente. Selezionare semplicemente i numeri di telefono dall'elenco a discesa. Per ulteriori informazioni, vedere [impostare telefono numeri incluso nel invita](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md). 


## <a name="step-8-set-up-meeting-invitations-optional"></a>Passaggio 8: Configurazione di convocazioni di riunione (facoltativo)
<a name="__top"> </a>
 
I numeri di accesso impostate per l'utente verranno aggiunta automaticamente per gli inviti alle riunioni inviati ai partecipanti alla riunione. Tuttavia, è possibile aggiungere Guida personalizzata e collegamenti legali, un messaggio di testo e immagine piccola società se si desidera. Vedere [Personalizza convocazioni di riunione](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>See also

[Domande ricorrenti sulle audioconferenze](audio-conferencing-common-questions.md)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Numeri di telefono per i servizi di audioconferenza](phone-numbers-for-audio-conferencing.md)
  
[Impostare le opzioni per riunioni online e conferenze telefoniche](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
