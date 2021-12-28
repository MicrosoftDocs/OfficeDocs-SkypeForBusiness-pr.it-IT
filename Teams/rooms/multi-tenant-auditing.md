---
title: Controllo multi-tenant
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Registrazione di controllo per TRM.
f1keywords: ''
ms.openlocfilehash: bb002ad546553e906339b03ff7b36ff2ccce8506
ms.sourcegitcommit: 848e462c4f0c94548d3f90f28fb1c69a9bce64be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/28/2021
ms.locfileid: "61620530"
---
# <a name="audit-logging-in-the-teams-rooms-managed-service"></a>Registrazione di controllo nel servizio Teams Rooms gestito

Il servizio Teams Rooms Managed (TRM) consente di cercare i record di controllo per le attività eseguite nel portale da utenti e amministratori. Questa funzionalità è abilitata per impostazione predefinita. Solo l'amministratore del servizio gestito ha l'autorizzazione per esportare e quindi visualizzare i log.

> [!NOTE]
> Le azioni eseguite nel servizio TRM non vengono registrate Microsoft 365 o Office 365 controllo 

## <a name="exporting-logs"></a>Esportazione dei log

Quando si esportano tutti i risultati di una ricerca nel log di controllo, i dati non elaborati del log di controllo unificato vengono copiati in un file con valori delimitati da virgole (CSV) scaricato nel computer locale. 

**Per scaricare i log** 

1. Passare a **Impostazioni > generale > di controllo**.
1. Per definire l'intervallo di date per i registri di interesse, immettere **la data di inizio** e la data di **fine.**

   > [!NOTE]
   > I log sono disponibili solo per un massimo di 180 giorni.

1. Selezionare **Scarica log.**

   ![Intervallo di date del log di controllo](../media/multi-tenant-auditing.png)

   Un messaggio visualizzato nella parte inferiore della finestra chiede di aprire o salvare il file CSV. 

1. Selezionare   >  **Salva con nome** e salvare il file CSV nel computer locale. 

1. Il download di molti risultati della ricerca richiede del tempo durante la ricerca di tutte le attività o in un intervallo di date ampio. Al termine del download del file CSV, viene visualizzato un messaggio nella parte inferiore della finestra.

## <a name="detailed-properties-in-the-audit-log"></a>Proprietà dettagliate nel log di controllo

La tabella seguente descrive le proprietà incluse nel file CSV.

|Proprietà|Descrizione|
| - | - |
|activity.category|<p>Categoria dell'oggetto su cui è stata eseguita l'azione. Valori possibili:</p><p>**Utente, Attività, PartnerInvitation, Ruolo**</p>|
|activity.objectName|Nome dell'oggetto modificato.|
|activity.operation|Tipo di operazione eseguita. I valori possibili sono: **Crea, Aggiorna, Elimina** |
|activity.resultStatus|<p>Indica se l'azione (specificata nella **proprietà activity.operation)** ha avuto esito positivo o meno.</p><p>Il valore è **Operazione riuscita** o **Non riuscita.**</p>|
|activity.tenantId|GUID del tenant in cui è stata eseguita l'azione|
|creationTime|Data e ora in formato UTC (Coordinated Universal Time) nel formato ISO quando l'utente ha eseguito l'attività.|
|user.userId|Utente che ha eseguito l'azione che ha comportato la registrazione del record.|
|user.userTenantId|GUID del tenant per l'utente che ha eseguito l'azione|


