---
title: Configurazione di archiviazione Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.localizationpriority: medium
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 'Le configurazioni di archiviazione vengono utilizzate per controllare le opzioni di archiviazione per la distribuzione. Le configurazioni di archiviazione includono la configurazione globale e, facoltativamente, una o più configurazioni di siti e pool:'
ms.openlocfilehash: 7a6511d4a72f8771a9accb8a9582d947e232541a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766744"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configurazione archiviazione: crearne una nuova o modificarne una esistente
 
Le configurazioni di archiviazione vengono utilizzate per controllare le opzioni di archiviazione per la distribuzione. Le configurazioni di archiviazione includono la configurazione globale e, facoltativamente, una o più configurazioni di siti e pool:
  
- **Configurazione globale** La configurazione globale viene creata per impostazione predefinita. È possibile modificare la configurazione globale, ma non eliminare questa configurazione di archiviazione. Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.
    
- **Configurazione sito (facoltativo)** È possibile specificare una o più configurazioni di archiviazione del sito, ognuna delle quali può essere configurata per controllare le opzioni di archiviazione per un sito specifico. Una configurazione di sito sostituisce la configurazione globale, ma solo per i siti specificati nelle configurazioni dei siti di archiviazione. È possibile modificare o eliminare configurazioni di sito.
    
- **Configurazione pool (facoltativo)** È possibile specificare una o più configurazioni di archiviazione del pool per controllare le opzioni di archiviazione per un pool specifico. La configurazione di un pool sostituisce la configurazione globale e la configurazione del sito, ma solo per i pool specificati nelle configurazioni del pool di archiviazione. È possibile modificare o eliminare le configurazioni del pool.
    
> [!NOTE]
> Le configurazioni di archiviazione si applicano agli utenti ospitati in Skype for Business Server e, se si abilita l'opzione di integrazione di Microsoft Exchange per utilizzare Exchange 2013 per archiviare i dati di archiviazione in Microsoft Exchange, agli utenti ospitati in Exchange 2013. Tuttavia, alcune opzioni sono implementate in modo leggermente diverso per gli utenti ospitati in Exchange 2013, come descritto nella sezione successiva. 
  
Per definire le impostazioni di una configurazione di archiviazione nuova o esistente, specificare le seguenti opzioni:
- **Nome** Ogni configurazione di archiviazione richiede un nome. Il nome è determinato dal tipo di configurazione che si sta aggiungendo o modificando:
    
  - **Configurazione globale** Il nome predefinito è Global. Ad esempio, Contoso North American Organization.
    
  - **Configurazione del sito** L'elenco contiene i siti disponibili nella distribuzione. Fare clic su un singolo sito per selezionarlo. Ad esempio, Redmond Data Center.
    
  - **Configurazione pool** Specificare un nome appropriato, che può essere il nome di uno specifico pool Front End o edizione Standard Server nella distribuzione. Ad esempio, Marketing Division.
    
- **Descrizione** Questo è facoltativo. Utilizzarlo per fornire ulteriori dettagli, ad esempio l'ambito o l'utilizzo della configurazione. Ad esempio, Coordinarsi con i reparti legali di altri siti.
    
- **Impostazione di archiviazione** Le opzioni disponibili sono le seguenti:
    
  - **Archivia sessioni di messaggistica istantanea**
    
  - **Archivia sessioni di messaggistica istantanea e Web Conferencing**
    
  - **Disabilita archiviazione**
    
- **Bloccare le sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione ha esito negativo** Gli errori includono quanto segue:
    
  - **Messaggistica** istantanea Un errore potrebbe essere un database completo o un problema con il servizio di archiviazione. In questo caso, la messaggistica istantanea viene bloccata per gli utenti abilitati per l'archiviazione.
    
  - **Conferenze** Un errore potrebbe essere una condivisione file non disponibile o un problema con il servizio di archiviazione. In questo caso, per tutte le conferenze attive ospitate nel pool al momento dell'errore viene impostata la modalità limitata e diventa impossibile attivare nuove conferenze.
    
    Sia la funzionalità di messaggistica immediata che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori.
    
- **Integrazione Exchange Microsoft** Selezionare questa opzione se si dispone di utenti ospitati in Exchange 2013. Con questa opzione, Exchange 2013 viene utilizzato per archiviare i dati per tali utenti, se le loro cassette postali sono state In-Place blocco. Se tutti gli utenti sono ospitati Exchange 2013, non è necessario configurare database SQL Server separati per l'archiviazione dei dati di archiviazione.
    
- **Abilitare l'eliminazione dei dati di archiviazione** Selezionare questa opzione per abilitare l'eliminazione e specificare le opzioni di eliminazione, tra cui:
    
  - Eliminazione dopo un determinato numero di giorni specificato.
    
  - Eliminazione dopo l'esportazione dei dati di archiviazione (inclusi i dati caricati in Exchange, se si abilita l'integrazione di Microsoft Exchange).
    
    > [!NOTE]
    > Se si abilita l'integrazione di Microsoft Exchange, l'eliminazione per gli utenti ospitati in Exchange 2013 e con le cassette postali poste In-Place blocco è controllata da Exchange. L'unica eccezione è per i file di conferenza, archiviati nella condivisione file di Lync Server. Questi file vengono eliminati dalla condivisione file solo dopo l'esportazione (il caricamento in Exchange), se si seleziona l'opzione per l'eliminazione dei dati dopo l'esportazione dei dati di archiviazione, o dopo il numero massimo di giorni specificato, se si specifica un numero massimo di giorni di conservazione. 
  
Per informazioni dettagliate sulle funzionalità e sulle funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [Plan for archiving in Skype for Business Server 2015,](../../plan-your-deployment/archiving/archiving.md)Deploy archiving for Skype for Business Server [2015](../../deploy/deploy-archiving/deploy-archiving.md)e [Manage archiving in Skype for Business Server 2015.](../../manage/archiving/archiving.md)

