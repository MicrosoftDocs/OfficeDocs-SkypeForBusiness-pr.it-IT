---
title: Configurazione di archiviazione creare nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 'Le configurazioni di archiviazione consentono di controllare le opzioni di archiviazione per la propria distribuzione e includono la configurazione globale e, facoltativamente, una o più configurazioni sito e pool:'
ms.openlocfilehash: d40750069d34cb274342c1f5aab5d8191f90a334
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195109"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>Configurazione archiviazione: crearne una nuova o modificarne una esistente
 
Le configurazioni di archiviazione consentono di controllare le opzioni di archiviazione per la propria distribuzione e includono la configurazione globale e, facoltativamente, una o più configurazioni sito e pool:
  
- **Configurazione globale** La configurazione globale viene creata per impostazione predefinita. È possibile modificare la configurazione globale, ma non è possibile eliminare questa configurazione di archiviazione. Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.
    
- **Configurazione sito (facoltativa)** È possibile specificare una o più configurazioni di archiviazione del sito, ognuna delle quali può essere configurata per controllare le opzioni di archiviazione per un sito specifico. Una configurazione di sito ha la priorità rispetto alla configurazione globale, ma solo per i siti specificati nelle configurazioni sito di archiviazione. È possibile modificare o eliminare le configurazioni sito.
    
- **Configurazione del pool (facoltativo)** Puoi specificare una o più configurazioni di archiviazione per il pool, per controllare le opzioni di archiviazione per un pool specifico. Una configurazione pool ha la priorità rispetto alla configurazione globale e alla configurazione sito, ma solo per i pool specificati nelle configurazioni pool di archiviazione. È possibile modificare o eliminare le configurazioni pool.
    
> [!NOTE]
> Le configurazioni di archiviazione si applicano agli utenti ospitati in Skype for Business Server e, se si Abilita l'opzione di integrazione di Microsoft Exchange per usare Exchange 2013 per archiviare i dati di archiviazione in Microsoft Exchange, agli utenti ospitati in Exchange 2013. Alcune opzioni sono tuttavia implementate in modo leggermente diverso per gli utenti residenti in Exchange 2013, come descritto nella sezione successiva. 
  
Per definire le impostazioni di una configurazione di archiviazione nuova o esistente, specificare le seguenti opzioni:
- **Nome** Ogni configurazione di archiviazione richiede un nome. Il nome è determinato dal tipo di configurazione che si sta aggiungendo o modificando:
    
  - **Configurazione globale** Il nome predefinito è Global. Ad esempio, contoso North American Organization.
    
  - **Configurazione sito** L'elenco contiene i siti disponibili nella distribuzione. Fare clic su un singolo sito per selezionarlo. Ad esempio, Redmond Data Center.
    
  - **Configurazione del pool** Specificare un nome appropriato, che può essere il nome di uno specifico pool Front-end o di un server Standard Edition nella distribuzione. Ad esempio, divisione marketing.
    
- **Descrizione** Questa opzione è facoltativa. Usalo per ottenere dettagli aggiuntivi, ad esempio l'ambito o l'uso della configurazione. Ad esempio, coordina i servizi legali di altri siti.
    
- **Impostazione archiviazione** Le opzioni includono le seguenti:
    
  - **Archivia sessioni di messaggistica istantanea**
    
  - **Archivia sessioni di messaggistica istantanea e Web Conferencing**
    
  - **Disabilita archiviazione**
    
- **Bloccare le sessioni di messaggistica istantanea o di conferenza Web se l'archiviazione non riesce** Gli errori includono i seguenti:
    
  - **Messaggistica istantanea** un errore potrebbe essere un database completo o un problema con il servizio di archiviazione. In questo caso, la messaggistica istantanea viene bloccata per gli utenti abilitati per l'archiviazione.
    
  - Servizi di **conferenza** Un errore potrebbe essere una condivisione file non disponibile o un problema con il servizio di archiviazione. In questo caso, per tutte le conferenze attive ospitate nel pool al momento dell'errore viene impostata la modalità limitata e diventa impossibile attivare nuove conferenze.
    
    Sia la funzionalità di messaggistica istantanea che il servizio di conferenza vengono ripristinati automaticamente subito dopo la correzione degli errori.
    
- **Integrazione con Microsoft Exchange** Selezionare questa opzione se si hanno utenti residenti in Exchange 2013. Con questa opzione, Exchange 2013 viene usato per archiviare i dati per tali utenti, se le cassette postali sono state inserite in blocco sul posto. Se tutti gli utenti sono ospitati in Exchange 2013, non è necessario configurare i database di SQL Server separati per l'archiviazione dei dati di archiviazione.
    
- **Abilitare l'eliminazione dei dati di archiviazione** Selezionare questa opzione per abilitare l'eliminazione e specificare le opzioni di eliminazione, che includono le seguenti:
    
  - Eliminazione dopo un determinato numero di giorni specificato.
    
  - Eliminazione dopo l'esportazione dei dati di archiviazione (che include i dati caricati in Exchange, se si Abilita l'integrazione di Microsoft Exchange).
    
    > [!NOTE]
    > Se si Abilita l'integrazione di Microsoft Exchange, l'eliminazione per gli utenti ospitati in Exchange 2013 e le cassette postali posizionate sul blocco sul posto è controllata da Exchange. L'unica eccezione è per i file di conferenza, archiviati nella condivisione file di Lync Server. Questi file vengono eliminati dalla condivisione file solo dopo l'esportazione (il caricamento in Exchange), se si seleziona l'opzione per l'eliminazione dei dati dopo l'esportazione dei dati di archiviazione, o dopo il numero massimo di giorni specificato, se si specifica un numero massimo di giorni di conservazione. 
  
Per informazioni dettagliate sulla funzionalità e le funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [pianificare l'archiviazione in Skype for Business server 2015](../../plan-your-deployment/archiving/archiving.md), [distribuire l'archiviazione per Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)e [gestire l'archiviazione in Skype for Business Server 2015](../../manage/archiving/archiving.md).

