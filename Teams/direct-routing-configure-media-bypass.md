---
title: Configurare il bypass multimediale con Instradamento diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
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
description: Scopri come configurare il bypass multimediale con il routing diretto del sistema telefonico per Microsoft Teams passando contemporaneamente a tutti gli utenti o implementando un approccio a fasi (scelta consigliata).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416896"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurare il bypass multimediale con Instradamento diretto

Prima di configurare il bypass multimediale con il routing diretto, assicurarsi di avere letto [Pianificare il bypass multimediale con Routing diretto.](direct-routing-plan-media-bypass.md)

Per attivare il bypass multimediale, è necessario che siano soddisfatte le condizioni seguenti:

1.    Assicurarsi che il proprio fornitore di Session Border Controller (SBC) supporti il bypass multimediale e fornisce istruzioni su come configurare il bypass sul controller SBC. Per istruzioni, consulta la pagina di certificazione per informazioni su SBC, che supportano il bypass multimediale.

2.    È necessario attivare il bypass multimediale sul trunk con il comando seguente: **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true.**

3.    Assicurarsi che le porte richieste siano aperte. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Eseguire la migrazione da trunk non bypassati a trunk abilitati per bypass

È possibile cambiare tutti gli utenti contemporaneamente oppure implementare un approccio a fasi (scelta consigliata).

- **Cambiare tutti gli utenti contemporaneamente.** Se vengono soddisfatte tutte le condizioni, è possibile attivare la modalità bypass. Tuttavia, tutti gli utenti di produzione verranno alternati contemporaneamente. Poiché inizialmente potrebbero verificarsi alcuni problemi durante la configurazione di trunk e porte, l'esperienza utente di produzione potrebbe risultare interessata. 

- **Approccio a fasi. (Scelta consigliata).**  Creare un nuovo trunk per lo stesso SBC (con una porta diversa), testarlo e modificare i criteri di routing vocale online in modo che gli utenti puntino al nuovo trunk. 

  Questo è l'approccio consigliato perché consente una transizione più fluida e un'esperienza utente senza interruzioni. Questo approccio richiede la configurazione del servizio SBC, di un nuovo nome FQDN e della configurazione del firewall. Tenere presente che è necessario verificare che il certificato supporti entrambi i trunk. In SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o un certificato con caratteri jolly.

![Eseguire la migrazione da trunk non bypassati a trunk abilitati per bypass)](media/direct-routing-media-bypass-8.png)

Per istruzioni su come configurare i trunk ed eseguire la migrazione, vedere la documentazione del fornitore di SBC:

- [Documentazione sulla distribuzione di AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentazione della distribuzione Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentazione sulla distribuzione di Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentazione sulla distribuzione di TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Per un elenco dei controller dei confini della sessione (SBC) certificati per l'instradamento diretto, vedere l'elenco dei controller di bordo di sessione certificati per [l'instradamento diretto.](direct-routing-border-controllers.md)



## <a name="related-topics"></a>Argomenti correlati

[Pianificare il bypass multimediale con l'instradamento diretto](direct-routing-plan-media-bypass.md)



