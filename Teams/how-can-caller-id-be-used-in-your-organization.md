---
title: Come usare l'ID chiamante nella tua organizzazione
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: L'ID chiamante può essere controllato sia per le chiamate in ingresso che per quelle in uscita per gli utenti di Sistema telefonico utilizzando un criterio denominato CallingLineIdentity.
ms.openlocfilehash: c0cd798f7aaed3b513db9d74fc52d458b9d17078
ms.sourcegitcommit: bf7de2101862a154eb375c06bc89e6e0c4872119
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2019
ms.locfileid: "36183541"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Come usare l'ID chiamante nella tua organizzazione

L'ID chiamante può essere controllato sia per le chiamate in ingresso che per quelle in uscita per gli utenti di Sistema telefonico utilizzando un criterio denominato CallingLineIdentity.
  
La funzionalità ID chiamante è disponibile per tutti gli utenti di Sistema telefonico indipendentemente dalla connettività PSTN:
  
- Connettività PSTN in linea
    
- Connettività PSTN locale con Skype for Businesss Cloud Connector Edition (richiede Cloud Connector Edition 1.4.2 e versioni successive)
    
- Connettività PSTN locale con Skype for Businesss Server (richiede Skype for Businesss Server 2015 CU5 e versioni successive)
    
> [!NOTE]
> Questo criterio non è disponibile in Skype for Businesss 2015 Server. 
  
## <a name="outbound-caller-id"></a>ID chiamante in uscita

Sono disponibili tre opzioni per l'ID chiamante PSTN in uscita:
  
- Numero di telefono assegnato all'utente, ovvero l'impostazione predefinita.
    
- A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.
    
- Impostato su anonimo.
    
Tuttavia, non è possibile assegnare questi tipi di numeri di telefono per l'ID chiamante in uscita:
  
- I numeri di telefono classificati come *utente* nella rubrica telefonica dei tuoi Piani chiamata
    
- Un numero di telefono Skype for Businesss Server locale
    
Per impostare l'ID chiamante in uscita, vedere [Impostazione dell'ID chiamante per gli utenti](/microsoftteams/set-the-caller-id-for-a-user).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Controllo degli utenti finali dell'ID chiamante in uscita

The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.
  
Gli utenti finali possono impostare l'ID chiamante su **Anonimo** usando la scheda **Impostazioni** nel client desktop Skype for business, selezionare **chiama un utente finale** (se abilitato dall'amministratore), selezionare Nascondi il **numero di telefono e le informazioni del profilo per tutte le chiamate **.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versione** <br/> |**Supportati** <br/> |
|A portata di clic  <br/> |Current Channel rilasciato il 6 dicembre 2016 - versione 1611 (Build 7571.2072)  <br/> |Sì  <br/> |
|A portata di clic  <br/> |Prima versione per Deferred Channel rilasciata il 22 febbraio 2017 - versione 1701 (Build 7766.2060)  <br/> |Sì  <br/> |
|A portata di clic  <br/> |Deferred Channel rilasciato il 13 giugno 2017 - versione 1701 (Build 7766.2092)  <br/> |Sì  <br/> |
|MSI  <br/> |Skype for business  <br/> |No  <br/> |
|Mac  <br/> |Skype for business  <br/> |No  <br/> |
   
## <a name="inbound-caller-id"></a>ID chiamante in ingresso

The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls. You can set this attribute, but it isn't available to your end users on the user settings page. And it is currently available only with Online PSTN connectivity.
  
Per impostare l'ID chiamante in uscita, vedere [Impostazione dell'ID chiamante per gli utenti](/microsoftteams/set-the-caller-id-for-a-user).
  
## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
