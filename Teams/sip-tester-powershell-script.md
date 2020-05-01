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
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43d1514eff811461ac8b6ad73f7c2a215205f4e3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951261"
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

  > [!NOTE]
  > Lo script client di SIP tester supporta solo adal.ps versione 3.19.8.1. Verrà restituito un errore se viene usata una versione più recente di adal.ps.
  
  
