---
title: Preparare lo schema
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Per preparare lo schema per Servizi di dominio Active Directory, eseguire il passaggio Preparazione schema nella Distribuzione guidata di Skype for Business Server. Fare clic su Esegui per avviare la preparazione dello schema. Il passaggio Prepare Schema legge i file di definizione dello schema forniti nella directory /Program Files/Microsoft Lync Server 2013/Deployment/Setup nel sistema in cui viene eseguita la Distribuzione guidata. Questi file sono disponibili anche nel supporto di installazione nella directory Support/Schema. Nel corso del passaggio di preparazione dello schema, quest'ultimo verrà esteso e verrà segnalato lo stato del processo. Verrà inoltre notificato il completamento del processo. La schermata di riepilogo consentirà di visualizzare i registri del processo. Esaminare tali registri per accertarsi che la preparazione sia stata completata correttamente.
ms.openlocfilehash: c6c29dfd8e9b0908091e61a569ca56a467a014d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829796"
---
# <a name="prepare-schema"></a>Preparare lo schema
 
Per preparare lo schema per Servizi di dominio Active Directory, eseguire il passaggio Preparazione schema nella Distribuzione guidata di Skype for Business Server. Fare clic su **Esegui** per avviare la preparazione dello schema. Il passaggio Preparazione schema legge i file di definizione dello schema forniti nella directory \Programmi\Microsoft Lync Server 2013\Deployment\Setup nel sistema in cui viene eseguita la Distribuzione guidata. Tali file sono inoltre disponibili nella directory \Support\Schema dei supporti di installazione. Nel corso del passaggio di preparazione dello schema, quest'ultimo verrà esteso e verrà segnalato lo stato del processo. Verrà inoltre notificato il completamento del processo. La schermata di riepilogo consentirà di visualizzare i registri del processo. Esaminare tali registri per accertarsi che la preparazione sia stata completata correttamente.
  
> [!IMPORTANT]
> Per estendere lo schema, è necessario essere connessi al dominio come membri del gruppo Schema Admins e del gruppo Enterprise Admins. 
  
Vengono aggiunti classi e attributi per estendere lo schema di Servizi di dominio Active Directory per supportare gli oggetti server, servizio e utente di Skype for Business Server 2015. Prima di estendere lo schema, è consigliabile effettuare un backup dello stato del sistema per il controller di dominio con il ruolo master schema. Per informazioni dettagliate sul processo di backup per Windows Server 2008 R2 con SP1, vedere [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198) . Per Windows Server 2003 e Windows Server 2003 R2, vedere [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199) .
  
> [!CAUTION]
> L'estensione dello schema non è un'operazione reversibile. È consigliabile fare tutto il possibile per limitare il potenziale impatto di un'estensione dello schema non riuscita e per garantire che l'estensione dello schema avrà esito positivo. Ciò è particolarmente importante in caso di perdita di comunicazione o di qualsiasi altro errore nel server. È consigliabile eseguire un backup del controller di dominio master schema e un backup completo di Active Directory. 
  
Per eseguire un backup del controller di dominio master schema e un backup completo di Active Directory:
  
1. Disconnettere dalla rete il controller di dominio con il ruolo master schema.
    
2. Effettuare un backup dello stato del sistema per il controller di dominio con il master schema.
    
3. Estendere lo schema.
    
4. Quando l'estensione dello schema ha esito positivo, riconnettere il controller di dominio alla rete e verificare che la replica sia attiva e funzionante.
    
5. Nell'improbabile eventualità di un errore di estensione dello schema, ripristinare lo stato del sistema del controller di dominio e di Active Directory utilizzando il backup dello stato del sistema eseguito in precedenza.
    
> [!NOTE]
> Se è necessario esaminare i file di registro creati dalla Distribuzione guidata di Skype for Business Server, è possibile trovare i file nel computer in cui è stata eseguita la Distribuzione guidata, nella directory Utenti dell'utente di Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha eseguito l'accesso come amministratore di dominio nel Contoso.net di dominio, i file di registro si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

