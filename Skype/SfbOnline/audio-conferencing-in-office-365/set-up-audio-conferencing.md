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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: "Informazioni su come configurare servizi di conferenza telefonica o audio per le persone nell'azienda che desiderano partecipare a conferenze telefoniche mediante un telefono. "
ms.openlocfilehash: 5d069822bf818db63ed35545a34a0bfa2eeee672
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562669"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurare le audioconferenze per Skype for Business e Microsoft Teams

Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Per le domande frequenti sui servizi di audioconferenza, vedere [Domande frequenti su Audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Passo 1: Verificare se l'Audioconferenza è disponibile nel tuo Paese o nella tua area geografica
<a name="__top"> </a>


Vai a [Disponibilità di audioconferenza e Piani di chiamata per Paese e area geografica](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e seleziona il Paese o l'area geografica per ottenere informazioni sulla disponibilità del servizio di Audioconferenza, nonché informazioni relative a Sistema telefonico, Piani di chiamata, numeri a pagamento e numeri verdi, e Credito per la comunicazione. 
 
## <a name="step-2-get-and-assign-licenses"></a>Passo 2: Ottenere e assegnare licenze
 
1. For Audio Conferencing, you need a license for each user who will set up dial-in meetings. To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.
    
3. We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step. To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> You can also set up pay-per-minute Audio Conferencing. Go [here](/microsoftteams/audio-conferencing-pay-per-minute) to find out more about how to use them.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Passo 3: Ottenere i numeri di servizio per i ponti per audioconferenza
<a name="__top"> </a>

For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers. You can get either toll or toll-free service numbers for your conferencing bridges. There are three ways to get toll and toll-free service numbers: 
  
- **Use the Skype for Business admin center.** For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Port your existing service numbers.** To port or transfer existing numbers from your current service provider or phone carrier to Office 365. You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.  
  
- **Use a request form for new numbers.** Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes. If so, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information. 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Passo 4: Assegnare un numero di servizio al ponte per audioconferenza
<a name="__top"> </a>

Una volta ottenuti i numeri a pagamento e i numeri verdi per il ponte per audioconferenza, è necessario assegnarli in modo che possano essere utilizzati per gli inviti alla riunione.  

Per assegnare un nuovo numero di telefono per il ponte per audioconferenza:

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**

 Vai al **Centro di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **vocale** > **i numeri di telefono**, selezionare il numero di telefono e fare clic su **Assegna**.

Per ulteriori informazioni, vedere [modificare i numeri di telefono del ponte per conferenze audio](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Passo 5: Impostare le lingue predefinite e alternative per un ponte per audioconferenza
<a name="__top"> </a>

Si desidera [impostare le lingue di operatore automatico per le conferenze Audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) che utilizza l'operatore automatico di servizi di conferenza per saluti salutare un chiamante quando si effettua la chiamata a un numero di telefono per le audioconferenze. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utilizzo di Microsoft Teams e dell'Interfaccia di amministrazione di Skype for Business:**

Dal Dashboard, vai su **Riunioni** > **Ponti per audioconferenza**, seleziona il numero di telefono del ponte per audiconferenza, fai clic su **Modifica**, quindi fai clic sulla lingua predefinita.

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**

Vai al **Centro di amministrazione di Office 365** > **Admin Center** > **Skype per le aziende** > **audioconferenze** > **bridging Microsoft**, selezionare il numero di telefono di ponte conferenza e quindi fare clic su ** Impostare lingue**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Passo 6: Configurare le impostazioni del ponte per audioconferenza
<a name="__top"> </a>
    
Dopo aver impostato il ponte per audioconferenza, verifica che le impostazioni predefinite, ad esempio le notifiche di ingresso e di uscita e la lunghezza del PIN siano quelle desiderate; se non lo sono, è possibile modificarle. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utilizzo di Microsoft Teams e dell'Interfaccia di amministrazione di Skype for Business:**

From the Dashboard, go to **Meetings** > **Conference bridges** > **Bridge settings**. This will open the **Bridge settings** pane. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**

Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**. This will open the **Microsoft bridge settings** page. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Passo 7: Assegnare i numeri di telefono con accesso esterno per gli utenti che conducono le riunioni

Dopo aver creato un ponte per Audioconferenza, è necessario impostare i numeri a pagamento e i numeri verdi per gli utenti.

You will need to do this for all of the people in your organization who lead or schedule meetings. To do this:

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utilizzo di Microsoft Teams e dell'Interfaccia di amministrazione di Skype for Business:**

Dal Dashboard, fai clic su **Utenti**, seleziona l'utente dall'elenco, fai clic su **Modifica**, fai clic su **Modifica** accanto a **Audioconferenza**, quindi nel riquadro **Audioconferenza**, seleziona un numero nelle liste **Numero a pagamento** e **Numero verde**.

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **con la Skype per Business admin center:**

Go to the **Office 365 admin center** > **Skype for Business** > **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**. If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Passo 8: Configurare gli inviti alla riunione (facoltativo)
<a name="__top"> </a>
 
The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees. However, you can add your own help and legal links, a text message, and small company graphic if you want. See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Argomenti correlati

[Domande ricorrenti sulle audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Numeri di telefono per i servizi di audioconferenza](phone-numbers-for-audio-conferencing.md)
  
[Impostare le opzioni per riunioni online e conferenze telefoniche](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
