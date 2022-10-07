---
title: Registrazione di controllo nel portale MTR Pro
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Registrazione di controllo per il portale MTR Pro.
f1keywords: ''
ms.openlocfilehash: 0436618e257128deb38d890cb92813ae13921e7d
ms.sourcegitcommit: 64c01699022b47fdfec8dc6e2ca279e57eae3baa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2022
ms.locfileid: "68243917"
---
# <a name="audit-logging-in-the-mtr-pro-portal"></a>Registrazione di controllo nel portale MTR Pro

I log di controllo del portale MTR Pro consentono di cercare record di controllo per le attività eseguite da utenti e amministratori. Questa funzionalità è abilitata per impostazione predefinita. Solo l'amministratore del servizio gestito ha l'autorizzazione per esportare e quindi visualizzare i log.

> [!NOTE]
> Le azioni eseguite nel portale MTR Pro non vengono registrate nel controllo di Microsoft 365 o Office 365 

## <a name="exporting-logs"></a>Esportazione dei log

Quando si esportano tutti i risultati di una ricerca nel log di controllo, i dati non elaborati dal log di controllo unificato vengono copiati in un file con valori delimitati da virgole (CSV) scaricato nel computer locale. 

**Per scaricare i log** 

1. Passare a **Impostazioni > Generale > Log di controllo**.
1. Per definire l'intervallo di date per i log di interesse, immettere la **data di inizio** e la **data di fine.**

   > [!NOTE]
   > I log sono disponibili solo per un massimo di 180 giorni.

1. Selezionare **Scarica log.**

   ![Intervallo di date del log di controllo](../media/multi-tenant-auditing.png)

   Un messaggio visualizzato nella parte inferiore della finestra chiede di aprire o salvare il file CSV. 

1. Selezionare **Salva con nome** >  e salvare il file CSV nel computer locale. 

1. Il download di molti risultati della ricerca durante la ricerca di tutte le attività o in un intervallo di date esteso richiede del tempo. Al termine del download del file CSV, viene visualizzato un messaggio nella parte inferiore della finestra.

## <a name="detailed-properties-in-the-audit-log"></a>Proprietà dettagliate nel log di controllo

La tabella seguente descrive le proprietà incluse nel file CSV.

|Proprietà|Descrizione|
| - | - |
|activity.category|<p>Categoria dell'oggetto su cui è stata eseguita l'azione. Valori possibili:</p><p>**Utente, Assegnazione, PartnerInvitation, Ruolo**</p>|
|activity.objectName|Nome dell'oggetto modificato.|
|activity.operation|Tipo di operazione eseguita. I valori possibili sono: **Create, Update, Delete** |
|activity.resultStatus|<p>Indica se l'azione (specificata nella proprietà **activity.operation** ) è riuscita o meno.</p><p>Il valore è **Esito positivo** o **Non riuscito**.</p>|
|activity.tenantId|GUID del tenant su cui è stata eseguita l'azione|
|creationTime|Data e ora in formato UTC (Coordinated Universal Time) in formato ISO quando l'utente ha eseguito l'attività.|
|user.userId|Utente che ha eseguito l'azione che ha determinato la registrazione del record.|
|user.userTenantId|GUID del tenant per l'utente che ha eseguito l'azione|


