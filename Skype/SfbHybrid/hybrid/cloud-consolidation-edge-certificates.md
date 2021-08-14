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
description: Questa appendice include la procedura dettagliata per l'aggiornamento del certificato perimetrale nell'ambito del consolidamento cloud per Teams e Skype for Business.
ms.openlocfilehash: 7370fe6949c471a6aad9b45ee246f1565b43bdb465eba2110a03f53afa69fe28
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330630"
---
# <a name="update-the-edge-certificate"></a>Aggiornare il certificato perimetrale

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


L'aggiornamento del certificato perimetrale è il passaggio chiave per garantire che un ambiente locale con SipDomain1 possa aggiungersi a un ambiente cloud con SipDomain2 e garantire il routing corretto in un ambiente con spazio di indirizzi condiviso tra i due domini SIP. Vedere il passaggio 14 in [Consolidamento cloud per](cloud-consolidation.md) Teams e Skype for Business per il contesto in cui è possibile eseguire questo passaggio. In questo esempio SipDomain1 è AcquiredCompany. <span> com e SipDomain2 sono OriginalCompany. <span> com.

Il nome soggetto alternativo (SAN) del certificato in tutti i server perimetrali nell'ambiente locale deve essere aggiornato in modo da includere tutti i domini SIP presenti nel tenant online puro (escluso qualsiasi onmicrosoft). <span> com domains), nel formato "sip. \<domain> ".  In questo esempio, si tratta di sip. OriginalCompany. <span> com. Questo passaggio è fondamentale prima di eseguire la migrazione degli utenti nel cloud.

**Passaggi:**

1.  Ottenere un nuovo certificato edge esterno per il server perimetrale con tutte le voci esistenti più voci aggiuntive nella san per tutti i domini SIP nell'ambiente cloud (esclusi i domini *.onmicrosoft.com) nel formato "sip. <DomainName> ".
2.  Installare il certificato in locale in ogni server perimetrale e assegnarlo al servizio edge Skype in ogni servizio perimetrale.  Per la procedura dettagliata, vedere la sezione "Certificati dell'interfaccia perimetrale esterna" [in Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).
3.  Riavviare il servizio Edge in ognuno dei server perimetrali. È possibile eseguire questa operazione per una singola casella con i comandi di PowerShell seguenti:

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>Vedere anche

[Consolidamento cloud per Teams e Skype for Business](cloud-consolidation.md)