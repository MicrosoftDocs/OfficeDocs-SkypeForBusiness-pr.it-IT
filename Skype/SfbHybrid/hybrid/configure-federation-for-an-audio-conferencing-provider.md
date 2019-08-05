---
title: Configurare la Federazione per un provider di servizi di audioconferenza nella distribuzione ibrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: 'Riepilogo: informazioni su come configurare la Federazione per un provider di servizi di audioconferenza in Skype for business online.'
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185462"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurare la Federazione per un provider di servizi di audioconferenza nella distribuzione ibrida

**Riepilogo:** Informazioni su come configurare la Federazione per un provider di servizi di audioconferenza in Skype for business online.

Se si vuole usare un provider di servizi di audioconferenza (ACP) nella distribuzione ibrida (locale con online), è necessario configurare la Federazione tra la distribuzione locale e il partner ACP come server partner consentito. È possibile configurare la Federazione aggiungendo il dominio partner ACP e il server perimetrale (può anche essere chiamato proxy di accesso) nell'elenco dei domini federati per la distribuzione locale. Il partner ACP deve quindi aggiungere il nome di dominio completo del pool di Edge Server locale all'elenco dei domini federati consentiti. Per ulteriori informazioni, contattare il provider ACP. Il partner ACP deve quindi aggiungere il nome di dominio completo del pool di Edge Server locale all'elenco dei domini federati consentiti.

- **Aggiunta del dominio ACP e del server perimetrale come dominio federato consentito**

    Per aggiungere il dominio ACP come server partner consentito (dominio federato consentito), seguire i passaggi descritti in [configurare il supporto per i domini esterni](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)consentiti. Per il server perimetrale, aggiungere il nome di dominio completo del server Edge del partner ACP. Potrebbe essere necessario contattare il partner ACP per ottenere il nome di dominio completo per il server perimetrale, che può anche essere indicato dal proprio proxy di accesso per i paesi ACP.

- **Fornire il nome di dominio completo del pool di Edge Server al partner ACP**

    Il partner ACP deve configurare la Federazione per aggiungere il dominio locale come server partner consentito aggiungendo il nome FQDN del pool di Edge Server come dominio federato consentito.


