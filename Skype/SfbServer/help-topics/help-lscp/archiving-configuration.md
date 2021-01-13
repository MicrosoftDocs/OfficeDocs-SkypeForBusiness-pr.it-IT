---
title: Configurazione archiviazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: "È possibile utilizzare le configurazioni di archiviazione per controllare le opzioni di archiviazione per la distribuzione di Skype for Business Server, inclusa l'abilitazione e la disabilitazione delle opzioni seguenti:"
ms.openlocfilehash: 96a01579f43833017978fc6067b5a86f9e9951aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827006"
---
# <a name="archiving-configuration"></a>Configurazione archiviazione
 
È possibile utilizzare le configurazioni di archiviazione per controllare le opzioni di archiviazione per la distribuzione di Skype for Business Server, inclusa l'abilitazione e la disabilitazione delle opzioni seguenti:
  
- Blocco delle sessioni di messaggistica istantanea o di conferenza se l'archiviazione ha esito negativo
    
- Integrazione con l'archiviazione di Exchange 2013, per gli utenti ospitati in Exchange 2013
    
- Eliminazione dei dati archiviati
    
Le configurazioni di archiviazione includono la configurazione globale e, facoltativamente, una o più configurazioni di archiviazione per sito e pool:
  
- **Configurazione globale** La configurazione globale viene creata per impostazione predefinita in tutte le distribuzioni di Skype for Business Server. È possibile modificare la configurazione globale, ma non è possibile eliminare la configurazione di archiviazione. Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.
    
- **Configurazione del sito (facoltativo)** È possibile specificare una o più configurazioni di archiviazione siti, ognuna delle quali può essere configurata per controllare le opzioni di archiviazione per un sito specifico. La configurazione di un sito sostituisce la configurazione globale, ma solo per i siti specificati nelle configurazioni del sito di archiviazione. È possibile modificare o eliminare le configurazioni di sito.
    
- **Configurazione del pool (facoltativa)** È possibile specificare una o più configurazioni di archiviazione pool per controllare le opzioni di archiviazione per un pool specifico. La configurazione del pool sostituisce la configurazione globale e la configurazione del sito, ma solo per i pool specificati nelle configurazioni del pool di archiviazione. È possibile modificare o eliminare le configurazioni del pool.
    
> [!NOTE]
> Le configurazioni di archiviazione si applicano agli utenti ospitati su Skype for Business Server e, se si utilizza Exchange per archiviare i dati di archiviazione in Microsoft Exchange, per gli utenti ospitati in Exchange 2013 ma vengono implementati in modo leggermente diverso per gli utenti ospitati in Exchange 2013. Le differenze sono descritte nella sezione successiva. 
  
Nella pagina **Configurazione archiviazione** sono elencati tutti i criteri di archiviazione configurati per la distribuzione. Viene inoltre visualizzato il nome del criterio, l'ambito (globale, sito o pool) e quali opzioni di archiviazione sono abilitate per ogni configurazione di archiviazione. Nella pagina **Configurazione archiviazione** sono disponibili le opzioni seguenti:
- **Nuovo** È possibile aggiungere una o più delle seguenti configurazioni di archiviazione facoltative.
    
  - Configurazione del sito
    
  - Configurazione del pool
    
- **Modifica** È possibile modificare le opzioni di tutte le configurazioni di archiviazione elencate nella pagina. Usando questa voce, è possibile scegliere tra le opzioni seguenti:
    
  - **Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni di archiviazione per la configurazione di archiviazione selezionata. È possibile visualizzare solo i dettagli per una configurazione di archiviazione alla volta.
    
  - **Seleziona tutto** Questa opzione consente di selezionare tutte le configurazioni di archiviazione nell'elenco.
    
  - **Eliminare** Questa opzione consente di eliminare tutte le configurazioni di archiviazione selezionate.
    
- **Azione** È possibile utilizzare questa opzione per abilitare o disabilitare rapidamente l'archiviazione delle sessioni di messaggistica istantanea o Web Conferencing in qualsiasi configurazione elencata nella pagina, anziché modificare la configurazione. Le opzioni disponibili in **azione** dipendono dall'opzione attualmente specificata nella configurazione di archiviazione. Tutte le opzioni sono disponibili, ad eccezione dell'opzione attualmente attiva per la configurazione di archiviazione. Tra le opzioni sono incluse le seguenti:
    
  - **Archivia sessioni di messaggistica istantanea**
    
  - **Archivia sessioni di messaggistica istantanea e Web Conferencing**
    
  - **Disabilita archiviazione**
    
- **Aggiorna** È possibile aggiornare la pagina **Configurazione archiviazione** per verificare lo stato delle opzioni di tutte le configurazioni di archiviazione.
    
Per informazioni dettagliate sulla funzionalità e sulle funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [Plan for archiving in Skype for Business server 2015](../../plan-your-deployment/archiving/archiving.md), [deploy Archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)e [Manage Archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).

