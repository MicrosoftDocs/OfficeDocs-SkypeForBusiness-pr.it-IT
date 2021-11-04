---
title: Script di PowerShell per testare le connessioni di Direct Routing Session Border Controller
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Usare questo esempio di script di PowerShell per testare le connessioni di Direct Routing Session Border Controller in Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: acba1d06debc9a0e06ee6636e14ee5cbf15bd90f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774406"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script di PowerShell per testare le connessioni di Direct Routing Session Border Controller

Il client tester SIP è uno script di PowerShell di esempio che è possibile usare per testare le connessioni SBC (Direct Routing Session Border Controller) in Microsoft Teams. Questo script verifica le funzionalità di base di un trunk SIP (Session Initiation Protocol) associato al cliente con il routing diretto.

Lo script invia un test SIP al test runner, attende il risultato e lo presenta in un formato leggibile. È possibile usare questo script per testare gli scenari seguenti:

- Chiamate in uscita e in ingresso
- Anello simultaneo
- Escalation multimediale
- Trasferimento consultivo

## <a name="download-the-script-and-documentation"></a>Scaricare lo script e la documentazione

Scaricare lo [script client SIP Tester e la documentazione](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).

  > [!NOTE]
  > Lo script client tester SIP supporta solo adal.ps versione 3.19.8.1. Se si usa una versione successiva del adal.ps viene restituito un errore.
  
  
