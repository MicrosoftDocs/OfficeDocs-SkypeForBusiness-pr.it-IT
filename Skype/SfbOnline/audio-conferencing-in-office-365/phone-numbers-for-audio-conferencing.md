---
title: Phone numbers for Audio Conferencing
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: Learn what countries and regions have dial-in conferencing numbers, and how they are automatically assigned.
ms.openlocfilehash: 9b1fca6a576a9de77e74bcab8df740b5106cf5bc
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
---
# <a name="phone-numbers-for-audio-conferencing"></a>Phone numbers for Audio Conferencing

When you are setting up **Audio Conferencing** for Skype for Business and Microsoft Teams, dial-in phone numbers are automatically assigned to your organization. You can see the phone numbers that are assigned to your audio conferencing bridge by going to the **Skype for Business admin center** > **Audio conferencing** > **Microsoft bridge**. See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> Non esiste una risorsa che contenga un elenco di tutti i numeri con accesso esterno per Audioconferenza. If you want to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Utilizza gli elenchi per **paese/area geografica**, **stato/regione**, e **città** per filtrare la ricerca. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
## <a name="audio-conferencing-coverage-and-pricing"></a>Audio Conferencing coverage and pricing

For a complete list of all the countries/regions and cities where Audio Conferencing is available, see [Countries and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). For pricing information, see 
  
[Prezzi per le Audioconferenze](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>Numeri di telefono di accesso esterno nell'invito alla riunione

When a Skype for Business Online or Microsoft Teams user schedules a meeting in Outlook or Outlook Web App, the default audio conferencing number that is set for the user is included in the meeting invite. If you want to select a different default number for one or more users, you can change that by going to the **Skype for Business admin center** > **Audio conferencing** > **Users**. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
  
Puoi visualizzare gli altri numeri di accesso esterno facendo clic sul collegamento **Trova un numero locale** nell'invito alla riunione.
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>Dial-in phone numbers set on an audio conferencing bridge

There are two types of audio conferencing phone numbers that can be assigned to your conferencing bridge: **Shared** and **Dedicated**. Both types of these numbers can be used by any caller to join audio meetings that are being held in your organization.
  
 I **numeri di telefono dedicati** sono i numeri di telefono disponibili solo per gli utenti all'interno dell'organizzazione. Puoi modificare le lingue utilizzate quando un utente partecipa a una riunione tramite telefono chiamando uno di questi numeri.
  
 I **numeri di telefono condivisi** sono i numeri di telefono che possono essere condivisi con altre organizzazioni Office 365. Non puoi modificare le lingue utilizzate quando un utente partecipa a una riunione tramite telefono chiamando uno di questi numeri.
  
While the default audio conferencing number that is assigned to an organizer is only included in the meeting invite, a caller can use any of the phone numbers that are assigned to your conferencing bridge to join a meeting. L'elenco dei numeri utilizzabili per partecipare a una riunione tramite telefono viene visualizzato facendo clic sul collegamento **Trova un numero locale** incluso in ogni invito alla riunione.
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>Automatically assigned audio conferencing phone numbers

Shared audio conferencing phone numbers are automatically assigned to organizations when they're enabled for audio conferencing. Il numero di telefono assegnato viene impostato come numero predefinito per il bridge di conferenza telefonica. Il numero di telefono impostato come numero predefinito del bridge appartiene al paese/area geografica dell'organizzazione.
  
> [!NOTE]
> The country or region location of your organization can be found by signing in to the **Office 365 admin center** and looking under **Organization Profile**. 
  
> [!CAUTION]
> Due to limited availability of toll phone numbers in Venezuela, Indonesia, and United Arab Emirates (UAE), organizations from these countries/regions won't have an Audio Conferencing toll number automatically assigned to them. I numeri verdi di queste località sono offerti in base alla disponibilità. 
  
Dedicated audio conferencing phone numbers are service numbers that you can get and then assign to your organization. Service numbers can be found by using the **Skype for Business admin center**. For details, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
  
To see a list of those countries/regions that have phone numbers automatically assigned to organizations, see [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).
  
## <a name="what-else-should-you-know"></a>Quali altre informazioni devi conoscere?

- To see the list of supported languages for audio conferencing, see [Audio Conferencing supported languages](audio-conferencing-supported-languages.md).
    
- You can use the [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) cmdlet to see the dedicated phone numbers for audio conferencing for you organization.
    
- Puoi utilizzare il cmdlet [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) per visualizzare le lingue che possono essere configurate per un numero di telefono di accesso esterno dedicato.
    
- You can set up to 4 languages for each audio conferencing phone number - one primary and three secondary. And you can also set languages on a dedicated audio conferencing phone number.
    
- To set the dial-in phone number for a user, see [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>See also

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
