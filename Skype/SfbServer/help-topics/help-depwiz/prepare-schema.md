---
title: Preparare lo schema
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Per preparare lo schema per Servizi di dominio Active Directory, eseguire il passaggio Preparare lo schema nella Skype for Business Server guidata. Fare clic su Esegui per avviare la preparazione dello schema. Il passaggio Prepare Schema consente di leggere i file di definizione dello schema forniti nella directory /Program Files/Microsoft Lync Server 2013/Deployment/Setup nel sistema in cui è in esecuzione la Distribuzione guidata. Questi file sono disponibili anche nel supporto di installazione nella directory Support/Schema. Nel corso del passaggio di preparazione dello schema, quest'ultimo verrà esteso e verrà segnalato lo stato del processo. Verrà inoltre notificato il completamento del processo. La schermata di riepilogo consentirà di visualizzare i registri del processo. Esaminare tali registri per accertarsi che la preparazione sia stata completata correttamente.
ms.openlocfilehash: 162937b56a4acc91c3fef70712feb713547cd2e2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402260"
---
# <a name="prepare-schema"></a>Preparare lo schema
 
Per preparare lo schema per Servizi di dominio Active Directory, eseguire il passaggio Preparare lo schema nella Skype for Business Server guidata. Fare clic su **Esegui** per avviare la preparazione dello schema. Il passaggio Prepare Schema legge i file di definizione dello schema forniti nella directory \Programmi\Microsoft Lync Server 2013\Deployment\Setup nel sistema in cui è in esecuzione la Distribuzione guidata. Tali file sono inoltre disponibili nella directory \Support\Schema dei supporti di installazione. Nel corso del passaggio di preparazione dello schema, quest'ultimo verrà esteso e verrà segnalato lo stato del processo. Verrà inoltre notificato il completamento del processo. La schermata di riepilogo consentirà di visualizzare i registri del processo. Esaminare tali registri per accertarsi che la preparazione sia stata completata correttamente.
  
> [!IMPORTANT]
> Per estendere lo schema, è necessario essere connessi al dominio come membri del gruppo Schema Admins e del gruppo Enterprise Admins. 
  
Vengono aggiunte classi e attributi per estendere lo schema di Servizi di dominio Active Directory per supportare Skype for Business Server oggetti server, servizio e utente di Active Directory 2015. Prima di estendere lo schema, è consigliabile effettuare un backup dello stato del sistema per il controller di dominio con il ruolo master schema. Per informazioni dettagliate sul processo di backup per Windows Server 2008 R2 con SP1, vedere [https://go.microsoft.com/fwlink/p/?linkId=207198](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee849849(v=ws.10)). Per Windows Server 2003 e Windows Server 2003 R2, vedere [https://go.microsoft.com/fwlink/p/?linkId=207199](/previous-versions/windows/it-pro/windows-server-2003/cc787254(v=ws.10)).
  
> [!CAUTION]
> L'estensione dello schema non è un'operazione reversibile. È consigliabile fare tutti gli sforzi possibili per limitare il potenziale impatto di un'estensione dello schema non riuscita e per garantire che l'estensione dello schema avrà esito positivo. Ciò è particolarmente importante in caso di perdita di comunicazione o di qualsiasi altro errore nel server. È consigliabile eseguire un backup del controller di dominio master schema e un backup completo di Active Directory. 
  
Per eseguire un backup del controller di dominio master schema e un backup completo di Active Directory:
  
1. Disconnettere dalla rete il controller di dominio con il ruolo master schema.
    
2. Effettuare un backup dello stato del sistema per il controller di dominio con il master schema.
    
3. Estendere lo schema.
    
4. Quando l'estensione dello schema ha esito positivo, riconnettere il controller di dominio alla rete e verificare che la replica sia attiva e funzionante.
    
5. Nel caso improbabile di un errore di estensione dello schema, ripristinare lo stato del sistema del controller di dominio e di Active Directory utilizzando il backup dello stato del sistema eseguito in precedenza.
    
> [!NOTE]
> Se è necessario esaminare i file di registro creati dalla Distribuzione guidata di Skype for Business Server, è possibile trovare i file nel computer in cui è stata eseguita la Distribuzione guidata nella directory Utenti dell'utente di Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha eseguito l'accesso come amministratore di dominio nel Contoso.net di dominio, i file di registro si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp 
