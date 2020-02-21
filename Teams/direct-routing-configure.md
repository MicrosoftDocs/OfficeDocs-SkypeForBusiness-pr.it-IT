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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come configurare il routing diretto di Microsoft Phone System.
ms.openlocfilehash: 9c56078a6d016967e518746e3567373404d1c486
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157874"
---
# <a name="configure-direct-routing"></a>Configurare Instradamento diretto

Microsoft Phone System Direct routing consente di connettere l'infrastruttura di telefonia locale a Microsoft teams. L'articolo elenca i passaggi di alto livello necessari per connettere un SBC (Session Border Controller) supportato a routing diretto e come configurare gli utenti di teams in modo da usare il routing diretto per connettersi alla rete PSTN (Public Switched Telephone Network). Questo articolo collega agli articoli associati per i dettagli.  

Per informazioni sul fatto che il routing diretto è la soluzione ideale per l'organizzazione, vedere [routing diretto del sistema telefonico](direct-routing-landing-page.md). Per informazioni sui prerequisiti e sulla pianificazione della distribuzione, vedere [pianificare il routing diretto](direct-routing-plan.md).

> [!Tip]
> È anche possibile guardare la sessione seguente per conoscere i vantaggi del routing diretto, come pianificare e come distribuirlo: [routing diretto in Microsoft teams](https://aka.ms/teams-direct-routing).

Per completare la procedura descritta in questo articolo, gli amministratori hanno bisogno di una certa familiarità con i cmdlet di PowerShell. Per altre informazioni sull'uso di PowerShell, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Prima di eseguire la procedura descritta in questi articoli, Microsoft consiglia di verificare che il SBC sia già stato configurato come consigliato dal fornitore SBC: 

- [Documentazione di distribuzione di AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentazione di distribuzione Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentazione sulla distribuzione delle comunicazioni della barra multifunzione](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentazione sulla distribuzione di TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Per un elenco completo delle SBCs supportate, vedere l' [elenco dei controller di bordo della sessione certificati per il routing diretto](direct-routing-border-controllers.md).

Per configurare il sistema telefonico Microsoft e consentire agli utenti di usare il routing diretto, eseguire le operazioni seguenti: 

- **Passaggio 1.** [Connettere il SBC con il sistema telefonico Microsoft e convalidare la connessione](direct-routing-connect-the-sbc.md)
- **Passaggio 2.** [Abilitare gli utenti per il routing diretto, la voce e la segreteria telefonica](direct-routing-enable-users.md)
- **Passaggio 3.** [Configurare il routing vocale](direct-routing-voice-routing.md)
- **Passaggio 4.** [Tradurre i numeri in un formato alternativo](direct-routing-translate-numbers.md) 

Se si configura un SBC per più tenant, si vorrà anche leggere [configurare un SBC per più tenant](direct-routing-sbc-multiple-tenants.md).


## <a name="see-also"></a>Vedere anche

[Instradamento diretto di Sistema telefonico](direct-routing-landing-page.md)

[Pianificare Instradamento diretto](direct-routing-plan.md)

