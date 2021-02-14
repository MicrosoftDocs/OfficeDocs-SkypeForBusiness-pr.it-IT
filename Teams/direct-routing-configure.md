---
title: Configurare Instradamento diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come configurare l'instradamento diretto del sistema telefonico Microsoft per connettere l'infrastruttura di telefonia locale a Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5388c93e741323d3dc9eda0fc51968b8b344d2cb
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701294"
---
# <a name="configure-direct-routing"></a>Configurare Instradamento diretto

Microsoft Phone System Direct Routing consente di connettere l'infrastruttura di telefonia locale a Microsoft Teams. In questo articolo sono elencati i passaggi di alto livello necessari per connettere un controller SBC (Session Border Controller) locale supportato al routing diretto e viene spiegato come configurare gli utenti di Teams in modo che usino il routing diretto per connettersi alla rete PSTN (Public Switched Telephone Network). Questo articolo contiene collegamenti ad articoli associati per informazioni dettagliate.  

Per informazioni sul fatto che l'instradamento diretto sia la soluzione giusta per la propria organizzazione, vedere Routing diretto sistema [telefonico.](direct-routing-landing-page.md) Per informazioni sui prerequisiti e la pianificazione della distribuzione, vedere [Pianificare il routing diretto.](direct-routing-plan.md)

> [!Tip]
> È anche possibile guardare la sessione seguente per informazioni sui vantaggi del routing diretto, su come pianificarlo e su come distribuirlo: Routing [diretto in Microsoft Teams.](https://aka.ms/teams-direct-routing)

Per completare i passaggi descritti in questo articolo, gli amministratori hanno bisogno di una certa familiarità con i cmdlet di PowerShell. Per altre informazioni sull'uso di PowerShell, vedere [Configurare il computer per Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 

Prima di eseguire i passaggi descritti in questi articoli, Microsoft consiglia di verificare che sBC sia già stato configurato come consigliato dal fornitore del servizio SBC: 

- [Documentazione sulla distribuzione di AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentazione della distribuzione Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentazione sulla distribuzione di Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentazione sulla distribuzione di TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentazione sulla distribuzione di Metapass](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Per un elenco completo dei controller dei confini della sessione supportati, consulta l'elenco dei controller dei confini [della sessione certificati per l'instradamento diretto.](direct-routing-border-controllers.md)

Per configurare il Sistema telefonico Microsoft e consentire agli utenti di usare l'instradamento diretto, seguire questa procedura: 

- **Passaggio 1.** [Collegare il servizio SBC al Sistema telefonico Microsoft e convalidare la connessione](direct-routing-connect-the-sbc.md)
- **Passaggio 2.** [Abilitare gli utenti per l'instradamento diretto, la voce e la segreteria telefonica](direct-routing-enable-users.md)
- **Passaggio 3.** [Configurare il routing vocale](direct-routing-voice-routing.md)
- **Passaggio 4.** [Convertire i numeri in un formato alternativo](direct-routing-translate-numbers.md) 

Se si sta configurando un database SBC per più tenant, è anche utile leggere Configurare un [SBC per più tenant.](direct-routing-sbc-multiple-tenants.md)


## <a name="related-topics"></a>Argomenti correlati

[Instradamento diretto di Sistema telefonico](direct-routing-landing-page.md)

[Pianificare Instradamento diretto](direct-routing-plan.md)

