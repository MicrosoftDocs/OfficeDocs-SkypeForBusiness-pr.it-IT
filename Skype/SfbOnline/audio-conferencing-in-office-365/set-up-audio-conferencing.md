---
title: Configurare Audioconferenza per Skype for Business e Microsoft Teams
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
description: "Impara come configurare servizi di conferenza con accesso esterno o di audioconferenza per le persone nell'azienda che desiderano partecipare a conferenze usando un telefono. "
ms.openlocfilehash: 02c04afa0a1079a53123ee56094dc6ddc764038c
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780532"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurare Audioconferenza per Skype for Business e Microsoft Teams

A volte gli utenti della propria organizzazione devono utilizzare un telefono per accedere a una riunione. Skype for Business e Microsoft Teams offrono la funzione di Audioconferenza proprio per queste evenienze! Le persone possono partecipare a una riunione Skype for Business o Microsoft Teams mediante un telefono, anziché utilizzare l'app Skype for Business o Microsoft Teams su un dispositivo mobile o PC. 
  
È sufficiente configurare il servizio di Audioconferenza per gli utenti che prevedono di pianificare o condurre riunioni. Le persone che partecipano alla riunione tramite telefono non hanno bisogno di altre impostazioni o che venga loro assegnata alcuna licenza.
  
Per le domande frequenti sui servizi di Audioconferenza, consulta [Domande frequenti su Audioconferenza](/MicrosoftTeams/audio-conferencing-common-questions).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Passo 1: Verificare se l'Audioconferenza è disponibile nel tuo Paese o nella tua area geografica
<a name="__top"> </a>


Vai a [Disponibilità di audioconferenza e Piani di chiamata per Paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e seleziona il Paese o l'area geografica per ottenere informazioni sulla disponibilità del servizio di Audioconferenza, nonché informazioni relative a Sistema telefonico, Piani di chiamata, numeri a pagamento e numeri verdi, e Credito per la comunicazione. 
 
## <a name="step-2-get-and-assign-licenses"></a>Passo 2: Ottenere e assegnare licenze
 
1. Per l'Audioconferenza, è necessaria una licenza per ogni utente che configurerà le riunioni con accesso esterno. Per informazioni su quali licenze è necessario acquistare per l'Audioconferenza e sui relativi costi, consulta [Licenze per i componenti aggiuntivi di Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. Dopo aver acquistato le licenze per Audioconferenza, è necessario assegnarle agli utenti dell'organizzazione che desiderano pianificare o condurre riunioni. Consulta come [Assegnare o rimuovere licenze di Office 365 per aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) che hai acquistato per gli utenti dell'organizzazione che intendono pianificare o condurre riunioni.
    
3. È inoltre consigliabile assegnare licenze di Credito per la comunicazione (non costano nulla) agli stessi utenti a cui sono state assegnate le licenze nel passo precedente. Per informazioni su come configurare il Credito per la comunicazione, consulta [Configurare il Credito per la comunicazione per la propria organizzazione](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> È inoltre possibile configurare un'Audioconferenza con tariffa al minuto. Andare [qui](/microsoftteams/audio-conferencing-pay-per-minute) per ulteriori informazioni su come utilizzarle.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Passo 3: Ottenere i numeri di servizio per i ponti per audioconferenza
<a name="__top"> </a>

Non è possibile utilizzare numeri di telefono per gli utenti per l'Audioconferenza. È necessario ottenere numeri di servizio. Per i ponti per audioconferenza è possibile ottenere numeri di servizio a pagamento o numeri verdi. Esistono tre modi per ottenere numeri di servizio a pagamento o numeri verdi: 
  
- **Usare l'interfaccia di amministrazione di Skype for Business.** Per alcuni Paesi e aree geografiche, è possibile ottenere i numeri di servizio per i ponti per audioconferenza usando l'Interfaccia di amministrazione di Skype for Business, consultando [Ottenere numeri di telefono di servizio](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Sfruttare la portabilità dei numeri di servizio esistenti.** Trasferire i numeri di telefono esistenti dal service provider o gestore telefonico attuali a Office 365. Per ulteriori informazioni su come eseguire questa operazione, è possibile consultare [Trasferire numeri di telefono in Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) o [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization).  
  
- **Utilizzare un modulo di richiesta per nuovi numeri.** A volte (a seconda del Paese o dell'area geografica) non sarà possibile ottenere nuovi numeri tramite l'Interfaccia di amministrazione di Skype for Business, oppure serviranno numeri di telefono o prefissi specifici. In questo caso, sarà necessario scaricare un modulo e inviarcelo. Per ulteriori informazioni, consulta [Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Passo 4: Assegnare un numero di servizio al ponte per audioconferenza
<a name="__top"> </a>

Una volta ottenuti i numeri a pagamento e i numeri verdi per il ponte per audioconferenza, è necessario assegnarli in modo che possano essere utilizzati per gli inviti alla riunione.  

Per assegnare un nuovo numero di telefono per il ponte per audioconferenza:

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilizzo dell'Interfaccia di amministrazione di Skype for Business**

 Vai su **Interfaccia di amministrazione di Office 365** > **Interfacce di amministrazione** > **Skype for Business** > **Voce** > **Numeri di telefono**, seleziona il numero di telefono e fai clic su **Assegna**.

Per ulteriori informazioni, consulta [Cambiare i numeri di telefono del ponte per audioconferenza](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Passo 5: Impostare le lingue predefinite e alternative per un ponte per audioconferenza
<a name="__top"> </a>

Successivamente è possibile [Impostare le lingue di operatore automatico per Audioconferenza](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md), che l'operatore automatico utilizza per ricevere un chiamante quando questi chiama da un numero di telefono per Audioconferenza. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utilizzo di Microsoft Teams e dell'Interfaccia di amministrazione di Skype for Business:**

Dal Dashboard, vai su **Riunioni** > **Ponti per audioconferenza**, seleziona il numero di telefono del ponte per audiconferenza, fai clic su **Modifica**, quindi fai clic sulla lingua predefinita.

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilizzo dell'Interfaccia di amministrazione di Skype for Business**

Vai su **Interfaccia di amministrazione di Office 365** > **Interfacce di amministrazione** > **Skype for Business** > **Audioconferenza** > **Impostazioni ponte Microsoft**, seleziona il numero di telefono del ponte per audioconferenza e quindi fai clic su **Imposta lingue**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Passo 6: Configurare le impostazioni del ponte per audioconferenza
<a name="__top"> </a>
    
Dopo aver impostato il ponte per audioconferenza, verifica che le impostazioni predefinite, ad esempio le notifiche di ingresso e di uscita e la lunghezza del PIN siano quelle desiderate; se non lo sono, è possibile modificarle. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utilizzo di Microsoft Teams e dell'Interfaccia di amministrazione di Skype for Business:**

Dal Dashboard, vai su **Riunioni** > **Ponti per conferenza** > **Impostazioni ponte**. Verrà visualizzato il riquadro **Impostazioni ponte**. Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilizzo dell'Interfaccia di amministrazione di Skype for Business**

Vai su **Interfaccia di amministrazione di Office 365** > **Interfacce di amministrazione** > **Skype for Business** > **Audioconferenza** > **Impostazioni ponte Microsoft**. Verrà visualizzata la pagina **Impostazioni ponte Microsoft**. Per ulteriori informazioni, consulta [Modificare le impostazioni per un ponte per Audioconferenza](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Passo 7: Assegnare i numeri di telefono con accesso esterno per gli utenti che conducono le riunioni

Dopo aver creato un ponte per Audioconferenza, è necessario impostare i numeri a pagamento e i numeri verdi per gli utenti.

È necessario eseguire questa operazione per tutti gli utenti dell'organizzazione che conducono o pianificano riunioni. Come fare:

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utilizzo di Microsoft Teams e dell'Interfaccia di amministrazione di Skype for Business:**

Dal Dashboard, fai clic su **Utenti**, seleziona l'utente dall'elenco, fai clic su **Modifica**, fai clic su **Modifica** accanto a **Audioconferenza**, quindi nel riquadro **Audioconferenza**, seleziona un numero nelle liste **Numero a pagamento** e **Numero verde**.

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilizzo dell'Interfaccia di amministrazione di Skype for Business**

Vai su **Interfaccia di amministrazione di Office 365** > **Skype for Business** > **Audioconferenza** > **Utenti**, quindi seleziona l'utente dall'elenco e fai clic su **Modifica**. Per ulteriori informazioni, consulta [Assegnare Microsoft come provider di servizi di audioconferenza](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Passo 8: Configurare gli inviti alla riunione (facoltativo)
<a name="__top"> </a>
 
I numeri con accesso esterno impostati per l'utente verranno aggiunti automaticamente agli inviti alla riunione inviati ai partecipanti. Tuttavia, è possibile aggiungere una guida o collegamenti legali personalizzati, un messaggio di testo e una piccola immagine aziendale, se si desidera. Consulta come [Personalizzare gli inviti alle riunioni](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Argomenti correlati

[Domande ricorrenti sull'Audioconferenza](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Numeri di telefono per Audioconferenza](phone-numbers-for-audio-conferencing.md)
  
[Impostare le opzioni per riunioni online e conferenze telefoniche](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
