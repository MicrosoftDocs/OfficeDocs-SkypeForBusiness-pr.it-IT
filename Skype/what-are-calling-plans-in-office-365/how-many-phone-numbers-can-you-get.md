---
title: "Quanti numeri di telefono è possibile ottenere."
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Quando si cerca e Guida i numeri di telefono per l'organizzazione, è possibile ottenere ulteriori numeri di telefono che si svolgono le licenze. Ma dipende dai tipi di numeri di telefono e i tipi di licenze di aver acquistato e assegnato. È possibile fare clic su tipi diversi di numeri di telefono utilizzati per la chiamata dei piani per conoscere i numeri di telefono diverso che vengono utilizzati in Skype Business online."
ms.openlocfilehash: 30a144bef07d7f91f297155cfb969337df6a703d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="how-many-phone-numbers-can-you-get"></a>Quanti numeri di telefono è possibile ottenere.

Quando si cerca e Guida i numeri di telefono per l'organizzazione, è possibile ottenere ulteriori numeri di telefono che si svolgono le licenze. Ma dipende dai tipi di numeri di telefono e i tipi di licenze di aver acquistato e assegnato. È possibile fare clic su [tipi diversi di numeri di telefono utilizzati per la chiamata dei piani](different-kinds-of-phone-numbers-used-for-calling-plans.md) per conoscere i numeri di telefono diverso che vengono utilizzati in Skype Business online.
  
È possibile visualizzare il numero dei numeri di telefono che è possibile ottenere la pagina di **numeri di telefono** nel Skype per interfaccia di amministrazione di Business oppure è possibile eseguire il cmdlet [Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/en-us/library/mt634605.aspx) .
  
> [!IMPORTANT]
> I limiti seguenti non includono i numeri di telefono trasferiti su Microsoft. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>Quanti numeri di telefono è possibile ottenere?

||||
|:-----|:-----|:-----|
|**Ecco il tipo di numero di telefono** <br/> |**Come ottieni i numeri di telefono totali?** <br/> |**Ecco un esempio** <br/> |
|Numero dell'utente (abbonato)  <br/> |Il numero dei numeri di telefono è uguale al numero totale di licenze **Chiamata pianificare interne** e/o **nazionali e internazionali chiamata Plan** moltiplicato per 1.1 + 10 altri numeri di telefono. <br/> |Se dispone di 50 utenti in totale con uno a nazionale chiamata Plan e/o nazionali e internazionali la chiamata a pianificare, è possibile acquisire **65** numeri di telefono **(50 x 1.1 + 10)**. <br/> |
|Numero di servizio a pagamento  <br/> | Il numero dei numeri di telefono è uguale al numero totale di **Conferenze Audio** e **Sistema telefonico in** licenze e utilizza le operazioni seguenti: <br/>  Se sono disponibili **da 1 a 25 licenze** vengono assegnati **5** numeri di telefono. <br/>  Se sono disponibili **da 26 a 49 licenze** vengono assegnati **10** numeri di telefono. <br/>  Se non vi sono **licenze 50-99** vengono assegnati **20** numeri di telefono. <br/>  Se sono disponibili **da 100 a 149 licenze** vengono assegnati **30** numeri di telefono. <br/>  Se sono disponibili **da 150 a 199 licenze** vengono assegnati **40** numeri di telefono. <br/>  Se sono disponibili **da 200 a 499 licenze** vengono assegnati **65** numeri di telefono. <br/>  Se sono disponibili **da 500 a 749 licenze** vengono assegnati **90** numeri di telefono. <br/>  Se sono disponibili **da 750 a 999 licenze** vengono assegnati **110** numeri di telefono. <br/>  Se sono disponibili **da 1000 a 1249 licenze** vengono assegnati **125** numeri di telefono. <br/>  Se non vi sono **1.250 1,499 licenze** vengono assegnati **135** numeri di telefono. <br/>  Se sono disponibili **da 1500 a 1999 licenze** vengono assegnati **160** numeri di telefono. <br/>  Se sono disponibili **da 2000 a 2999 licenze** vengono assegnati **210** numeri di telefono. <br/>  Se sono disponibili **da 3000 a 6999 licenze** vengono assegnati **420** numeri di telefono. <br/>  Se sono disponibili **da 7000 a 9999 licenze** vengono assegnati **500** numeri di telefono. <br/>  Se sono disponibili **da 10.000 a 14.999 licenze** vengono assegnati **600** numeri di telefono. <br/>  Se sono disponibili **da 15.000 a 19.999 licenze** vengono assegnati **700** numeri di telefono. <br/>  Se sono disponibili **da 20.000 a 49.999 licenze** vengono assegnati **1000** numeri di telefono. <br/>  Se sono disponibili **più di 50.000 licenze** vengono assegnati **1500** numeri di telefono. <br/> |Se si dispone di un totale di licenze di **Conferenze Audio** e **51** **Sistema telefonico** , è possibile ottenere numeri di servizio a pagamento **20** . <br/> |
|Numero di servizio gratuito  <br/> | Il numero dei numeri di telefono è uguale al numero totale di **Conferenze Audio** e **Sistema telefonico in** licenze e utilizza le operazioni seguenti: <br/>  Se sono disponibili **da 1 a 25 licenze** vengono assegnati **5** numeri di telefono. <br/>  Se sono disponibili **da 26 a 49 licenze** vengono assegnati **10** numeri di telefono. <br/>  Se non vi sono **licenze 50-99** vengono assegnati **20** numeri di telefono. <br/>  Se sono disponibili **da 100 a 149 licenze** vengono assegnati **30** numeri di telefono. <br/>  Se sono disponibili **da 150 a 199 licenze** vengono assegnati **40** numeri di telefono. <br/>  Se sono disponibili **da 200 a 499 licenze** vengono assegnati **65** numeri di telefono. <br/>  Se sono disponibili **da 500 a 749 licenze** vengono assegnati **90** numeri di telefono. <br/>  Se sono disponibili **da 750 a 999 licenze** vengono assegnati **110** numeri di telefono. <br/>  Se sono disponibili **da 1000 a 1249 licenze** vengono assegnati **125** numeri di telefono. <br/>  Se non vi sono **1.250 1,499 licenze** vengono assegnati **135** numeri di telefono. <br/>  Se sono disponibili **da 1500 a 1999 licenze** vengono assegnati **160** numeri di telefono. <br/>  Se sono disponibili **da 2000 a 2999 licenze** vengono assegnati **210** numeri di telefono. <br/>  Se sono disponibili **da 3000 a 6999 licenze** vengono assegnati **420** numeri di telefono. <br/>  Se sono disponibili **da 7000 a 9999 licenze** vengono assegnati **500** numeri di telefono. <br/>  Se sono disponibili **da 10.000 a 14.999 licenze** vengono assegnati **600** numeri di telefono. <br/>  Se sono disponibili **da 15.000 a 19.999 licenze** vengono assegnati **700** numeri di telefono. <br/>  Se sono disponibili **da 20.000 a 49.999 licenze** vengono assegnati **1000** numeri di telefono. <br/>  Se sono disponibili **più di 50.000 licenze** vengono assegnati **1500** numeri di telefono. <br/> |Se si dispone di un totale di **1001** **Sistema telefonico** e le licenze di **Conferenze Audio** , è possibile ottenere numeri verdi servizio **125** . <br/> <br/> **Importante:** [Riconoscimenti Communications fatturazione](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md) è necessario per prenotare e utilizzare numeri verdi.          |
   
> [!NOTE]
> Se si desidera ottenere altri numeri di telefono rispetto a quella, [contattare il supporto per i prodotti di business - della Guida di amministrazione](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
  
## <a name="related-topics"></a>Argomenti correlati
[Trasferimento di domande comuni numeri di telefono](transferring-phone-numbers-common-questions.md)

[Diversi tipi di numeri di telefono utilizzati per la chiamata dei piani](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per l'organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
[condizioni di chiamata di emergenza](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://go.microsoft.com/fwlink/?LinkID=692099)
