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
description: Informazioni su come configurare Telefono Microsoft routing diretto di sistema per connettere l'infrastruttura di telefonia locale a Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122240"
---
# <a name="configure-direct-routing"></a>Configurare Instradamento diretto

Telefono Microsoft System Direct Routing consente di connettere l'infrastruttura di telefonia locale a Microsoft Teams. L'articolo elenca i passaggi di alto livello necessari per connettere un controller SBC (Session Border Controller) locale supportato al routing diretto e come configurare gli utenti di Teams per l'uso del routing diretto per connettersi alla rete PSTN (Public Switched Telephone Network). Questo articolo contiene collegamenti ad articoli associati per informazioni dettagliate.  

Per informazioni sul fatto che il routing diretto sia la soluzione giusta per l'organizzazione, vedere Sistema telefonico [Routing diretto](direct-routing-landing-page.md). Per informazioni sui prerequisiti e sulla pianificazione della distribuzione, vedere [Pianificare il routing diretto.](direct-routing-plan.md)

> [!Tip]
> È anche possibile guardare la sessione seguente per informazioni sui vantaggi del routing diretto, su come pianificarla e su come distribuirla: Routing diretto [in Microsoft Teams](https://aka.ms/teams-direct-routing).

Per completare i passaggi descritti in questo articolo, gli amministratori hanno bisogno di una certa familiarità con i cmdlet di PowerShell. Per altre informazioni sull'uso di PowerShell, vedere [Configurare il computer per Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 

Prima di eseguire i passaggi descritti in questi articoli, Microsoft consiglia di confermare che il proprio SBC è già stato configurato come consigliato dal fornitore SBC: 

- [Documentazione sulla distribuzione di AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentazione sulla distribuzione Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentazione sulla distribuzione di Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentazione sulla distribuzione di TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentazione sulla distribuzione di Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Per un elenco completo dei controller SBC supportati, vedere Elenco dei controller di [bordo delle sessioni certificati per il routing diretto.](direct-routing-border-controllers.md)

Per configurare Telefono Microsoft sistema e consentire agli utenti di usare Il routing diretto, seguire questa procedura: 

- **Passaggio 1.** [Connessione SBC con Telefono Microsoft sistema e convalidare la connessione](direct-routing-connect-the-sbc.md)
- **Passaggio 2.** [Abilitare gli utenti per routing diretto, segreteria telefonica e segreteria telefonica](direct-routing-enable-users.md)
- **Passaggio 3.** [Configurare il routing vocale](direct-routing-voice-routing.md)
- **Passaggio 4.** [Tradurre i numeri in un formato alternativo](direct-routing-translate-numbers.md) 

Se si sta configurando un SBC per più tenant, è anche utile leggere Configurare un [SBC per più tenant.](direct-routing-sbc-multiple-tenants.md)


## <a name="related-topics"></a>Argomenti correlati

[Instradamento diretto di Sistema telefonico](direct-routing-landing-page.md)

[Pianificare Instradamento diretto](direct-routing-plan.md)