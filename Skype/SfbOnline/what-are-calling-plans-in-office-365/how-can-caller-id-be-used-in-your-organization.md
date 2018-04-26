---
title: Come ID chiamante utilizzare all'interno dell'organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
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
- Calling Plans
- Strat_SB_PSTN
description: ID chiamante può essere controllato per le chiamate in ingresso e in uscita per gli utenti di sistema telefonico utilizzando un criterio denominato CallingLineIdentity.
ms.openlocfilehash: 4dc596e8301310f2c229c46add5795e72c432daf
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Come ID chiamante utilizzare all'interno dell'organizzazione

ID chiamante può essere controllato per le chiamate in ingresso e in uscita per gli utenti di sistema telefonico utilizzando un criterio denominato CallingLineIdentity.
  
La funzionalità ID chiamante è disponibile per tutti gli utenti di sistema telefonico indipendentemente dalla connettività PSTN:
  
- Connettività PSTN in linea
    
- Connettività PSTN locale con Skype per Business Cloud connettore Edition (richiede Cloud connettore Edition 1.4.2 e versioni successive)
    
- Connettività PSTN locale con Skype per Business Server (è richiesto Skype per Business Server 2015 CU5 e versioni successive)
    
> [!NOTE]
> Questo criterio non è disponibile in Skype per Business 2015 Server. 
  
## <a name="outbound-caller-id"></a>ID chiamante in uscita

Sono disponibili tre opzioni per l'ID chiamante PSTN in uscita:
  
- Numero di telefono assegnato all'utente, ovvero il valore predefinito.
    
- Inventario dei numeri di un numero di telefono che verrà classificato come un *servizio* e il *numero verde* numero nei piani di chiamata in Office 365 telefono. In genere assegnata a una coda di chiamata o operatore automatico dell'organizzazione.
    
- Impostare su anonimo.
    
Tuttavia, è possibile assegnare questi tipi di numeri di telefono per l'ID chiamante in uscita:
  
- Inventario dei numeri dei numeri di telefono che classificati come *utente* nel proprio telefono tariffe di chiamate
    
- Skype per numero di telefono locale Business Server
    
Per impostare l'ID chiamante in uscita, vedere [impostazione dell'ID chiamante per un utente](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Controllo degli utenti finali dell'ID chiamante in uscita

L'attributo EnableUserOverride consente agli utenti di un o più modificare le impostazioni di ID chiamante su **anonimo**. Ciò è valido solo quando viene configurato un criterio CallingLineIdentity con un parametro CallingIDSubstitute LineURI o sostituto. Il valore predefinito di EnableUserOverride è False.
  
Gli utenti finali possono impostare ID chiamante su **anonimo** utilizzando la scheda **Chiama impostazioni** nel Skype per client desktop aziendali.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versione** <br/> |**È supportata** <br/> |
|A portata di clic  <br/> |Canale corrente su 6 dicembre 2016 - versione completa 1611 (Build 7571.2072)  <br/> |Sì  <br/> |
|A portata di clic  <br/> |Prima versione per il canale rinviata rilasciato il 22 febbraio 2017 - versione 1701 (Build 7766.2060)  <br/> |Sì  <br/> |
|A portata di clic  <br/> |Rinviato canale rilasciato il 13 giugno 2017 - versione 1701 (Build 7766.2092)  <br/> |Sì  <br/> |
|MSI  <br/> |Skype per le aziende  <br/> |No  <br/> |
|Mac  <br/> |Skype per le aziende  <br/> |No  <br/> |
   
## <a name="inbound-caller-id"></a>ID chiamante in ingresso

L'attributo BlockIncomingCallerID consente di bloccare l'ID chiamante nelle chiamate PSTN in arrivo. È possibile impostare questo attributo, ma non è disponibile per gli utenti finali nella pagina Impostazioni utente. Ed è attualmente disponibile solo con connettività PSTN in linea.
  
Per impostare l'ID chiamante in uscita, vedere [impostazione dell'ID chiamante per un utente](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](transferring-phone-numbers-common-questions.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termini e condizioni per le chiamate al numero di emergenza](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 