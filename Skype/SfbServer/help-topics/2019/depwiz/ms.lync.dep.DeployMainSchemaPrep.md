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
description: Per preparare lo schema per Servizi di dominio Active Directory, eseguire il passaggio Preparare lo schema nella Skype for Business Server guidata. Fare clic su Esegui per avviare la preparazione dello schema.
ms.openlocfilehash: d2dfd0525d0ec1fa1ee46479194b029b1db591781303436f008ed5d3900f01be
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340122"
---
# <a name="prepare-schema"></a>Preparare lo schema
 
Per preparare lo schema per Servizi di dominio Active Directory, eseguire il passaggio Preparare lo schema nella Skype for Business Server guidata. Fare clic su **Esegui** per avviare la preparazione dello schema. Il passaggio Prepare Schema legge i file di definizione dello schema forniti nella directory \Programmi\Skype for Business Server 2019\Deployment\Setup nel sistema in cui è in esecuzione la Distribuzione guidata. Tali file sono inoltre disponibili nella directory \Support\Schema dei supporti di installazione. Nel corso del passaggio di preparazione dello schema, quest'ultimo verrà esteso e verrà segnalato lo stato del processo. Verrà inoltre notificato il completamento del processo. La schermata di riepilogo consentirà di visualizzare i registri del processo. Esaminare tali registri per accertarsi che la preparazione sia stata completata correttamente.
  
> [!IMPORTANT]
> Per estendere lo schema, è necessario essere connessi al dominio come membri del gruppo Schema Admins e del gruppo Enterprise Admins. 
  
Le classi e gli attributi vengono aggiunti per estendere lo schema di Servizi di dominio Active Directory per supportare Skype for Business Server server, servizio e oggetti utente. Prima di estendere lo schema, è consigliabile effettuare un backup dello stato del sistema per il controller di dominio con il ruolo master schema. 
  
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
  

