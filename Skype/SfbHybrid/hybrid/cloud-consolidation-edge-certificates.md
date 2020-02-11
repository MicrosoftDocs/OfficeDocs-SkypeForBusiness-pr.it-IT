---
title: Aggiornare il certificato del server perimetrale
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: In questa appendice sono riportati i passaggi dettagliati per l'aggiornamento del certificato Edge nell'ambito del consolidamento cloud per Teams e Skype for business.
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888605"
---
# <a name="update-the-edge-certificate"></a>Aggiornare il certificato del server perimetrale

L'aggiornamento del certificato del server perimetrale è il passaggio fondamentale per garantire che un ambiente su Prem con SipDomain1 possa unirsi a un ambiente cloud con SipDomain2 e garantire il routing corretto in un ambiente di spazio degli indirizzi condiviso tra i due domini SIP. Vedere il passaggio 14 nel [consolidamento del cloud per i team e Skype for business](cloud-consolidation.md) per il contesto in cui è possibile eseguire questo passaggio. Negli esempi riportati di seguito, SipDomain1 è AcquiredCompany. <span>com e SipDomain2 è OriginalCompany. <span>com.

Il nome alternativo soggetto (SAN) del certificato su tutti i server perimetrali nell'ambiente locale deve essere aggiornato in modo da includere tutti i domini SIP presenti nel tenant online puro (escludendo qualsiasi onmicrosoft.<span> domini com), nel formato SIP. \<> di dominio ".  In questo esempio, si tratta di SIP. OriginalCompany. <span>com. Questo passaggio è fondamentale per eseguire la migrazione di tutti gli utenti nel cloud.

**Passi**

1.  Ottenere un nuovo certificato perimetrale esterno per il server perimetrale in cui sono presenti tutte le voci esistenti e altre voci nella rete SAN per tutti i domini SIP nell'ambiente cloud (ad eccezione dei domini *. onmicrosoft.com) nel formato SIP. <DomainName>".
2.  Installare il certificato in locale su ogni server perimetrale e assegnarlo al servizio Edge Skype su ogni servizio Edge.  Per la procedura dettagliata, vedere la sezione "certificati dell'interfaccia perimetrale esterna" in [Deploy Edge service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).
3.  Riavviare il servizio Edge in ogni server perimetrale. È possibile eseguire questa operazione per una singola casella con i comandi di PowerShell seguenti:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Vedere anche

[Consolidamento cloud per Teams e Skype for business](cloud-consolidation.md)