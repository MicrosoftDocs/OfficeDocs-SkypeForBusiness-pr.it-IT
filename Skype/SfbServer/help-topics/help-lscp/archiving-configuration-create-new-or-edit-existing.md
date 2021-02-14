---
title: Configurazione archiviazione Crea nuova o Modifica esistente
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
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 'Le configurazioni di archiviazione vengono utilizzate per controllare le opzioni di archiviazione per la distribuzione. Le configurazioni di archiviazione includono la configurazione globale e, facoltativamente, una o più configurazioni di siti e pool:'
ms.openlocfilehash: e0f56e125919bcb27cd9523213c92b7906e89ff0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827016"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configurazione archiviazione: crearne una nuova o modificarne una esistente
 
Le configurazioni di archiviazione vengono utilizzate per controllare le opzioni di archiviazione per la distribuzione. Le configurazioni di archiviazione includono la configurazione globale e, facoltativamente, una o più configurazioni di siti e pool:
  
- **Configurazione globale** La configurazione globale viene creata per impostazione predefinita. È possibile modificare la configurazione globale, ma non eliminare questa configurazione di archiviazione. Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.
    
- **Configurazione del sito (facoltativo)** È possibile specificare una o più configurazioni di archiviazione del sito, ognuna delle quali può essere configurata per controllare le opzioni di archiviazione per un sito specifico. Una configurazione di sito ha la precedenza sulla configurazione globale, ma solo per i siti specificati nelle configurazioni del sito di archiviazione. È possibile modificare o eliminare le configurazioni dei siti.
    
- **Configurazione pool (facoltativo)** È possibile specificare una o più configurazioni di archiviazione del pool per controllare le opzioni di archiviazione per un pool specifico. La configurazione di un pool sostituisce la configurazione globale e la configurazione del sito, ma solo per i pool specificati nelle configurazioni dei pool di archiviazione. È possibile modificare o eliminare le configurazioni del pool.
    
> [!NOTE]
> Le configurazioni di archiviazione si applicano agli utenti ospitati in Skype for Business Server e, se si abilita l'opzione di integrazione di Microsoft Exchange per utilizzare Exchange 2013 per archiviare i dati di archiviazione in Microsoft Exchange, agli utenti ospitati in Exchange 2013. Tuttavia, alcune opzioni sono implementate in modo leggermente diverso per gli utenti ospitati in Exchange 2013, come descritto nella sezione successiva. 
  
Per definire le impostazioni di una configurazione di archiviazione nuova o esistente, specificare le seguenti opzioni:
- **Name** Ogni configurazione di archiviazione richiede un nome. Il nome è determinato dal tipo di configurazione che si sta aggiungendo o modificando:
    
  - **Configurazione globale** Il nome predefinito è Global. Ad esempio, Contoso North American Organization.
    
  - **Configurazione del sito** L'elenco contiene i siti disponibili nella distribuzione. Fare clic su un singolo sito per selezionarlo. Ad esempio, Redmond Data Center.
    
  - **Configurazione pool** Specificare un nome appropriato, che può essere il nome di un pool Front End o di un server Standard Edition specifico nella distribuzione. Ad esempio, Marketing Division.
    
- **Descrizione** Questo è facoltativo. Utilizzarlo per fornire ulteriori dettagli, ad esempio l'ambito o l'utilizzo della configurazione. Coordinarsi, ad esempio, con i reparti legali di altri siti.
    
- **Impostazione di archiviazione** Tra le opzioni sono incluse le seguenti:
    
  - **Archivia sessioni di messaggistica istantanea**
    
  - **Archivia sessioni di messaggistica istantanea e Web Conferencing**
    
  - **Disabilita archiviazione**
    
- **Bloccare le sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione ha esito negativo** Gli errori includono quanto segue:
    
  - **Un** errore di messaggistica istantanea potrebbe essere un database completo o un problema con il servizio di archiviazione. In questo caso, la messaggistica istantanea viene bloccata per gli utenti abilitati per l'archiviazione.
    
  - **Conferenze** Un errore potrebbe essere una condivisione file non disponibile o un problema con il servizio di archiviazione. In questo caso, per tutte le conferenze attive ospitate nel pool al momento dell'errore viene impostata la modalità limitata e diventa impossibile attivare nuove conferenze.
    
    Sia la funzionalità di messaggistica immediata che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori.
    
- **Integrazione di Microsoft Exchange** Selezionare questa opzione se sono presenti utenti ospitati in Exchange 2013. Con questa opzione, Exchange 2013 viene utilizzato per archiviare i dati per tali utenti, se le loro cassette postali sono state In-Place conservazione. Se tutti gli utenti sono ospitati in Exchange 2013, non è necessario configurare database SQL Server separati per l'archiviazione dei dati di archiviazione.
    
- **Abilitare l'eliminazione dei dati di archiviazione** Selezionare questa opzione per abilitare l'eliminazione e specificare le opzioni di eliminazione, tra cui:
    
  - Eliminazione dopo un determinato numero di giorni specificato.
    
  - Eliminazione dopo l'esportazione dei dati di archiviazione (inclusi i dati caricati in Exchange, se si abilita l'integrazione di Microsoft Exchange).
    
    > [!NOTE]
    > Se si abilita l'integrazione di Microsoft Exchange, l'eliminazione per gli utenti ospitati in Exchange 2013 e con le cassette postali abilitate In-Place blocco è controllata da Exchange. L'unica eccezione è per i file di conferenza, archiviati nella condivisione file di Lync Server. Questi file vengono eliminati dalla condivisione file solo dopo l'esportazione (il caricamento in Exchange), se si seleziona l'opzione per l'eliminazione dei dati dopo l'esportazione dei dati di archiviazione, o dopo il numero massimo di giorni specificato, se si specifica un numero massimo di giorni di conservazione. 
  
Per informazioni dettagliate sulle funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere Pianificare l'archiviazione [in Skype for Business Server 2015,](../../plan-your-deployment/archiving/archiving.md)Distribuire l'archiviazione per Skype for Business Server [2015](../../deploy/deploy-archiving/deploy-archiving.md)e Gestire l'archiviazione [in Skype for Business Server 2015.](../../manage/archiving/archiving.md)

