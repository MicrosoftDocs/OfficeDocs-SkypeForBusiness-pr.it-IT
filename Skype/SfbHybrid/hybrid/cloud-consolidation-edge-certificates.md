---
title: Aggiornare il certificato Edge
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questa appendice include i passaggi dettagliati per aggiornare il certificato Edge nell'ambito del consolidamento del cloud per Teams e Skype for business.
ms.openlocfilehash: 1c3aaa8859db530ceccbebc68ae76f21e8d4a77f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185501"
---
# <a name="update-the-edge-certificate"></a>Aggiornare il certificato Edge

L'aggiornamento del certificato Edge è il passaggio chiave per garantire che un ambiente su Prem con SipDomain1 sia in grado di partecipare a un ambiente cloud con SipDomain2 e garantire un routing corretto in un ambiente di spazio di indirizzi condiviso tra i due domini SIP. Vedere il passaggio 14 nel consolidamento del [cloud per Teams e Skype for business](cloud-consolidation.md) per il contesto in cui è possibile eseguire questo passaggio. In questo esempio SipDomain1 è AcquiredCompany. <span>com e SipDomain2 è OriginalCompany. <span>com.

Il nome alternativo soggetto (SAN) del certificato in tutti i server perimetrali nell'ambiente locale deve essere aggiornato per includere tutti i domini SIP presenti nel tenant puro online (ad esclusione di qualsiasi onmicrosoft.<span> domini com), nel formato "SIP". \<Domain> ".  In questo esempio si tratta di SIP. OriginalCompany. <span>com. Questo passaggio è fondamentale per eseguire la migrazione degli utenti al cloud.

**Passaggi**

1.  Ottenere un nuovo certificato perimetrale esterno per il bordo che contiene tutte le voci esistenti e altre voci nella SAN per tutti i domini SIP nell'ambiente cloud (ad eccezione dei domini *. onmicrosoft.com) nel modulo "SIP". <DomainName>".
2.  Installare il certificato localmente in ogni Edge Server e assegnarlo a Skype Edge service in ogni servizio Edge.  Per la procedura dettagliata, vedere la sezione "certificati di interfaccia Edge esterni" in [Deploy Edge service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).
3.  Riavviare il servizio Edge in ogni server perimetrale. Puoi eseguire questa operazione per una singola casella con i comandi di PowerShell seguenti:

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Vedere anche

[Consolidamento cloud per Teams e Skype for business](cloud-consolidation.md)