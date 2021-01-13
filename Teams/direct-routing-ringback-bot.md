---
title: Configurare la risponderia per il routing diretto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Informazioni su come usare la risponderia per il routing diretto per evitare silenzi imprevisti che si verificano quando viene stabilita una chiamata.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91cea9183a85a804ca43464aab08f417ccaff1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827516"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurare la risponderia per il routing diretto

In questo articolo vengono illustrate le risponderie, che è possibile usare per evitare silenzi imprevisti che possono verificarsi quando richiede più tempo per stabilire le chiamate. La risponderia è disponibile per il routing diretto in modalità bypass non multimediale.

A volte le chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network) ai client teams possono richiedere più tempo del previsto. Questo problema può verificarsi per diversi motivi. In questo caso, il chiamante potrebbe non sentire nulla, il client teams non squilla e alcuni provider di telecomunicazioni potrebbero annullare la chiamata.

La risponderia bot aiuta ad evitare silenzi imprevisti che possono verificarsi in questo scenario. Per le chiamate in ingresso dalla rete PSTN ai client teams, la risponderia riproduce un segnale audio distintivo per il chiamante per indicare che il team sta per stabilire la chiamata.

> [!NOTE]
> La risponderia genera elementi multimediali iniziali dal backend teams. In alcuni paesi e aree geografiche potrebbe essere addebitata la chiamata quando viene avviato il flusso multimediale.

## <a name="configure-the-ringback-bot"></a>Configurare le risponderie

Usa il cmdlet [set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) per modificare una configurazione di Session Border Controller (SBC) in precedenza definita o il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) per creare una nuova configurazione SBC, insieme al parametro **GenerateRingingWhileLocatingUser** per configurare la risponderia:

- Per attivare la risponderie, imposta il parametro **GenerateRingingWhileLocatingUser** su **$true**. Questo è il valore predefinito. 

- Per disattivare la risponderia bot, imposta il parametro **GenerateRingingWhileLocatingUser** su **$false**. 

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
