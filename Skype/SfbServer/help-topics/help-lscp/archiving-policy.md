---
title: Criteri di archiviazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: "Si usano i criteri di archiviazione per abilitare e disabilitare l'archiviazione per gli utenti ospitati in Skype for Business Server. Nei criteri di archiviazione è possibile abilitare o disabilitare la funzionalità per uno o entrambi i tipi di comunicazione seguenti:"
ms.openlocfilehash: 230b27a0d87b553f64b209e5aa3d464e88ae370a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823189"
---
# <a name="archiving-policy"></a>Criteri di archiviazione
 
Si usano i criteri di archiviazione per abilitare e disabilitare l'archiviazione per gli utenti ospitati in Skype for Business Server. Nei criteri di archiviazione è possibile abilitare o disabilitare la funzionalità per uno o entrambi i tipi di comunicazione seguenti:
  
- Comunicazioni interne
    
- Comunicazioni esterne (comunicazioni che includono almeno un utente esterno alla rete interna)
    
I criteri di archiviazione includono il criterio globale e, facoltativamente, uno o più criteri di archiviazione per sito e utente:
  
- **Criteri globali** Il criterio globale viene creato per impostazione predefinita in tutte le distribuzioni. È possibile modificare il criterio globale, ma non eliminarlo. Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.
    
- **Criteri sito (facoltativo)** Puoi specificare uno o più criteri di archiviazione del sito, ognuno dei quali puoi configurare per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un singolo sito. Un criterio sito ha la precedenza sui criteri globali, ma solo per il sito specificato nei criteri di archiviazione del sito. È possibile modificare o eliminare i criteri sito.
    
- **Criteri utente (facoltativo)** Puoi specificare uno o più criteri di archiviazione degli utenti, ognuno dei quali puoi configurare per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un utente o un gruppo di utenti specifico. Un criterio utente ha la precedenza sui criteri globali e i criteri sito, ma solo per gli utenti e i gruppi di utenti a cui si assegnano i criteri di archiviazione a livello utente. È possibile modificare o eliminare i criteri utente.
    
> [!NOTE]
> I criteri di archiviazione si applicano solo agli utenti residenti in Skype for Business Server. Se si usa l'integrazione di Exchange per archiviare i dati di archiviazione in Microsoft Exchange, i criteri di Exchange 2013 controllano l'archiviazione per gli utenti ospitati in Exchange 2013. Per abilitare l'archiviazione per tali utenti, la cassetta postale dell'utente deve essere posizionata sul blocco sul posto. 
  
Nella pagina **Criteri di archiviazione** sono elencati tutti i criteri di archiviazione configurati per la distribuzione. Sono inoltre mostrati il nome del criterio, l'ambito (globale, sito o utente) e quali opzioni di archiviazione sono abilitate per ogni criterio di archiviazione. Nella pagina **Criteri di archiviazione** sono disponibili le opzioni seguenti:
- **Nuovo** È possibile aggiungere uno o più dei seguenti criteri di archiviazione facoltativi:
    
  - Criteri sito
    
  - Criteri utente
    
- **Modifica** È possibile modificare le opzioni di uno dei criteri di archiviazione elencati nella pagina. Usando questa opzione è possibile eseguire le operazioni seguenti:
    
  - **Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni di archiviazione per un criterio di archiviazione.
    
  - **Seleziona tutto** Questa opzione consente di selezionare tutti i criteri di archiviazione nell'elenco.
    
  - **Elimina** Questa opzione consente di eliminare tutti i criteri di archiviazione selezionati.
    
- **Azione** Puoi usare questa opzione per abilitare o disabilitare rapidamente l'archiviazione delle comunicazioni interne o esterne in qualsiasi criterio elencato nella pagina, invece di modificare i criteri. Le opzioni disponibili in **Azione** dipendono dall'opzione attualmente specificata nel criterio di archiviazione. Tutte le opzioni sono disponibili, ad eccezione di quella attualmente applicata per il criterio di archiviazione. Tra le opzioni disponibili sono incluse le seguenti:
    
  - **Abilita archiviazione di comunicazioni interne**
    
  - **Disabilita archiviazione di comunicazioni interne**
    
  - **Abilita archiviazione di comunicazioni esterne**
    
  - **Disabilita archiviazione di comunicazioni esterne**
    
- **Aggiornare** È possibile aggiornare la pagina dei **criteri di archiviazione** per verificare lo stato delle opzioni di tutti i criteri di archiviazione.
    
Per informazioni dettagliate sulla funzionalità e le funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [pianificare l'archiviazione in Skype for Business server 2015](../../plan-your-deployment/archiving/archiving.md), [distribuire l'archiviazione per Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)e [gestire l'archiviazione in Skype for Business Server 2015](../../manage/archiving/archiving.md).

