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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: L'ID chiamante può essere controllato sia per le chiamate in ingresso che per quelle in uscita per gli utenti di Sistema telefonico utilizzando un criterio denominato CallingLineIdentity.
ms.openlocfilehash: 250f8a1a516aec4c9941b0c6396e6d44771b4f53
ms.sourcegitcommit: f608811288c82a6348a6af1671246a93ed06e578
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2022
ms.locfileid: "66660962"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Come usare l'ID chiamante nella tua organizzazione

L'ID chiamante è costituito da due informazioni rivolte all'utente:

- Un numero di telefono (detto CLID o ID linea di chiamata). Questo è il numero PSTN (Public Switched Telephone Network) presentato come identificazione del chiamante.

- Nome di un chiamante (in genere chiamato CNAM). 
  
La funzionalità ID chiamante è disponibile per tutti gli utenti del sistema telefonico, indipendentemente [dall'opzione di connettività PSTN](pstn-connectivity.md): Piano per chiamate Microsoft, Connessione operatore o Routing diretto. 
  
È possibile controllare l'ID chiamante sia per le chiamate in ingresso che per le chiamate in uscita utilizzando un criterio denominato CallingLineIdentity. Per ulteriori informazioni, vedi [Ulteriori informazioni sull'ID della linea di chiamata e sul nome del chiamante](more-about-calling-line-id-and-calling-party-name.md).

  
## <a name="outbound-pstn-caller-id"></a>ID chiamante PSTN in uscita

Per l'ID chiamante PSTN in uscita sono disponibili le opzioni seguenti. 
  
- Numero di telefono assegnato all'utente, ovvero l'impostazione predefinita.

- Anonimo, disponibile rimuovendo la presentazione del numero PSTN dell'utente. 

- Un numero di telefono sostitutivo, che può essere:

  - Numero di telefono classificato come servizio e numero verde nell'inventario dei numeri di telefono dei Piani per chiamate. È assegnato a un operatore automatico di Teams o a una coda di chiamata.

  - Un numero di telefono locale tramite routing diretto assegnato a un account di risorsa utilizzato da un operatore automatico di Teams o da una coda di chiamata. 

- Nome del chiamante o CNAM impostato per la chiamata PSTN in uscita.  
    
Per altre informazioni, vedere [Impostare l'ID chiamante per un utente](./set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Controllo dell'ID chiamante in uscita da parte dell'utente finale

Gli utenti possono modificare l'impostazione dell'ID chiamante su **Anonimo** impostando l'attributo EnableUserOverride. 

Se l'ID chiamante in uscita è impostato su Anonimo, EnableUserOverride non ha alcun effetto e l'ID chiamante è sempre impostato su Anonimo. Il valore predefinito di EnableUserOverride è False.

Gli utenti finali possono impostare il proprio ID chiamante su Anonimo accedendo a **Impostazioni > Chiamate** e quindi in **ID chiamante** selezionare **Nascondi il numero di telefono e le informazioni del profilo per tutte le chiamate**. La modifica di questa impostazione richiede alcuni minuti per riflettere sulle nuove chiamate. 

### <a name="notes"></a>Note

Tenere presente quanto segue:

- Non è possibile assegnare i tipi di numeri di telefono seguenti per l'ID chiamante in uscita:

  - Qualsiasi numero di telefono classificato come utente nell'inventario dei numeri di telefono dei Piani per chiamate.

  - Qualsiasi numero di telefono locale tramite routing diretto assegnato a un utente.

  - Un Skype for Business Server numero di telefono locale.

- L'uso della sostituzione del numero di telefono dell'account delle risorse funziona per gli utenti di Teams. La sostituzione del numero di telefono del servizio funziona per gli utenti di Teams.

- Il nome del chiamante viene inviato alle chiamate in cui l'ID chiamante viene sostituito con LineUri, un numero di telefono dell'account di servizio o risorsa e quando il chiamante è un utente di Teams.

- Il nome del chiamante può avere un massimo di 200 caratteri, ma i sistemi a valle potrebbero supportare meno caratteri.

- Per l'instradamento diretto, la sostituzione del numero di telefono e il nome del chiamante vengono inviati nell'intestazione SIP. Se l'onlinePstnGateway corrispondente è configurato con ForwardPai = True, l'intestazione SIP P-ASSERTED-IDENTITY conterrà l'utente chiamante reale.

- EnableUserOverride ha la precedenza sulle altre impostazioni del criterio, a meno che la sostituzione non sia impostata su Anonymous. Si supponga, ad esempio, che l'istanza dei criteri abbia la sostituzione usando un account di risorsa e EnableUserOverride sia impostato e abilitato dall'utente. In questo caso, l'ID chiamante in uscita verrà bloccato e verrà usato Anonymous. Se un'istanza di criterio ha impostato la sostituzione su Anonymous e EnableUserOverride è impostata, l'ID chiamante in uscita sarà sempre Anonimo, indipendentemente dall'impostazione dell'utente finale.

   
## <a name="inbound-caller-id"></a>ID chiamante in ingresso

Sistema telefonico mostra il numero di telefono esterno in arrivo come ID chiamante. Se il numero è associato a un utente o un contatto in Azure AD o a un contatto personale, i client di Skype for Business e Teams mostreranno l'ID chiamante in base a tali informazioni. Se il numero di telefono non è incluso in Azure AD o in un contatto personale, il nome visualizzato fornito da telco verrà visualizzato se disponibile.

L'attributo BlockIncomingCallerID consente di bloccare l'ID chiamante nelle chiamate PSTN in arrivo. Puoi impostare questo attributo, ma questo non è disponibile per gli utenti finali nella pagina Impostazioni utente. Quando questa impostazione è abilitata, il chiamante PSTN in arrivo viene visualizzato come proveniente da Anonimo.
  
Per bloccare l'ID chiamante in ingresso, vedere [Impostare l'ID chiamante per un utente](./set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](./phone-number-calling-plans/port-order-overview.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
