---
title: "Come è necessario immettere i numeri di telefono?"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Informazioni su come configurare i numeri di telefono quando porta Skype per le aziende. '
ms.openlocfilehash: a7364c5ebf72730179c6848dc79172f4f971ff6a
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a>Come è necessario immettere i numeri di telefono?

Quando si trasferisce i numeri di telefono, è necessario immettere tali nel formato corretto. 
  
> [!NOTE]
> Ogni numero di telefono o un intervallo di numero di telefono deve essere immesso separatamente su ogni riga. 
  
- Quando si immettono i numeri di telefono singolo:
    
  - Verranno ignorati tutti i caratteri speciali (inclusi trattino "-"). Ad esempio:
    
  - Per un numero a 10 cifre: ** &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649** verrà corretto per **+14255550649**.
    
  - Per un numero a 11 cifre: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** verrà corretto per **+14255550649**.
    
  - Tutti i tag verranno ignorati se sono presenti 10 o 11 cifre. Ad esempio ** \<div > 4255551234\</div >** sarà **+ 14255551234**.
    
  - "-", verrà ignorato spazio e parentesi chiusa. Ad esempio:
    
  - Per un numero a 10 cifre: **(425) 555-6776** verrà corretto per **+14255556776**.
    
  - Per un numero a 11 cifre: **555-6776 1(425)** verrà corretto per **+14255556776**.
    
  - Tutte le lettere verranno considerate come caratteri speciali e viene ignorate se esiste un numero di telefono 10 o 11 cifre. Ad esempio:
    
  - Per un numero a 10 cifre: **14jaosia2reoij05jof55506ajfoj49isdjf** verrà corretto per **+14255550649**.
    
  - Per un numero a 11 cifre: **1ade4jaoda2rfoij05ojof55506dsfoj49if** verrà corretto per **+14255550649**.
    
  - Verrà corretto qualsiasi combinazione dei caratteri speciali, anche in altre lingue. Ad esempio: 
    
  - Per un numero a 10 cifre:**中文4中文2ajj5\*() (\*(5() 551345** verrà corretto per **+14555551345**.
    
  - Per un numero a 11 cifre:**中文4中文2$ a5\*() (\*(5() 55 (.1345** verrà corretto per **+14555551345**.
    
  - Se tutti i numeri contengono meno di 10 o superiore a 11 cifre, vengono evidenziate per l'utente corretta:
    
  - \*\*5551245\* \* verrà evidenziata e da correggere.
    
  - **1234567891011** verrà evidenziata e da correggere.
    
  - Tutti i numeri presenti meno di 10 o superiore a 11 cifre, con i caratteri speciali, verranno evidenziati senza da correggere automaticamente.
    
  - Per un numero a 7 cifre senza caratteri speciali immessi: **123456abcdefg7** verrà evidenziata e da correggere, ma non verranno ignorate le lettere.
    
  - Per un numero a 7 cifre con caratteri speciali immessi: **12345!@#$%^&amp;\*(.)-@# $% ^&amp;\*(7)** verrà evidenziata per da correggere. I caratteri speciali non vengono ignorati.
    
- Quando si immette un intervallo di numeri di telefono.
    
  - Sono consentiti solo due numeri di telefono. Il numero più piccolo deve essere il primo numero nell'intervallo.
    
  - Tutti i caratteri speciali (tranne per il trattino "-") vengono trattati come numeri singolo. Ad esempio, **(425) 555 0&amp;\*(123-(1425) 5557899nm** verrà corretto per **+ 14255550123 - +13202040659**.
    
  - Il "-" viene utilizzato per separare solo due numeri. Non è supportato in modo da includere più "-" nell'intervallo di numeri. Ad esempio, **(425) 555-0649-(425) 555-1115** deve essere immesso come **(425) 5550649 - (425) 5551115**.
    
 **Per istruzioni dettagliate complete, vedere [trasferire i numeri di telefono a Office 365](transfer-phone-numbers-to-office-365.md).**

 > [!NOTE]
> Se hai bisogno di ulteriori numeri di telefono, visita la pagina [Contattare il supporto per i prodotti aziendali - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

  
## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](transferring-phone-numbers-common-questions.md)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per la propria organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://go.microsoft.com/fwlink/?LinkID=692099)

## <a name="feedback"></a>Commenti e suggerimenti?
Per inviare commenti e suggerimenti prodotto o per consentire us sapere come ci si limita, vedere [Skype per commenti e suggerimenti Business](https://www.skypefeedback.com).