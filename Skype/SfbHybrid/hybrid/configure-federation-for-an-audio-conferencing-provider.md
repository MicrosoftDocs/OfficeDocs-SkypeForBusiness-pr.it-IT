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
description: 'Riepilogo: informazioni su come configurare la federazione per un provider di servizi di audioconferenza in Skype for Business online.'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726886"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurare la federazione per un provider di servizi di audioconferenza nella distribuzione ibrida

**Riepilogo:** Informazioni su come configurare la federazione per un provider di servizi di audioconferenza in Skype for Business online.

Se si desidera utilizzare un Provider di servizi di audioconferenza (ACP) nella distribuzione ibrida (locale con online), è necessario configurare la federazione tra la distribuzione locale e il partner ACP come server partner consentito. È possibile configurare la federazione aggiungendo il dominio del partner ACP e il server perimetrale (denominato anche proxy di accesso) all'elenco Domini federati per la distribuzione locale. Il partner ACP deve quindi aggiungere il nome di dominio completo del pool di server perimetrali locali all'elenco dei domini federati consentiti. Per ulteriori dettagli, contattare il provider ACP. Il partner ACP deve quindi aggiungere il nome di dominio completo del pool di server perimetrali locali all'elenco dei domini federati consentiti.

- **Aggiunta del dominio ACP e del server perimetrale come dominio federato consentito**

    Per aggiungere il dominio ACP come server partner consentito (dominio federato consentito), seguire la procedura descritta in Configurare il supporto [per i domini esterni consentiti.](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx) Per il server perimetrale, aggiungere il nome di dominio completo del server perimetrale del partner ACP. Potrebbe essere necessario contattare il partner ACP per ottenere il nome di dominio completo per il server perimetrale, che può anche essere indicato dal proprio ACP come proxy di accesso.

- **Fornire l'FQDN del pool di server perimetrali al partner ACP**

    Il partner ACP deve configurare la federazione per aggiungere il dominio locale come server partner consentito aggiungendo il nome di dominio completo del pool di server perimetrali come dominio federato consentito.


