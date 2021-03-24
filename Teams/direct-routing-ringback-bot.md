---
title: Configurare il bot Ringback per l'instradamento diretto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Informazioni su come usare il bot Ringback per l'instradamento diretto per evitare silenzi imprevisti che possono verificarsi quando viene stabilita una chiamata.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec53f1d4f9cd21d3b28c87c07c1bc91d48b9b58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098422"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurare il bot Ringback per l'instradamento diretto

Questo articolo descrive il bot Ringback, che è possibile usare per evitare silenzi imprevisti che possono verificarsi quando le chiamate devono essere stabilite più a lungo. Il bot Ringback è disponibile per il routing diretto in modalità di bypass non multimediale.

A volte le chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network) ai client di Teams possono richiedere più tempo del previsto. Questo problema può verificarsi per vari motivi. In questo caso, il chiamante potrebbe non sentire nulla, il client teams non squilla e alcuni provider di telecomunicazioni potrebbero annullare la chiamata.

Il bot Ringback consente di evitare silenzi imprevisti che possono verificarsi in questo scenario. Per le chiamate in ingresso dai client PSTN a Teams, il bot Ringback riproduce un segnale audio distintivo per il chiamante per indicare che Teams è in corso di definizione della chiamata.

> [!NOTE]
> Il bot Ringback genera elementi multimediali iniziali dal back-end di Teams. In alcuni paesi e aree geografiche potrebbe essere addebitato l'addebito per la chiamata all'avvio del flusso multimediale.

## <a name="configure-the-ringback-bot"></a>Configurare il bot Ringback

Usare il cmdlet [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) per modificare una configurazione SBC (Session Border Controller) definita in precedenza oppure il cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) per creare una nuova configurazione SBC, insieme al parametro **GenerateRingingWhileLocatingUser** per configurare il bot Ringback:

- Per attivare il bot Ringback, impostare il **parametro GenerateRingingWhileLocatingUser** **su $True**. Questo è il valore predefinito. 

- Per disattivare il bot Ringback, impostare il **parametro GenerateRingingWhileLocatingUser** **su $False**. 

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)