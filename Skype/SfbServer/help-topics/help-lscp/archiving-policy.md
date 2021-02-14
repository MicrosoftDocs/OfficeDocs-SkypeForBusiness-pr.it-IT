---
title: Criteri archiviazione
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
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: "I criteri di archiviazione consentono di abilitare e disabilitare l'archiviazione per gli utenti ospitati in Skype for Business Server. In ogni criterio di archiviazione è possibile abilitare o disabilitare l'archiviazione per uno o entrambi gli elementi seguenti:"
ms.openlocfilehash: 19bc0612208e719b7a963bf4c7f0dc6a9cc69537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826946"
---
# <a name="archiving-policy"></a>Criteri archiviazione
 
I criteri di archiviazione consentono di abilitare e disabilitare l'archiviazione per gli utenti ospitati in Skype for Business Server. In ogni criterio di archiviazione è possibile abilitare o disabilitare l'archiviazione per uno o entrambi gli elementi seguenti:
  
- Comunicazioni interne
    
- Comunicazioni esterne (comunicazioni che includono almeno un utente esterno alla rete interna)
    
I criteri di archiviazione includono i criteri globali e, facoltativamente, uno o più criteri di archiviazione per siti e utenti:
  
- **Criteri globali** Il criterio globale viene creato per impostazione predefinita in tutte le distribuzioni. È possibile modificare il criterio globale, ma non eliminarlo. Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.
    
- **Criteri sito (facoltativo)** È possibile specificare uno o più criteri di archiviazione del sito, ognuno dei quali può essere configurato per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un singolo sito. Un criterio sito ha la precedenza sul criterio globale, ma solo per i siti specificati nei criteri del sito di archiviazione. È possibile modificare o eliminare i criteri sito.
    
- **Criteri utente (facoltativo)** È possibile specificare uno o più criteri di archiviazione utente, ognuno dei quali può essere configurato per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un utente o un gruppo di utenti specifico. I criteri utente sostituiscono i criteri globali e i criteri sito, ma solo per gli utenti e i gruppi di utenti a cui si assegnano criteri di archiviazione a livello di utente. È possibile modificare o eliminare i criteri utente.
    
> [!NOTE]
> I criteri di archiviazione si applicano solo agli utenti ospitati in Skype for Business Server. Se si utilizza l'integrazione di Exchange per archiviare i dati di archiviazione in Microsoft Exchange, i criteri di Exchange 2013 controllano l'archiviazione per gli utenti ospitati in Exchange 2013. Per abilitare l'archiviazione per tali utenti, la cassetta postale dell'utente deve essere In-Place blocco. 
  
Nella **pagina Criteri di** archiviazione sono elencati i criteri di archiviazione configurati per la distribuzione. Vengono inoltre visualizzati il nome del criterio, l'ambito (globale, sito o utente) e le opzioni di archiviazione abilitate per ogni criterio di archiviazione. Nella pagina **Criteri di** archiviazione sono disponibili le opzioni seguenti:
- **Nuovo** È possibile aggiungere uno o più dei criteri di archiviazione facoltativi seguenti:
    
  - Criterio sito
    
  - Criteri utente
    
- **Modifica** È possibile modificare le opzioni di uno qualsiasi dei criteri di archiviazione elencati nella pagina. Usando questa voce, è possibile scegliere tra le opzioni seguenti:
    
  - **Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni di archiviazione per un criterio di archiviazione.
    
  - **Seleziona tutto** Questa opzione consente di selezionare tutti i criteri di archiviazione nell'elenco.
    
  - **Elimina** Questa opzione consente di eliminare tutti i criteri di archiviazione selezionati.
    
- **Azione** È possibile utilizzare questa opzione per abilitare o disabilitare rapidamente l'archiviazione delle comunicazioni interne o esterne in qualsiasi criterio elencato nella pagina, anziché modificare il criterio. Le opzioni disponibili in **Azione** dipendono dall'opzione attualmente specificata nei criteri di archiviazione. Sono disponibili tutte le opzioni, ad eccezione dell'opzione attualmente in vigore per il criterio di archiviazione. Tra le opzioni sono incluse le seguenti:
    
  - **Abilitare l'archiviazione delle comunicazioni interne**
    
  - **Disabilitare l'archiviazione delle comunicazioni interne**
    
  - **Abilitare l'archiviazione delle comunicazioni esterne**
    
  - **Disabilitare l'archiviazione delle comunicazioni esterne**
    
- **Aggiorna** È possibile aggiornare la pagina **Criteri di** archiviazione per verificare lo stato delle opzioni di tutti i criteri di archiviazione.
    
Per informazioni dettagliate sulle funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere Pianificare l'archiviazione [in Skype for Business Server 2015,](../../plan-your-deployment/archiving/archiving.md)Distribuire l'archiviazione per Skype for Business Server [2015](../../deploy/deploy-archiving/deploy-archiving.md)e Gestire l'archiviazione [in Skype for Business Server 2015.](../../manage/archiving/archiving.md)

