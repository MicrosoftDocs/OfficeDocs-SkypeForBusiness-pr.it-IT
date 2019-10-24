---
title: Script di PowerShell per testare le connessioni del controller di bordo della sessione di routing diretto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Usare questo esempio di script di PowerShell per testare le connessioni del controller di bordo della sessione di routing diretto in Microsoft teams.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6df8ee654696ceef89c36a354d943c97139bf8b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37639486"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script di PowerShell per testare le connessioni del controller di bordo della sessione di routing diretto

Il client tester SIP è uno script di PowerShell di esempio che puoi usare per testare le connessioni SBC (Direct routing session border controller) in Microsoft teams. Questo script verifica le funzionalità di base di un trunk SIP (Session Initiation Protocol) associato al cliente con routing diretto.

Lo script Invia un test SIP al Runner di prova, attende il risultato e lo presenta in un formato leggibile. Puoi usare questo script per testare gli scenari seguenti:

- Chiamate in uscita e in ingresso
- Squillo simultaneo
- Escalation multimediale
- Trasferimento consultivo

## <a name="download-the-script-and-documentation"></a>Scaricare lo script e la documentazione

Scaricare lo [script e la documentazione del client del tester SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).