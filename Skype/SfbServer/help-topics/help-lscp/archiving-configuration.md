---
title: Configurazione archiviazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: "Puoi usare le configurazioni di archiviazione per controllare le opzioni di archiviazione per la distribuzione di Skype for Business Server, incluso l'abilitazione e la disabilitazione delle opzioni seguenti:"
ms.openlocfilehash: f56b452058a8ce51ac5d5761e9b24c6595bbdd39
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687039"
---
# <a name="archiving-configuration"></a>Configurazione archiviazione
 
Puoi usare le configurazioni di archiviazione per controllare le opzioni di archiviazione per la distribuzione di Skype for Business Server, incluso l'abilitazione e la disabilitazione delle opzioni seguenti:
  
- Blocco delle sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce
    
- Integrazione con lo spazio di archiviazione di Exchange 2013 per gli utenti residenti in Exchange 2013
    
- Eliminazione dei dati archiviati
    
Le configurazioni di archiviazione includono la configurazione globale e, facoltativamente, una o più configurazioni di archiviazione per sito e pool:
  
- **Configurazione globale** La configurazione globale viene creata per impostazione predefinita in tutte le distribuzioni di Skype for Business Server. È possibile modificare la configurazione globale, ma non eliminare la configurazione di archiviazione. Se si tenta di eliminarla, tutte le opzioni verranno ripristinate ai valori predefiniti.
    
- **Configurazione sito (facoltativa)** È possibile specificare una o più configurazioni di archiviazione del sito, ognuna delle quali può essere configurata per controllare le opzioni di archiviazione per un sito specifico. Una configurazione di sito ha la priorità rispetto alla configurazione globale, ma solo per i siti specificati nelle configurazioni sito di archiviazione. È possibile modificare o eliminare le configurazioni sito.
    
- **Configurazione del pool (facoltativo)** Puoi specificare una o più configurazioni di archiviazione del pool per controllare le opzioni di archiviazione per un pool specifico. Una configurazione pool ha la priorità rispetto alla configurazione globale e alla configurazione sito, ma solo per i pool specificati nelle configurazioni pool di archiviazione. È possibile modificare o eliminare le configurazioni pool.
    
> [!NOTE]
> Le configurazioni di archiviazione si applicano agli utenti ospitati in Skype for Business Server e, se si usa Exchange per archiviare i dati di archiviazione in Microsoft Exchange, agli utenti ospitati in Exchange 2013, ma vengono implementati in modo leggermente diverso per gli utenti residenti in Exchange 2013. Le differenze sono descritte nella sezione successiva. 
  
Nella pagina **Configurazione archiviazione** sono elencati tutti i criteri di archiviazione configurati per la distribuzione. Sono inoltre mostrati il nome del criterio, l'ambito (globale, sito o pool) e quali opzioni di archiviazione sono abilitate per ogni configurazione di archiviazione. Nella pagina **Configurazione archiviazione** sono disponibili le opzioni seguenti:
- **Nuovo** È possibile aggiungere una o più delle configurazioni di archiviazione facoltative seguenti.
    
  - Configurazione sito
    
  - Configurazione pool
    
- **Modifica** È possibile modificare le opzioni di tutte le configurazioni di archiviazione elencate nella pagina. Usando questa voce, è possibile scegliere tra le opzioni seguenti:
    
  - **Mostra dettagli** Questa opzione apre una finestra di dialogo in cui è possibile modificare le opzioni di archiviazione per la configurazione di archiviazione selezionata. È possibile mostrare i dettagli solo per una configurazione di archiviazione alla volta.
    
  - **Seleziona tutto** Questa opzione consente di selezionare tutte le configurazioni di archiviazione nell'elenco.
    
  - **Eliminare** Questa opzione Elimina tutte le configurazioni di archiviazione selezionate.
    
- **Azione** Puoi usare questa opzione per abilitare o disabilitare rapidamente l'archiviazione delle sessioni di messaggistica istantanea o delle sessioni di conferenza Web in qualsiasi configurazione elencata nella pagina, invece di modificare la configurazione. Le opzioni disponibili in **Azione** dipendono dall'opzione attualmente specificata nella configurazione di archiviazione. Tutte le opzioni sono disponibili, a eccezione di quella attualmente applicata per la configurazione di archiviazione. Tra le opzioni disponibili sono incluse le seguenti:
    
  - **Archivia sessioni di messaggistica istantanea**
    
  - **Archivia sessioni di messaggistica istantanea e Web Conferencing**
    
  - **Disabilita archiviazione**
    
- **Aggiornare** È possibile aggiornare la pagina di **configurazione dell'archiviazione** per verificare lo stato delle opzioni di tutte le configurazioni di archiviazione.
    
Per informazioni dettagliate sulla funzionalità e le funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [pianificare l'archiviazione in Skype for Business server 2015](../../plan-your-deployment/archiving/archiving.md), [distribuire l'archiviazione per Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)e [gestire l'archiviazione in Skype for Business Server 2015](../../manage/archiving/archiving.md).

