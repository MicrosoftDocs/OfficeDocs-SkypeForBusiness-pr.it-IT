---
title: Numeri di telefono per Audioconferenza su Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7
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
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: Informazioni su quali Paesi e aree possiedono numeri telefonici di accesso esterno e come vengono assegnati automaticamente.
ms.openlocfilehash: feaa7972766ffeb21517080e97ee67dcd597edb4
ms.sourcegitcommit: 7d85a6784a21aec20dcaddd8940ffe95d532c2f4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2019
ms.locfileid: "35134253"
---
# <a name="phone-numbers-for-audio-conferencing-in-skype-for-business-online"></a>Numeri di telefono per Audioconferenza su Skype for Business online

> [!NOTE]
> Per informazioni sui numeri di telefono in Microsoft Teams, consulta [Numeri di telefono per Audioconferenza su Microsoft Teams](/MicrosoftTeams/phone-numbers-for-audio-conferencing-in-teams).

When you are setting up **Audio Conferencing** for Skype for Business, dial-in phone numbers are automatically assigned to your organization. You can see the phone numbers that are assigned to your audio conferencing bridge by going to the **Skype for Business admin center** > **Audio conferencing** > **Microsoft bridge**. See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you want to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Use the lists for **Country/Region**, **State/Region**, and **City** to filter your search. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
## <a name="audio-conferencing-coverage-and-pricing"></a>Copertura e prezzi per Audioconferenza

For a complete list of all the countries/regions and cities where Audio Conferencing is available, see [Countries and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans). For pricing information, see [Pricing for Audio Conferencing](https://products.office.com/it-IT/skype-for-business/audio-conferencing#Requirements).
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>Numeri di telefono con accesso esterno nell’invito alla riunione

When a Skype for Business Online user schedules a meeting in Outlook or Outlook Web App, the default audio conferencing number that is set for the user is included in the meeting invite. If you want to select a different default number for one or more users, you can change that by going to the **Skype for Business admin center** > **Audio conferencing** > **Users**. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
  
È possibile visualizzare altri numeri con accesso esterno facendo clic sul collegamento **Trova un numero locale** nell'invito alla riunione.
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>Numeri con accesso esterno impostati in un bridge per i servizi di audioconferenza

There are two types of audio conferencing phone numbers that can be assigned to your conferencing bridge: **Shared** and **Dedicated**. Both types of these numbers can be used by any caller to join audio meetings that are being held in your organization.
  
 I **numeri di telefono dedicati** sono i numeri di telefono disponibili solo per gli utenti all'interno dell'organizzazione. Puoi modificare le lingue utilizzate quando un utente partecipa a una riunione tramite telefono chiamando uno di questi numeri.
  
 I **numeri di telefono condivisi** sono i numeri di telefono che possono essere condivisi con altre organizzazioni Office 365. Non puoi modificare le lingue utilizzate quando un utente partecipa a una riunione tramite telefono chiamando uno di questi numeri.
  
While the default audio conferencing number that is assigned to an organizer is only included in the meeting invite, a caller can use any of the phone numbers that are assigned to your conferencing bridge to join a meeting. The list of phone numbers that can be used to join a meeting is available using the **Find a local number** link that is included on every meeting invite.
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>Assegnare automaticamente numeri di telefono per i servizi di audioconferenza

Shared audio conferencing phone numbers are automatically assigned to organizations when they're enabled for audio conferencing. When the phone numbers are assigned, a phone number is assigned as the default phone number of the conferencing bridge. The phone number assigned as the default number of the bridge will be one from the country/region of the organization.
  
> [!NOTE]
> Il paese o l'area geografica dell'organizzazione è disponibile accedendo all'**interfaccia di amministrazione di Office 365** e controllando in **Profilo organizzazione**. 
  
> [!CAUTION]
> A causa della disponibilità limitata di numeri di telefono a pagamento in Venezuela, Indonesia, Vietnam e Emirati Arabi Uniti (UAE), le organizzazioni di tali paesi o aree geografiche non dispongono di un numero a pagamento per la conferenza telefonica assegnato automaticamente. I numeri gratuiti in queste località sono disponibili a seconda dell’inventario. 
  
Dedicated audio conferencing phone numbers are service numbers that you can get and then assign to your organization. Service numbers can be found by using the **Skype for Business admin center**. For details, see [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).
  
Per visualizzare un elenco di Paesi/aree geografiche che hanno numeri di telefono automaticamente assegnati per le organizzazioni, consulta [Disponibilità per Paese e area geografica per Audioconferenza e Piani di chiamata](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).
  
## <a name="what-else-should-you-know"></a>Informazioni aggiuntive

- Per visualizzare l'elenco delle lingue supportate per l’audioconferenza, consulta [Lingue supportate per audioconferenza](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Puoi usare il cmdlet [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) per visualizzare i numeri di telefono dedicati per i servizi di audioconferenza per l'organizzazione.
    
- È possibile usare il cmdlet [Get- CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) per visualizzare le lingue disponibili per il numero di telefono con accesso esterno dedicato.
    
- You can set up to four languages for each audio conferencing phone number - one primary and three secondary. And you can also set languages on a dedicated audio conferencing phone number.
    
- Per impostare il numero di telefono con accesso esterno, vedere [Impostare i numeri di telefono inclusi negli inviti.](set-the-phone-numbers-included-on-invites.md)
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
