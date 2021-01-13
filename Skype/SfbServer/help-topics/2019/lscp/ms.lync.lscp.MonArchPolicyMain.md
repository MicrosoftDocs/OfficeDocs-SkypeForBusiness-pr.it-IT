---
title: Criteri archiviazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: "È possibile utilizzare i criteri di archiviazione per abilitare e disabilitare l'archiviazione per gli utenti ospitati in Skype for Business Server. In ogni criterio di archiviazione, è possibile abilitare o disabilitare l'archiviazione per uno o entrambi gli elementi seguenti:"
ms.openlocfilehash: 041fc71da18ff38b14e82ce9d2ab14f366326b29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833616"
---
# <a name="archiving-policy"></a>Criteri archiviazione
 
È possibile utilizzare i criteri di archiviazione per abilitare e disabilitare l'archiviazione per gli utenti ospitati in Skype for Business Server. In ogni criterio di archiviazione, è possibile abilitare o disabilitare l'archiviazione per uno o entrambi gli elementi seguenti:
  
- Comunicazioni interne
    
- Comunicazioni esterne (comunicazioni che includono almeno un utente esterno alla rete interna)
    
I criteri di archiviazione includono il criterio globale e, facoltativamente, uno o più criteri di archiviazione per sito e utente:
  
- **Criteri globali** Il criterio globale viene creato per impostazione predefinita in tutte le distribuzioni. È possibile modificare il criterio globale, ma non eliminarlo. Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.
    
- **Criteri sito (facoltativo)** È possibile specificare uno o più criteri di archiviazione dei siti, ognuno dei quali può essere configurato per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un singolo sito. Un criterio sito ha la precedenza sui criteri globali, ma solo per i siti specificati nei criteri del sito di archiviazione. È possibile modificare o eliminare i criteri sito.
    
- **Criteri utente (facoltativo)** È possibile specificare uno o più criteri di archiviazione degli utenti, ognuno dei quali può essere configurato per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un utente o un gruppo di utenti specifico. Un criterio utente ha la precedenza sui criteri globali e sui criteri sito, ma solo per gli utenti e i gruppi di utenti a cui si assegnano i criteri di archiviazione a livello di utente. È possibile modificare o eliminare i criteri utente.
    
> [!NOTE]
> I criteri di archiviazione sono validi solo per gli utenti ospitati in Skype for Business Server. Se si utilizza l'integrazione di Exchange per archiviare i dati di archiviazione in Microsoft Exchange, i criteri di Exchange controllano l'archiviazione per gli utenti ospitati in Exchange. Per abilitare l'archiviazione per tali utenti, è necessario che la cassetta postale dell'utente venga inserita In-Place blocco. 
  
La pagina **criteri di archiviazione** elenca tutti i criteri di archiviazione configurati per la distribuzione. Vengono inoltre visualizzati il nome del criterio, l'ambito (globale, sito o utente) e quali opzioni di archiviazione sono abilitate per ogni criterio di archiviazione. Nella pagina **criteri di archiviazione** sono disponibili le opzioni seguenti:
- **Nuovo** È possibile aggiungere uno o più dei seguenti criteri di archiviazione facoltativi:
    
  - Criterio sito
    
  - Criteri utente
    
- **Modifica** È possibile modificare le opzioni di tutti i criteri di archiviazione elencati nella pagina. Usando questa voce, è possibile scegliere tra le opzioni seguenti:
    
  - **Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni di archiviazione per un criterio di archiviazione.
    
  - **Seleziona tutto** Questa opzione consente di selezionare tutti i criteri di archiviazione nell'elenco.
    
  - **Eliminare** Questa opzione consente di eliminare tutti i criteri di archiviazione selezionati.
    
- **Azione** È possibile utilizzare questa opzione per abilitare o disabilitare rapidamente l'archiviazione delle comunicazioni interne o esterne in qualsiasi criterio elencato nella pagina, anziché modificare il criterio. Le opzioni disponibili in **azione** dipendono dall'opzione attualmente specificata nei criteri di archiviazione. Tutte le opzioni sono disponibili, ad eccezione dell'opzione attualmente attiva per il criterio di archiviazione. Tra le opzioni sono incluse le seguenti:
    
  - **Abilitare l'archiviazione delle comunicazioni interne**
    
  - **Disabilitare l'archiviazione delle comunicazioni interne**
    
  - **Abilitare l'archiviazione delle comunicazioni esterne**
    
  - **Disabilitare l'archiviazione delle comunicazioni esterne**
    
- **Aggiorna** È possibile aggiornare la pagina **criteri di archiviazione** per verificare lo stato delle opzioni di tutti i criteri di archiviazione.
    
Per informazioni dettagliate sulla funzionalità e sulle funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [deploy Archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)e [Manage Archiving in Skype for Business Server](../../../manage/archiving/archiving.md).

