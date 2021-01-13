---
title: Preparare lo schema
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Per preparare lo schema per i servizi di dominio Active Directory, è necessario eseguire il passaggio Prepara schema nella distribuzione guidata di Skype for Business Server. Fare clic su Esegui per avviare la preparazione dello schema.
ms.openlocfilehash: b666cda29267c6f74eb034389f3f7967d7af99c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833776"
---
# <a name="prepare-schema"></a>Preparare lo schema
 
Per preparare lo schema per i servizi di dominio Active Directory, è necessario eseguire il passaggio Prepara schema nella distribuzione guidata di Skype for Business Server. Fare clic su **Esegui** per avviare la preparazione dello schema. Il passaggio di preparazione dello schema consente di leggere i file di definizione dello schema forniti nella directory \Program Skype for Business Server 2019 \ Deployment\Setup del sistema in cui è in esecuzione la distribuzione guidata. Tali file sono inoltre disponibili nella directory \Support\Schema dei supporti di installazione. Nel corso del passaggio di preparazione dello schema, quest'ultimo verrà esteso e verrà segnalato lo stato del processo. Verrà inoltre notificato il completamento del processo. La schermata di riepilogo consentirà di visualizzare i registri del processo. Esaminare tali registri per accertarsi che la preparazione sia stata completata correttamente.
  
> [!IMPORTANT]
> Per estendere lo schema, è necessario essere connessi al dominio come membri del gruppo Schema Admins e del gruppo Enterprise Admins. 
  
Sono state aggiunte classi e attributi per estendere lo schema dei servizi di dominio Active Directory al supporto degli oggetti server, del servizio e degli utenti di Skype for Business Server. Prima di estendere lo schema, è consigliabile effettuare un backup dello stato del sistema per il controller di dominio con il ruolo master schema. 
  
> [!CAUTION]
> L'estensione dello schema non è un'operazione reversibile. È consigliabile eseguire tutti gli sforzi possibili per limitare l'impatto potenziale di un'estensione dello schema con esito negativo e per garantire che l'estensione dello schema abbia esito positivo. Questo è particolarmente importante in caso di perdita della comunicazione o di qualsiasi altro errore sul server. È consigliabile eseguire un backup del controller di dominio master schema e un backup completo di Active Directory. 
  
Per eseguire un backup del controller di dominio master schema e di un backup completo di Active Directory:
  
1. Disconnettere dalla rete il controller di dominio con il ruolo master schema.
    
2. Effettuare un backup dello stato del sistema per il controller di dominio con il master schema.
    
3. Estendere lo schema.
    
4. Quando l'estensione dello schema ha esito positivo, riconnettere il controller di dominio alla rete e verificare che la replica sia attiva e funzionante.
    
5. Nell'improbabile eventualità di un'estensione dello schema, ripristinare lo stato dei sistemi del controller di dominio e Active Directory utilizzando il backup dello stato del sistema eseguito precedentemente.
    
> [!NOTE]
> Se è necessario controllare i file di registro creati dalla distribuzione guidata di Skype for Business Server, è possibile trovare i file nel computer in cui è stata eseguita la distribuzione guidata, nella directory degli utenti dell'utente di Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha effettuato l'accesso come amministratore del dominio nel dominio Contoso.net, i file di registro sono disponibili in: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

