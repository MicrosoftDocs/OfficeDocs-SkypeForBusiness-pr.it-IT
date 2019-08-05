---
title: Preparare uno schema
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Per preparare lo schema per i servizi di dominio Active Directory, eseguire il passaggio Prepara schema nella distribuzione guidata di Skype for Business Server. Fare clic su Esegui per avviare la preparazione dello schema.
ms.openlocfilehash: e48ae4ff28cf0423d3a29ae9f7d637cb8a58297c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191021"
---
# <a name="prepare-schema"></a>Preparare uno schema
 
Per preparare lo schema per i servizi di dominio Active Directory, eseguire il passaggio Prepara schema nella distribuzione guidata di Skype for Business Server. Fare clic su **Esegui** per avviare la preparazione dello schema. Il passaggio Preparazione schema legge i file di definizione dello schema forniti nella directory \Program Skype for Business Server 2019 \ Deployment\Setup nel sistema in cui è in corso la distribuzione guidata. Tali file sono inoltre disponibili nella directory \Support\Schema dei supporti di installazione. Nel corso del passaggio di preparazione dello schema, quest'ultimo verrà esteso e verrà segnalato lo stato del processo. Verrà inoltre notificato il completamento del processo. La schermata di riepilogo consentirà di visualizzare i registri del processo. Esaminare tali registri per accertarsi che la preparazione sia stata completata correttamente.
  
> [!IMPORTANT]
> Per estendere lo schema, è necessario essere connessi al dominio come membri del gruppo Schema Admins e del gruppo Enterprise Admins. 
  
Le classi e gli attributi vengono aggiunti per estendere lo schema dei servizi di dominio Active Directory per supportare gli oggetti server, servizio e utenti di Skype for Business Server. Prima di estendere lo schema, è consigliabile effettuare un backup dello stato del sistema per il controller di dominio con il ruolo master schema. 
  
> [!CAUTION]
> L'estensione dello schema non è reversibile. È consigliabile eseguire tutte le operazioni possibili per limitare l'impatto potenziale di un'estensione di schema non riuscita e per assicurarsi che l'estensione dello schema abbia successo. Questo è particolarmente importante in caso di perdita di comunicazioni o di qualsiasi altro errore nel server. È consigliabile eseguire un backup del controller di dominio master schema e un backup completo di Active Directory. 
  
Per eseguire un backup del controller di dominio master schema e un backup completo di Active Directory:
  
1. Disconnettere dalla rete il controller di dominio con il ruolo master schema.
    
2. Effettuare un backup dello stato del sistema per il controller di dominio con il master schema.
    
3. Estendere lo schema.
    
4. Quando l'estensione dello schema ha esito positivo, riconnettere il controller di dominio alla rete e verificare che la replica sia attiva e funzionante.
    
5. Nell'eventualità di un errore di estensione dello schema, ripristinare lo stato dei sistemi del controller di dominio e di Active Directory usando il backup dello stato del sistema adottato in precedenza.
    
> [!NOTE]
> Se è necessario rivedere i file di log creati dalla distribuzione guidata di Skype for Business Server, è possibile trovare i file nel computer in cui è stata eseguita la distribuzione guidata, nella directory utenti dell'utente di Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha effettuato l'accesso come amministratore del dominio nel dominio Contoso.net, i file di log si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

