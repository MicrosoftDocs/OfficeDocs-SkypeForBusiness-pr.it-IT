---
title: Aggiornare il certificato perimetrale
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
description: Questa appendice include la procedura dettagliata per aggiornare il certificato edge nell'ambito del consolidamento del cloud per Teams e Skype for Business.
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888605"
---
# <a name="update-the-edge-certificate"></a>Aggiornare il certificato perimetrale

L'aggiornamento del certificato perimetrali è il passaggio chiave per garantire che un ambiente locale con SipDomain1 possa aggiungersi a un ambiente cloud con SipDomain2 e garantire il routing appropriato in un ambiente con spazio di indirizzi condiviso tra i due domini SIP. Vedere il passaggio 14 nel [consolidamento del cloud per Teams e Skype for Business](cloud-consolidation.md) per il contesto in cui è possibile eseguire questo passaggio. In questo esempio SipDomain1 è AcquiredCompany. <span> com e SipDomain2 sono OriginalCompany. <span> com.

Il nome alternativo del soggetto (SAN) del certificato in tutti i server perimetrali nell'ambiente locale deve essere aggiornato per includere tutti i domini SIP presenti nel tenant online puro (escluso qualsiasi onmicrosoft. <span> com domains), nel formato "sip. \< dominio>".  In questo esempio, si tratta di sip. OriginalCompany. <span> com. Questo passaggio è fondamentale prima di eseguire la migrazione degli utenti nel cloud.

**Passaggi:**

1.  Ottenere un nuovo certificato perimetrali esterno per il server perimetrale con tutte le voci esistenti più voci aggiuntive nel san per tutti i domini SIP nell'ambiente cloud (esclusi i domini *.onmicrosoft.com) nel formato "sip. <DomainName> ".
2.  Installare il certificato in locale in ogni server perimetrale e assegnarlo al servizio Skype Edge in ogni servizio perimetrale.  Per la procedura dettagliata, vedere la sezione "Certificati dell'interfaccia perimetrale esterna" in [Distribuire il servizio Edge in Skype for Business Server 2015.](https://technet.microsoft.com/library/dn951368.aspx)
3.  Riavviare il servizio Edge in ognuno dei server perimetrali. È possibile eseguire questa operazione per una singola casella con i comandi di PowerShell seguenti:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Vedere anche

[Consolidamento del cloud per Teams e Skype for Business](cloud-consolidation.md)