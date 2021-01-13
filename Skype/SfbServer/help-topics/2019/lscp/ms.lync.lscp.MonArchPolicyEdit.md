---
title: Criteri di archiviazione creare nuovi o modificarne uno esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: "È possibile utilizzare i criteri di archiviazione per controllare l'archiviazione delle comunicazioni interne ed esterne nella distribuzione per gli utenti che si trovano in Skype for Business Server. I criteri di archiviazione includono il criterio globale e, facoltativamente, uno o più criteri per sito e utente:"
ms.openlocfilehash: 71ffa03d0d3af8ea98fcc9ded17d4e3498e1705e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820316"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Criteri di archiviazione: crearne di nuovi o modificare quelli esistenti
 
È possibile utilizzare i criteri di archiviazione per controllare l'archiviazione delle comunicazioni interne ed esterne nella distribuzione per gli utenti che si trovano in Skype for Business Server. I criteri di archiviazione includono il criterio globale e, facoltativamente, uno o più criteri per sito e utente:
  
- **Criteri globali** Il criterio globale viene creato per impostazione predefinita in tutte le distribuzioni di Skype for Business Server. È possibile modificare il criterio globale, ma non eliminarlo. Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.
    
- **Criteri sito (facoltativo)** È possibile specificare uno o più criteri di archiviazione dei siti, ognuno dei quali può essere configurato per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un sito specifico. Un criterio sito ha la precedenza sui criteri globali, ma solo per il sito specificato nei criteri di archiviazione. È possibile modificare o eliminare i criteri sito.
    
- **Criteri utente (facoltativo)** È possibile specificare uno o più criteri di archiviazione degli utenti, ognuno dei quali può essere configurato per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un utente specifico. Un criterio utente ha la precedenza sui criteri globali e i criteri sito, ma solo per gli utenti a cui si assegna un criterio utente. È possibile modificare o eliminare i criteri utente.
    
> [!NOTE]
> Se si utilizza l'integrazione di Exchange per archiviare i dati di archiviazione in Microsoft Exchange, i criteri di Exchange controllano l'archiviazione per gli utenti ospitati in Exchange. Per abilitare l'archiviazione per tali utenti, è necessario che la cassetta postale dell'utente venga inserita In-Place blocco. 
  
Per configurare le impostazioni per un criterio di archiviazione nuovo o esistente, è necessario specificare le opzioni seguenti:
- **Nome** Ogni criterio di archiviazione richiede un nome. Il nome è determinato dal tipo di criterio che si sta aggiungendo o modificando:
    
  - **Criteri globali** Il nome predefinito è Global. È possibile modificarla in un nome più descrittivo. Ad esempio, contoso North American Organization.
    
  - **Criteri sito** I siti elencati in questa finestra di dialogo includono tutti i siti disponibili nella distribuzione. Fare clic su un singolo sito per selezionarlo. Ad esempio, Redmond Data Center.
    
  - **Criteri utente** Specificare un nome appropriato, ad esempio il nome di un utente specifico o il nome di un gruppo di utenti o di un team nell'organizzazione. Ad esempio, reparto legale.
    
- **Descrizione/Controlli** Questo è facoltativo. Utilizzarla per fornire ulteriori dettagli, ad esempio l'ambito o l'utilizzo dei criteri. Ad esempio, coordinarsi con i reparti legali di altri siti.
    
- **Archiviazione delle comunicazioni interne** Selezionare questa casella di controllo per abilitare l'archiviazione delle comunicazioni nella rete interna. Per impostazione predefinita, questa opzione non è abilitata in alcun criterio.
    
- **Archiviazione delle comunicazioni esterne** Selezionare questa casella di controllo per abilitare l'archiviazione delle comunicazioni che includono gli utenti esterni, ad esempio gli utenti remoti (inclusi gli utenti anonimi e le impostazioni PIC) e i partner federati. Per impostazione predefinita, questa opzione non è abilitata in alcun criterio.
    
Per informazioni dettagliate sulla funzionalità e sulle funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [deploy Archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)e [Manage Archiving in Skype for Business Server](../../../manage/archiving/archiving.md).

