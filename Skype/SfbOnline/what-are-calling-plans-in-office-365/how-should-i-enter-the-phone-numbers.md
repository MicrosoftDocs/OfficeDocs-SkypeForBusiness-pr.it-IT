---
title: Come è possibile immettere i numeri di telefono?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Scopri come configurare i numeri di telefono quando li porti in Skype for business. '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280531"
---
# <a name="how-should-i-enter-the-phone-numbers"></a>Come è possibile immettere i numeri di telefono?

Quando si trasferiscono i numeri di telefono, è necessario immetterli nel formato corretto. 
  
> [!NOTE]
> Ogni numero di telefono o intervallo di numeri di telefono deve essere immesso separatamente per ogni riga. 
  
- Quando si immette un singolo numero di telefono:
    
  - Tutti i caratteri speciali verranno ignorati (incluso Dash "-"). Ad esempio:
    
  - Per un numero a 10 cifre: ** &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649** verrà corretto in **+ 14255550649**.
    
  - Per un numero a 11 cifre: **1\*() (\*&amp;42&amp;\*()\*&amp;(55550649** verrà corretto in **+ 14255550649**.
    
  - Tutti i tag verranno ignorati se sono presenti 10 o 11 cifre. Ad esempio, ** \<div> 4255551234\</div>** sarà **+ 14255551234**.
    
  - "-", spazio e parentesi verranno ignorati. Ad esempio:
    
  - Per un numero a 10 cifre: **(425) 555-6776** verrà corretto in **+ 14255556776**.
    
  - Per un numero a 11 cifre: **1 (425) 555-6776** verrà corretto in **+ 14255556776**.
    
  - Tutte le lettere verranno trattate come caratteri speciali e ignorate se è presente un numero di telefono di 10 cifre o di 11 numeri. Ad esempio:
    
  - Per un numero a 10 cifre: **14jaosia2reoij05jof55506ajfoj49isdjf** verrà corretto in **+ 14255550649**.
    
  - Per un numero a 11 cifre: **1ade4jaoda2rfoij05ojof55506dsfoj49if** verrà corretto in **+ 14255550649**.
    
  - Qualsiasi combinazione di caratteri speciali, anche in altre lingue, verrà corretta. Ad esempio: 
    
  - Per un numero a 10 cifre:**中文 4 中文2ajj5\*() (\*(5 ()... 551345** verrà corretto in **+ 14555551345**.
    
  - Per un numero a 11 cifre:**中文 4 中文 2 $ a5\*() (\*(5 ()... 55 (. 1345** verrà corretto in **+ 14555551345**.
    
  - Se i numeri contengono meno di 10 cifre o più di 11 cifre, verranno evidenziati per correggere l'utente:
    
  - \*\*5551245\* \* sarà evidenziato e deve essere corretto.
    
  - **1234567891011** sarà evidenziato e deve essere corretto.
    
  - Tutti i numeri con meno di 10 cifre o più di 11 cifre, con eventuali caratteri speciali, verranno evidenziati senza essere corretti automaticamente.
    
  - Per un numero a 7 cifre senza caratteri speciali immessi: **123456abcdefg7** verrà evidenziato e deve essere corretto, ma le lettere non verranno ignorate.
    
  - Per un numero a 7 cifre con caratteri speciali immessi: **12345! @ # $% ^&amp;\*()--@ # $% ^&amp;\*() 7** verrà evidenziato per essere corretto. I caratteri speciali non verranno ignorati.
    
- Quando si immette un intervallo di numeri di telefono.
    
  - Sono consentiti solo due numeri di telefono. Il numero più piccolo deve essere il primo numero nell'intervallo.
    
  - Tutti i caratteri speciali (ad eccezione del trattino "-") vengono trattati come numeri singoli. Ad esempio, **(425) 555 0&amp;\*(123-(1425) 5557899nm** verrà corretto in **+ 14255550123-+ 13202040659**.
    
  - "-" Viene usato solo per separare i due numeri. Non è supportata l'inclusione di più "-" nell'intervallo di numeri. Ad esempio, **(425) 555-0649-(425) 555-1115** deve essere immesso come **(425) 5550649-(425) 5551115**.
    
  **Per istruzioni dettagliate, vedere [trasferire i numeri di telefono in Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**

  > [!NOTE]
  > Se hai bisogno di ulteriori numeri di telefono, visita la pagina [Contattare il supporto per i prodotti aziendali - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

  
## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 