---
title: Configurare il bypass multimediale con Instradamento diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come configurare il bypass multimediale con Sistema telefonico routing diretto per Microsoft Teams passando da un utente all'altro contemporaneamente o implementando un approccio graduale (scelta consigliata).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dcbc893d3549e491d40268ae3417f5203d755ff6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598580"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurare il bypass multimediale con Instradamento diretto

Prima di configurare il bypass multimediale con Il routing diretto, assicurarsi di aver letto Pianificare [il bypass multimediale con Routing diretto.](direct-routing-plan-media-bypass.md)

Per attivare il bypass multimediale, è necessario che siano soddisfatte le condizioni seguenti:

1.    Assicurarsi che il fornitore di session border controller (SBC) scelto supporti il bypass multimediale e fornisce istruzioni su come configurare il bypass nel controller SBC. Fare riferimento alla pagina di certificazione per informazioni sugli SBC, su quelli che supportano il bypass multimediale e per istruzioni.

2.    È necessario attivare il bypass multimediale nel trunk usando il comando seguente:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.

3.    Assicurarsi che le porte richieste siano aperte. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Eseguire la migrazione da trunk non bypassati a trunk abilitati per bypass

È possibile cambiare tutti gli utenti contemporaneamente oppure implementare un approccio graduale (scelta consigliata).

- **Cambiare tutti gli utenti contemporaneamente.** Se vengono soddisfatte tutte le condizioni, è possibile attivare la modalità di bypass. Tuttavia, tutti gli utenti di produzione verranno commutati contemporaneamente. Poiché inizialmente potrebbero verificarsi alcuni problemi durante la configurazione di trunk e porte, l'esperienza utente di produzione potrebbe essere interessata. 

- **Approccio a fasi. (Scelta consigliata)**.  Creare un nuovo trunk per lo stesso SBC (con una porta diversa), testarlo e modificare i criteri di routing vocale online in modo che gli utenti puntino al nuovo trunk. 

  Questo è l'approccio consigliato perché consente una transizione più fluida e un'esperienza utente ininterrotta. Questo approccio richiede la configurazione del SBC, un nuovo nome FQDN e la configurazione del firewall. Si noti che è necessario assicurarsi che il certificato supporti entrambi i trunk. Nella rete SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o avere un certificato con caratteri jolly.

![Eseguire la migrazione da trunk non bypassati a trunk abilitati per bypass)](media/direct-routing-media-bypass-8.png)

Per istruzioni su come configurare i trunk ed eseguire la migrazione, vedere la documentazione del fornitore SBC:

- [Documentazione sulla distribuzione di AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentazione sulla distribuzione Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentazione sulla distribuzione di Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentazione sulla distribuzione di TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Per un elenco dei session border controller (SBC) certificati per il routing diretto, vedere Elenco dei controller di sessione certificati [per il routing diretto.](direct-routing-border-controllers.md)



## <a name="related-topics"></a>Argomenti correlati

[Pianificare il bypass multimediale con Routing diretto](direct-routing-plan-media-bypass.md)



