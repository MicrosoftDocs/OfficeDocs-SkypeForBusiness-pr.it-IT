---
title: Configurare la federazione per un provider di servizi di audioconferenza nella distribuzione ibrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Riepilogo: informazioni su come configurare la federazione per un provider di servizi di audioconferenza in Skype for Business Online.'
ms.openlocfilehash: 3e01615c65777508c2adead26dd15ca85afbb102e04d8ba57492826942f86672
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301822"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurare la federazione per un provider di servizi di audioconferenza nella distribuzione ibrida

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


**Riepilogo:** Informazioni su come configurare la federazione per un provider di servizi di audioconferenza in Skype for Business Online.

Se si desidera utilizzare un provider di servizi di audioconferenza (ACP) nella distribuzione ibrida (locale con online), è necessario configurare la federazione tra la distribuzione locale e il partner ACP come server partner consentito. È possibile configurare la federazione aggiungendo il dominio partner ACP e il server perimetrale (denominato anche proxy di accesso) all'elenco Domini federati per la distribuzione locale. Il partner ACP deve quindi aggiungere il nome di dominio completo del pool di server perimetrali locale all'elenco dei domini federati consentiti. Per ulteriori dettagli, contattare il provider ACP. Il partner ACP deve quindi aggiungere il nome di dominio completo del pool di server perimetrali locale all'elenco dei domini federati consentiti.

- **Aggiunta del dominio ACP e del server perimetrale come dominio federato consentito**

    Per aggiungere il dominio ACP come server partner consentito (dominio federato consentito), seguire i passaggi descritti in [Configure Support for Allowed External Domains](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains). Per il server perimetrale, aggiungere il nome di dominio completo del server perimetrale del partner ACP. Potrebbe essere necessario contattare il partner ACP per ottenere il nome di dominio completo per il server perimetrale, che può anche essere indicato dal proprio ACP come proxy di accesso.

- **Fornire il nome di dominio completo del pool di server perimetrali al partner ACP**

    Il partner ACP deve configurare la federazione per aggiungere il dominio locale come server partner consentito aggiungendo il nome di dominio completo del pool di server perimetrali come dominio federato consentito.