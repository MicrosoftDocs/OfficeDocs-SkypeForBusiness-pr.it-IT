---
title: Configurare la risponderia per il routing diretto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Informazioni su come usare la risponderia per il routing diretto per evitare silenzi imprevisti che si verificano quando viene stabilita una chiamata.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fcb69ba1bc612fe940054ec982eb7462c6679be
ms.sourcegitcommit: a23f45ab3a2cb7b5c279356edddf61c4030c41bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962503"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurare la risponderia per il routing diretto

In questo articolo vengono illustrate le risponderie, che è possibile usare per evitare silenzi imprevisti che possono verificarsi quando richiede più tempo per stabilire le chiamate. La risponderia è disponibile per il routing diretto in modalità bypass non multimediale.

A volte le chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network) ai client teams possono richiedere più tempo del previsto. Questo problema può verificarsi per diversi motivi. In questo caso, il chiamante potrebbe non sentire nulla, il client teams non squilla e la chiamata può essere annullata da alcuni provider di telecomunicazioni.

La risponderia bot aiuta ad evitare silenzi imprevisti che possono verificarsi in questo scenario. Per le chiamate in ingresso dalla rete PSTN ai client teams, la risponderia riproduce un segnale audio distintivo per il chiamante per indicare che il team sta per stabilire la chiamata.

> [!NOTE]
> La risponderia genera elementi multimediali iniziali dal backend teams. In alcuni paesi e aree geografiche potrebbe essere addebitata la chiamata quando viene avviato il flusso multimediale.

## <a name="configure-the-ringback-bot"></a>Configurare le risponderie

USA i cmdlet [set-CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) e [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) insieme al parametro **GenerateRingingWhileLocatingUser** per configurare la risponderia.

Per attivare la risponderie, imposta il parametro **GenerateRingingWhileLocatingUser** su **$true**. Questo è il valore predefinito. 

Per disattivare la risponderia bot, imposta il parametro **GenerateRingingWhileLocatingUser** su **$false**. 

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell Teams](teams-powershell-overview.md)