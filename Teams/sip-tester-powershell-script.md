---
title: Script di PowerShell per testare le connessioni di Direct Routing Session Border Controller
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Usare questo esempio di script di PowerShell per testare le connessioni di Direct Routing Session Border Controller in Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834276"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script di PowerShell per testare le connessioni di Direct Routing Session Border Controller

Il client tester SIP è uno script di PowerShell di esempio che è possibile usare per testare le connessioni SBC (Direct Routing Session Border Controller) in Microsoft Teams. Questo script verifica le funzionalità di base di un trunk SIP (Session Initiation Protocol) associato al cliente con il routing diretto.

Lo script invia un test SIP al test runner, attende il risultato e lo presenta in un formato leggibile. È possibile usare questo script per testare gli scenari seguenti:

- Chiamate in uscita e in ingresso
- Anello simultaneo
- Escalation multimediale
- Trasferimento consultivo

## <a name="download-the-script-and-documentation"></a>Scaricare lo script e la documentazione

Scaricare lo [script client SIP Tester e la documentazione.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)

  > [!NOTE]
  > Lo script client di Tester SIP supporta solo adal.ps versione 3.19.8.1. Se viene usata una versione successiva del adal.ps viene restituito un errore.
  
  
