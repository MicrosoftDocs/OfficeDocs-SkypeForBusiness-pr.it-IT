---
title: Criteri di archiviazione Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: "I criteri di archiviazione consentono di controllare l'archiviazione delle comunicazioni interne ed esterne nella distribuzione per gli utenti ospitati in Skype for Business Server. I criteri di archiviazione includono il criterio globale e, facoltativamente, uno o più criteri per sito e utente:"
ms.openlocfilehash: a32ca25092c5240b3be2080098b8bd8bc3477ec6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838788"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Criteri di archiviazione: crearne di nuovi o modificare quelli esistenti
 
I criteri di archiviazione consentono di controllare l'archiviazione delle comunicazioni interne ed esterne nella distribuzione per gli utenti ospitati in Skype for Business Server. I criteri di archiviazione includono il criterio globale e, facoltativamente, uno o più criteri per sito e utente:
  
- **Criteri globali** Il criterio globale viene creato per impostazione predefinita in tutte Skype for Business Server distribuzione. È possibile modificare il criterio globale, ma non eliminarlo. Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.
    
- **Criteri sito (facoltativo)** È possibile specificare uno o più criteri di archiviazione del sito, ognuno dei quali può essere configurato per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un sito specifico. Un criterio sito ha la precedenza sui criteri globali, ma solo per il sito specificato nei criteri di archiviazione. È possibile modificare o eliminare i criteri sito.
    
- **Criteri utente (facoltativo)** È possibile specificare uno o più criteri di archiviazione utente, ognuno dei quali può essere configurato per abilitare e disabilitare l'archiviazione per le comunicazioni interne o esterne per un utente specifico. Un criterio utente ha la precedenza sui criteri globali e i criteri sito, ma solo per gli utenti a cui si assegna un criterio utente. È possibile modificare o eliminare i criteri utente.
    
> [!NOTE]
> Se si utilizza l'integrazione Exchange per archiviare i dati di archiviazione in Microsoft Exchange, i criteri di Exchange 2013 controllano l'archiviazione per gli utenti ospitati in Exchange 2013. Per abilitare l'archiviazione per tali utenti, è necessario che la cassetta postale dell'utente sia In-Place blocco. 
  
Per configurare le impostazioni per un criterio di archiviazione nuovo o esistente, è necessario specificare le opzioni seguenti:
- **Nome** Ogni criterio di archiviazione richiede un nome. Il nome è determinato dal tipo di criterio che si sta aggiungendo o modificando:
    
  - **Criteri globali** Il nome predefinito è Global. È possibile modificarlo con un nome più descrittivo. Ad esempio, Contoso North American Organization.
    
  - **Criteri sito** I siti elencati in questa finestra di dialogo includono tutti i siti disponibili nella distribuzione. Fare clic su un singolo sito per selezionarlo. Ad esempio, Redmond Data Center.
    
  - **Criteri utente** Specificare un nome appropriato, ad esempio il nome di un utente specifico o il nome di un gruppo di utenti o di un team dell'organizzazione. Ad esempio, Ufficio legale.
    
- **Descrizione** Questo è facoltativo. Usalo per fornire ulteriori dettagli, ad esempio l'ambito o l'uso del criterio. Ad esempio, Coordinarsi con i reparti legali di altri siti.
    
- **Archiviare le comunicazioni interne** Selezionare questa casella di controllo per abilitare l'archiviazione delle comunicazioni nella rete interna. Per impostazione predefinita, questa opzione non è abilitata in alcun criterio.
    
- **Archiviare le comunicazioni esterne** Selezionare questa casella di controllo per abilitare l'archiviazione delle comunicazioni che includono utenti esterni, ad esempio utenti remoti (inclusi utenti anonimi e di impostazione PIC) e partner federati. Per impostazione predefinita, questa opzione non è abilitata in alcun criterio.
    
Per informazioni dettagliate sulle funzionalità e sulle funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [Plan for archiving in Skype for Business Server 2015,](../../plan-your-deployment/archiving/archiving.md)Deploy archiving for Skype for Business Server [2015](../../deploy/deploy-archiving/deploy-archiving.md)e [Manage archiving in Skype for Business Server 2015.](../../manage/archiving/archiving.md)

