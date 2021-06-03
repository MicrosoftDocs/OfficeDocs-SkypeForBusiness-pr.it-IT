---
title: Come usare l'ID chiamante nella tua organizzazione
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: L'ID chiamante può essere controllato sia per le chiamate in ingresso che per quelle in uscita per gli utenti di Sistema telefonico utilizzando un criterio denominato CallingLineIdentity.
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723547"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Come usare l'ID chiamante nella tua organizzazione

L'ID chiamante è costituito da due informazioni identificabili dall'utente:

- Un numero di telefono (in genere definito CLID o ID della linea telefonica). Si tratta del numero pstn (Public Switched Telephone Number) presentato come identificativo del chiamante.

- Nome di una parte chiamante(in genere denominata CNAM). 
  
La funzionalità ID chiamante è disponibile per tutti Sistema telefonico utenti indipendentemente dall'opzione di connettività PSTN:

- Piani per chiamate Microsoft 

- Instradamento diretto di Sistema telefonico 
  
È possibile controllare l'ID chiamante per le chiamate in ingresso e in uscita usando un criterio denominato CallingLineIdentity. Per altre informazioni, vedere [Altre informazioni su ID linea chiamante e Nome della parte chiamante.](more-about-calling-line-id-and-calling-party-name.md)

  
## <a name="outbound-pstn-caller-id"></a>ID chiamante PSTN in uscita

Per l'ID chiamante PSTN in uscita, sono disponibili le opzioni seguenti. 
  
- Numero di telefono assegnato all'utente, ovvero l'impostazione predefinita.

- Anonimo, che è disponibile rimuovendo la presentazione del numero PSTN dell'utente. 

- Un numero di telefono sostitutivo, che può essere:

  - Numero di telefono classificato come servizio e numero verde nell'inventario dei numeri di telefono dei Piani per chiamate. In genere viene assegnato a una Teams Operatore automatico o coda di chiamata.

  - Numero di telefono locale tramite Routing diretto assegnato a un account di risorsa usato da un Teams Operatore automatico o coda di chiamata. 

- Nome della parte chiamante o CNAM impostato sulla chiamata PSTN in uscita.  
    
Per altre informazioni, vedere [Impostare l'ID chiamante per un utente.](./set-the-caller-id-for-a-user.md)
  
### <a name="end-user-control-of-outbound-caller-id"></a>Controllo utente finale dell'ID chiamante in uscita

Gli utenti possono modificare l'impostazione dell'ID chiamante **su Anonimo** impostando l'attributo EnableUserOverride. 

Se l'ID chiamante in uscita è impostato su Anonimo, EnableUserOverride non ha alcun effetto e l'ID chiamante è sempre impostato su Anonimo. Il valore predefinito di EnableUserOverride è False.

Gli utenti finali possono impostare l'ID chiamante su Anonimo selezionando **Impostazioni > Chiamate** e quindi in **ID** chiamante selezionare Nascondi il numero di telefono e le informazioni del profilo per tutte **le chiamate.**

### <a name="notes"></a>Note

Tenere presente quanto segue:

- Non è possibile assegnare i tipi di numeri di telefono seguenti per l'ID chiamante in uscita:

  - Tutti i numeri di telefono classificati come utente nell'inventario dei numeri di telefono dei Piani per chiamate.

  - Qualsiasi numero di telefono locale tramite Routing diretto assegnato a un utente.

  - Un Skype for Business Server di telefono locale.

- L'uso della sostituzione del numero di telefono dell'account della risorsa funziona solo per Teams utenti. La sostituzione del numero di telefono del servizio funziona sia per Skype for Business online che per Teams utenti.

- Il nome della parte chiamante viene inviato solo sulle chiamate in cui l'ID chiamante viene sostituito con LineUri, un numero di telefono dell'account di servizio o della risorsa e quando il chiamante è un Teams utente.

- Nome parte chiamante può contenere un massimo di 200 caratteri, ma i sistemi a valle potrebbero supportare un numero inferiore di caratteri.

- Per l'instradamento diretto, la sostituzione del numero di telefono e il nome della parte chiamante vengono inviati nell'intestazione SIP FROM. Se il corrispondente OnlinePstnGateway è configurato con ForwardPai = True, l'intestazione SIP P-ASSERTED-IDENTITY conterrà l'utente chiamante reale.

- EnableUserOverride ha la precedenza sulle altre impostazioni del criterio, a meno che la sostituzione non sia impostata su Anonimo. Si supponga, ad esempio, che l'istanza dei criteri abbia la sostituzione con un account di risorsa e che EnableUserOverride sia impostato e abilitato dall'utente. In questo caso, l'ID chiamante in uscita verrà bloccato e verrà usato Anonimo. Se un'istanza dei criteri ha la sostituzione impostata su Anonimo e EnableUserOverride è impostato, l'ID chiamante in uscita sarà sempre Anonimo, indipendentemente dall'impostazione dell'utente finale.

   
## <a name="inbound-caller-id"></a>ID chiamante in ingresso

Sistema telefonico il numero di telefono esterno in arrivo come ID chiamante. Se il numero è associato a un utente o un contatto in Azure AD o a un contatto personale, i client Skype for Business e Teams mostreranno l'ID chiamante in base a queste informazioni. Se il numero di telefono non si trova in Azure AD o in un contatto personale, se disponibile verrà visualizzato il nome visualizzato fornito da telco.

L'attributo BlockIncomingCallerID consente di bloccare l'ID chiamante nelle chiamate PSTN in arrivo. Puoi impostare questo attributo, ma questo non è disponibile per gli utenti finali nella pagina Impostazioni utente. Quando questa impostazione è abilitata, il chiamante PSTN in arrivo verrà visualizzato come proveniente da Anonimo.
  
Per bloccare l'ID chiamante in ingresso, vedere [Impostare l'ID chiamante per un utente.](./set-the-caller-id-for-a-user.md)
  
## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](./phone-number-calling-plans/port-order-overview.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
