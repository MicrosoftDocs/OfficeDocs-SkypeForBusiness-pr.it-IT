---
title: Quanti numeri di telefono puoi ottenere?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.quantity
ms.custom:
- Calling Plans
description: Se per la tua organizzazione hai bisogno di numeri di telefono aggiuntivi, puoi ottenere una quantità di numeri di telefono maggiore rispetto al numero di licenze assegnate. Tutto dipende, però, dal tipo di numeri di telefono e di licenze acquistate e assegnate. È possibile fare clic su diversi tipi di numeri di telefono usati per chiamare i piani per scoprire i diversi numeri di telefono usati in Microsoft teams.
ms.openlocfilehash: 58767883e25027909b69b9c5a78b7890ee7b3882
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572081"
---
# <a name="how-many-phone-numbers-can-you-get"></a>Quanti numeri di telefono puoi ottenere?

Se per la tua organizzazione hai bisogno di numeri di telefono aggiuntivi, puoi ottenere una quantità di numeri di telefono maggiore rispetto al numero di licenze assegnate. Tutto dipende, però, dal tipo di numeri di telefono e di licenze acquistate e assegnate. È possibile fare clic su [diversi tipi di numeri di telefono usati per chiamare i piani](different-kinds-of-phone-numbers-used-for-calling-plans.md) per scoprire i diversi numeri di telefono usati in Microsoft teams.
  
Puoi visualizzare il numero di numeri di telefono che puoi ottenere nella pagina **Ottieni numeri di telefono** nell'interfaccia di amministrazione di Microsoft teams oppure puoi eseguire il cmdlet [Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/library/mt634605.aspx) .
  
> [!IMPORTANT]
> I limiti seguenti non includono i numeri di telefono trasferiti su Microsoft. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>Quanti numeri di telefono è possibile ottenere?

||||
|:-----|:-----|:-----|
|**Ecco il tipo di numero di telefono** <br/> |**Come ottieni i numeri di telefono totali?** <br/> |**Ecco un esempio** <br/> |
|Numero dell'utente (abbonato)  <br/> |Il numero di numeri di telefono è uguale al numero totale di licenze per le chiamate **nazionali** e/o per il **piano di chiamate nazionali e internazionali** moltiplicato per 1,1 + 10 numeri di telefono aggiuntivi. <br/> |Se si hanno 50 utenti in totale con un piano per chiamate nazionali e/o un piano per chiamate nazionali e internazionali, è possibile acquistare **65** numero di telefono **(50 x 1,1 + 10)**. <br/> |
|Numero di servizio a pagamento  <br/> | Il numero di numeri di telefono è uguale al numero totale di licenze per il **sistema telefonico** e per i servizi di **audioconferenza** e USA quanto segue: <br/>  Se sono disponibili **da 1 a 25 licenze** vengono assegnati **5** numeri di telefono. <br/>  Se sono disponibili **da 26 a 49 licenze** vengono assegnati **10** numeri di telefono. <br/>  Se sono **50-99 licenze** vengono assegnati **20** numeri di telefono. <br/>  Se sono disponibili **da 100 a 149 licenze** vengono assegnati **30** numeri di telefono. <br/>  Se sono disponibili **da 150 a 199 licenze** vengono assegnati **40** numeri di telefono. <br/>  Se sono disponibili **da 200 a 499 licenze** vengono assegnati **65** numeri di telefono. <br/>  Se sono disponibili **da 500 a 749 licenze** vengono assegnati **90** numeri di telefono. <br/>  Se sono disponibili **da 750 a 999 licenze** vengono assegnati **110** numeri di telefono. <br/>  Se sono disponibili **da 1000 a 1249 licenze** vengono assegnati **125** numeri di telefono. <br/>  Se sono disponibili **licenze da 1250 a 1499** , vengono assegnati i numeri di telefono di **135** . <br/>  Se sono disponibili **da 1500 a 1999 licenze** vengono assegnati **160** numeri di telefono. <br/>  Se sono disponibili **da 2000 a 2999 licenze** vengono assegnati **210** numeri di telefono. <br/>  Se sono disponibili **da 3000 a 6999 licenze** vengono assegnati **420** numeri di telefono. <br/>  Se sono disponibili **da 7000 a 9999 licenze** vengono assegnati **500** numeri di telefono. <br/>  Se sono disponibili **da 10.000 a 14.999 licenze** vengono assegnati **600** numeri di telefono. <br/>  Se sono disponibili **da 15.000 a 19.999 licenze** vengono assegnati **700** numeri di telefono. <br/>  Se sono disponibili **da 20.000 a 49.999 licenze** vengono assegnati **1000** numeri di telefono. <br/>  Se sono disponibili **più di 50.000 licenze** vengono assegnati **1500** numeri di telefono. <br/> |Se si dispone di un totale di **51** di **sistema telefonico** e di licenze per i servizi di **audioconferenza** , è possibile ottenere **20** numeri di servizio a pedaggio. <br/> |
|Numero di servizio gratuito  <br/> | Il numero di numeri di telefono è uguale al numero totale di licenze per il **sistema telefonico** e per i servizi di **audioconferenza** e USA quanto segue: <br/>  Se sono disponibili **da 1 a 25 licenze** vengono assegnati **5** numeri di telefono. <br/>  Se sono disponibili **da 26 a 49 licenze** vengono assegnati **10** numeri di telefono. <br/>  Se sono **50-99 licenze** vengono assegnati **20** numeri di telefono. <br/>  Se sono disponibili **da 100 a 149 licenze** vengono assegnati **30** numeri di telefono. <br/>  Se sono disponibili **da 150 a 199 licenze** vengono assegnati **40** numeri di telefono. <br/>  Se sono disponibili **da 200 a 499 licenze** vengono assegnati **65** numeri di telefono. <br/>  Se sono disponibili **da 500 a 749 licenze** vengono assegnati **90** numeri di telefono. <br/>  Se sono disponibili **da 750 a 999 licenze** vengono assegnati **110** numeri di telefono. <br/>  Se sono disponibili **da 1000 a 1249 licenze** vengono assegnati **125** numeri di telefono. <br/>  Se sono disponibili **licenze da 1250 a 1499** , vengono assegnati i numeri di telefono di **135** . <br/>  Se sono disponibili **da 1500 a 1999 licenze** vengono assegnati **160** numeri di telefono. <br/>  Se sono disponibili **da 2000 a 2999 licenze** vengono assegnati **210** numeri di telefono. <br/>  Se sono disponibili **da 3000 a 6999 licenze** vengono assegnati **420** numeri di telefono. <br/>  Se sono disponibili **da 7000 a 9999 licenze** vengono assegnati **500** numeri di telefono. <br/>  Se sono disponibili **da 10.000 a 14.999 licenze** vengono assegnati **600** numeri di telefono. <br/>  Se sono disponibili **da 15.000 a 19.999 licenze** vengono assegnati **700** numeri di telefono. <br/>  Se sono disponibili **da 20.000 a 49.999 licenze** vengono assegnati **1000** numeri di telefono. <br/>  Se sono disponibili **più di 50.000 licenze** vengono assegnati **1500** numeri di telefono. <br/> |Se si ha un totale di **1001** e **licenze per i servizi di** **audioconferenza** , è possibile ottenere i numeri di servizio senza pedaggio di **125** . <br/> <br/> **Importante:** i [crediti per comunicazioni la fatturazione](set-up-communications-credits-for-your-organization.md) è necessaria per prenotare e usare numeri verdi gratuiti.          |
   
> [!NOTE]
> Se hai bisogno di ulteriori numeri di telefono, visita la pagina [Contattare il supporto per i prodotti aziendali - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
  
## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](transferring-phone-numbers-common-questions.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)

[Etichetta Disclaimer per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 