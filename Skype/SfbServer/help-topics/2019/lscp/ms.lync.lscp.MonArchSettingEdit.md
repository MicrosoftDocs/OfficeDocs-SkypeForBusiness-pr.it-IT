---
title: Configurazione di archiviazione creare una nuova o modificarne una esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 'È possibile utilizzare le configurazioni di archiviazione per controllare le opzioni di archiviazione per la distribuzione. Le configurazioni di archiviazione includono la configurazione globale e, facoltativamente, una o più configurazioni del sito e del pool:'
ms.openlocfilehash: 77d1be61be3a1bad063bb7f32957937f182094e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812256"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configurazione archiviazione: crearne una nuova o modificarne una esistente
 
È possibile utilizzare le configurazioni di archiviazione per controllare le opzioni di archiviazione per la distribuzione. Le configurazioni di archiviazione includono la configurazione globale e, facoltativamente, una o più configurazioni del sito e del pool:
  
- **Configurazione globale** La configurazione globale viene creata per impostazione predefinita. È possibile modificare la configurazione globale, ma non è possibile eliminare la configurazione di archiviazione. Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.
    
- **Configurazione del sito (facoltativo)** È possibile specificare una o più configurazioni di archiviazione siti, ognuna delle quali può essere configurata per controllare le opzioni di archiviazione per un sito specifico. La configurazione di un sito sostituisce la configurazione globale, ma solo per i siti specificati nelle configurazioni del sito di archiviazione. È possibile modificare o eliminare le configurazioni di sito.
    
- **Configurazione del pool (facoltativa)** È possibile specificare una o più configurazioni di archiviazione pool per controllare le opzioni di archiviazione per un pool specifico. La configurazione del pool sostituisce la configurazione globale e la configurazione del sito, ma solo per i pool specificati nelle configurazioni del pool di archiviazione. È possibile modificare o eliminare le configurazioni del pool.
    
> [!NOTE]
> Le configurazioni di archiviazione si applicano agli utenti ospitati su Skype for Business Server e, se si Abilita l'opzione di integrazione di Microsoft Exchange per l'utilizzo di Exchange per archiviare i dati di archiviazione in Microsoft Exchange, per gli utenti ospitati in Exchange. Tuttavia, alcune opzioni vengono implementate in modo leggermente diverso per gli utenti ospitati in Exchange, come descritto nella sezione successiva. 
  
Per definire le impostazioni di una configurazione di archiviazione nuova o esistente, specificare le seguenti opzioni:
- **Nome** Ogni configurazione di archiviazione richiede un nome. Il nome è determinato dal tipo di configurazione che si sta aggiungendo o modificando:
    
  - **Configurazione globale** Il nome predefinito è Global. Ad esempio, contoso North American Organization.
    
  - **Configurazione del sito** L'elenco contiene i siti disponibili nella distribuzione. Fare clic su un singolo sito per selezionarlo. Ad esempio, Redmond Data Center.
    
  - **Configurazione del pool** Specificare un nome appropriato, che può essere il nome di un pool Front end specifico o di un server Standard Edition nella distribuzione. Ad esempio, divisione marketing.
    
- **Descrizione/Controlli** Questo è facoltativo. Utilizzarla per fornire ulteriori dettagli, ad esempio l'ambito o l'utilizzo della configurazione. Ad esempio, coordinarsi con i reparti legali di altri siti.
    
- **Impostazione di archiviazione** Tra le opzioni sono incluse le seguenti:
    
  - **Archivia sessioni di messaggistica istantanea**
    
  - **Archivia sessioni di messaggistica istantanea e Web Conferencing**
    
  - **Disabilita archiviazione**
    
- **Blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce** Tra gli errori sono inclusi i seguenti:
    
  - **Im** un errore potrebbe essere un database completo o un problema con il servizio di archiviazione. In questo caso, la messaggistica istantanea viene bloccata per gli utenti abilitati per l'archiviazione.
    
  - Servizi di **conferenza** Un errore potrebbe essere una condivisione file non disponibile o un problema con il servizio di archiviazione. In questo caso, per tutte le conferenze attive ospitate nel pool al momento dell'errore viene impostata la modalità limitata e diventa impossibile attivare nuove conferenze.
    
    Sia la funzionalità di messaggistica immediata che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori.
    
- **Integrazione di Microsoft Exchange** Selezionare questa opzione se si dispone di utenti ospitati in Exchange. Con questa opzione, Exchange viene utilizzato per archiviare i dati per tali utenti, se le relative cassette postali sono state inserite in In-Place blocco. Se tutti gli utenti sono ospitati in Exchange, non è necessario configurare database SQL Server separati per l'archiviazione dei dati di archiviazione.
    
- **Abilitare l'eliminazione dei dati di archiviazione** Selezionare questa opzione per abilitare l'eliminazione e specificare le opzioni di eliminazione, che includono le seguenti:
    
  - Eliminazione dopo un determinato numero di giorni specificato.
    
  - Eliminazione dopo l'esportazione dei dati di archiviazione (che include i dati caricati in Exchange, se si Abilita l'integrazione di Microsoft Exchange).
    
    > [!NOTE]
    > Se si Abilita l'integrazione di Microsoft Exchange, l'eliminazione per gli utenti ospitati in Exchange e con le relative cassette postali inserite in In-Place blocco è controllato da Exchange. L'unica eccezione è per i file di conferenza, che sono archiviati nella condivisione file di Lync Server. Questi file vengono eliminati dalla condivisione file solo dopo l'esportazione (il caricamento in Exchange), se si seleziona l'opzione per l'eliminazione dei dati dopo l'esportazione dei dati di archiviazione, o dopo il numero massimo di giorni specificato, se si specifica un numero massimo di giorni di conservazione. 
  
Per informazioni dettagliate sulla funzionalità e sulle funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [deploy Archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)e [Manage Archiving in Skype for Business Server](../../../manage/archiving/archiving.md).

