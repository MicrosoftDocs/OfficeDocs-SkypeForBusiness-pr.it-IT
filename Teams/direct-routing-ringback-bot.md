---
title: Configurare il bot Ringback per il routing diretto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Scopri come usare il bot Ringback per l'instradamento diretto per evitare silenzi imprevisti che possono verificarsi durante la chiamata.
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
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurare il bot Ringback per il routing diretto

Questo articolo descrive il bot di Ringback, che puoi usare per evitare silenzi imprevisti che possono verificarsi quando l'esecuzione delle chiamate richiede più tempo. Il bot Ringback è disponibile per il routing diretto in modalità di bypass non multimediale.

A volte le chiamate in ingresso dalla rete PSTN (Public Switched Telephone Network) ai client Teams possono richiedere più tempo del previsto. Questo problema può verificarsi per vari motivi. In questo caso, il chiamante potrebbe non sentire nulla, il client di Teams non squilla e alcuni provider di telecomunicazioni potrebbero annullare la chiamata.

Il bot Ringback consente di evitare silenzi imprevisti che possono verificarsi in questo scenario. Per le chiamate in entrata dalla rete PSTN ai client di Teams, il bot Ringback riproduce un segnale audio distintivo per il chiamante, per indicare che Teams è in corso di definizione della chiamata.

> [!NOTE]
> Il bot Ringback genera contenuti multimediali iniziali dal back-end di Teams. In alcuni paesi e aree geografiche, l'addebito per la chiamata potrebbe essere addebitato all'inizio del flusso degli elementi multimediali.

## <a name="configure-the-ringback-bot"></a>Configurare il bot Ringback

Usa il cmdlet [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) per modificare una configurazione SBC (Session Border Controller) definita in precedenza oppure il cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) per creare una nuova configurazione SBC, insieme al parametro **GenerateRingingWhileLocatingUser** per configurare il bot di Ringback:

- Per attivare il bot Ringback, impostare il **parametro GenerateRingingWhileLocatingUser** **su $True.** Questo è il valore predefinito. 

- Per disattivare il bot Ringback, impostare il **parametro GenerateRingingWhileLocatingUser** **su $False.** 

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
