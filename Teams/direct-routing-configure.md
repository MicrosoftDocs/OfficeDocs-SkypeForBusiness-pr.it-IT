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
description: Informazioni su come configurare Microsoft Direct Routing per connettere l'infrastruttura telefonica locale a Teams Phone System.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf6a180b558edad23450fad3991ee2c646f6cf55
ms.sourcegitcommit: 830357674103c0c5c99bd73d40261afe02a2da49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/09/2022
ms.locfileid: "67291402"
---
# <a name="configure-direct-routing"></a>Configurare Instradamento diretto

Direct Routing consente di connettere l'infrastruttura di telefonia locale a Microsoft Teams. L'articolo elenca i passaggi di alto livello necessari per connettere un controller SBC (Session Border Controller) locale supportato al routing diretto e come configurare gli utenti di Teams per l'uso del routing diretto per la connessione alla rete PSTN (Public Switched Telephone Network). Questo articolo contiene collegamenti ad articoli associati per informazioni dettagliate.  

Per informazioni sulla scelta del routing diretto come soluzione adatta per l'organizzazione, vedere [Opzioni di connettività PSTN](pstn-connectivity.md). Per informazioni sui prerequisiti e sulla pianificazione della distribuzione, vedere [Pianificare il routing diretto](direct-routing-plan.md).

Per completare i passaggi descritti in questo articolo, gli amministratori devono avere familiarità con i cmdlet di PowerShell. Per altre informazioni sull'uso di PowerShell, vedere [Configurare il computer per Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Prima di eseguire i passaggi descritti in questi articoli, Microsoft consiglia di confermare che il servizio SBC è già stato configurato come consigliato dal fornitore di SBC: 

- [Documentazione sulla distribuzione AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentazione relativa alla distribuzione di Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentazione sulla distribuzione di comunicazioni sulla barra multifunzione](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentazione sulla distribuzione di TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentazione sulla distribuzione di Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Per un elenco completo degli SBC supportati, vedi [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).

Per configurare Sistema telefonico e consentire agli utenti di utilizzare l'instradamento diretto, attenersi alla seguente procedura: 

- **Passaggio 1.** [Connettere SBC con sistema telefonico e convalidare la connessione](direct-routing-connect-the-sbc.md)
- **Passaggio 2.** [Abilitare gli utenti per routing diretto, voce e segreteria telefonica](direct-routing-enable-users.md)
- **Passaggio 3.** [Configurare il routing delle chiamate](direct-routing-voice-routing.md)
- **Passaggio 4.** [Tradurre numeri in un formato alternativo](direct-routing-translate-numbers.md) 

Se si sta configurando una scheda SBC per più tenant, è consigliabile leggere anche [Configurare una scheda SBC per più tenant](direct-routing-sbc-multiple-tenants.md).

## <a name="support-boundaries"></a>Limiti del supporto
Microsoft supporta solo un sistema telefonico con instradamento diretto se usato con dispositivi certificati. In caso di problemi, è necessario contattare prima il supporto tecnico del fornitore di SBC. Se necessario, il fornitore SBC invierà il problema a Microsoft tramite canali interni. Microsoft si riserva il diritto di rifiutare i casi di supporto in cui un dispositivo non certificato è connesso al sistema telefonico tramite instradamento diretto. Se Microsoft determina che il problema di instradamento diretto di un cliente riguarda un dispositivo SBC di un fornitore, il cliente dovrà contattare nuovamente il fornitore SBC per ricevere supporto.

## <a name="related-topics"></a>Argomenti correlati

[Pianificare la soluzione vocale](cloud-voice-landing-page.md)

[Opzioni di connettività PSTN](pstn-connectivity.md)

[Pianificare Instradamento diretto](direct-routing-plan.md)
