---
title: Configurare Instradamento diretto
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
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
description: Informazioni su come configurare Microsoft Direct Routing per connettere l'infrastruttura di telefonia locale a Teams Sistema telefonico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b72a51008e2a5d55b57809ab5e8ae989f4ed3ec7
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518578"
---
# <a name="configure-direct-routing"></a>Configurare Instradamento diretto

Il routing diretto consente di connettere l'infrastruttura di telefonia locale a Microsoft Teams. L'articolo elenca i passaggi di alto livello necessari per connettere un controller SBC (Session Border Controller) locale supportato al routing diretto e come configurare gli utenti di Teams per l'uso del routing diretto per connettersi alla rete PSTN (Public Switched Telephone Network). Questo articolo contiene collegamenti ad articoli associati per informazioni dettagliate.  

Per informazioni sul fatto che Il routing diretto sia la soluzione giusta per l'organizzazione, vedere [Opzioni di connettività PSTN](pstn-connectivity.md). Per informazioni sui prerequisiti e sulla pianificazione della distribuzione, vedere [Pianificare il routing diretto](direct-routing-plan.md).

Per completare i passaggi descritti in questo articolo, gli amministratori hanno bisogno di una certa familiarità con i cmdlet di PowerShell. Per altre informazioni sull'uso di PowerShell, vedere [Configurare il computer per Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Prima di eseguire la procedura descritta in questi articoli, Microsoft consiglia di confermare che il proprio SBC è già stato configurato come consigliato dal fornitore SBC: 

- [Documentazione sulla distribuzione di AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentazione sulla distribuzione Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentazione sulla distribuzione di Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentazione sulla distribuzione di TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentazione sulla distribuzione di Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Per un elenco completo degli SBC supportati, vedere [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).

Per configurare Sistema telefonico e consentire agli utenti di usare Il routing diretto, seguire questa procedura: 

- **Passaggio 1.** [Connessione SBC con Sistema telefonico e convalidare la connessione](direct-routing-connect-the-sbc.md)
- **Passaggio 2.** [Abilitare gli utenti per routing diretto, segreteria telefonica e segreteria telefonica](direct-routing-enable-users.md)
- **Passaggio 3.** [Configurare il routing delle chiamate](direct-routing-voice-routing.md)
- **Passaggio 4.** [Tradurre i numeri in un formato alternativo](direct-routing-translate-numbers.md) 

Se si sta configurando un SBC per più tenant, è anche utile leggere [Configurare un SBC per più tenant](direct-routing-sbc-multiple-tenants.md).


## <a name="related-topics"></a>Argomenti correlati

[Pianificare la soluzione vocale](cloud-voice-landing-page.md)

[Opzioni di connettività PSTN](pstn-connectivity.md)

[Pianificare Instradamento diretto](direct-routing-plan.md)