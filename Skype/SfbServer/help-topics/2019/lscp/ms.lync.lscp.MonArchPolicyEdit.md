---
title: Criteri di archiviazione creare nuovi o modifica esistenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: "Si usano i criteri di archiviazione per controllare l'archiviazione delle comunicazioni interne ed esterne nella distribuzione per gli utenti residenti in Skype for Business Server. I criteri di archiviazione includono il criterio globale e, facoltativamente, uno o più criteri per sito e utente:"
ms.openlocfilehash: 162266ebdb3a59148b539d6681930698e30426c7
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796375"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>Criteri di archiviazione: crearne di nuovi o modificare quelli esistenti
 
Si usano i criteri di archiviazione per controllare l'archiviazione delle comunicazioni interne ed esterne nella distribuzione per gli utenti residenti in Skype for Business Server. I criteri di archiviazione includono il criterio globale e, facoltativamente, uno o più criteri per sito e utente:
  
- **Criteri globali** Il criterio globale viene creato per impostazione predefinita in tutte le distribuzioni di Skype for Business Server. È possibile modificare il criterio globale, ma non eliminarlo. Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.
    
- **Criteri sito (facoltativo)** Puoi specificare uno o più criteri di archiviazione del sito, ognuno dei quali puoi configurare per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un sito specifico. Un criterio sito ha la precedenza sui criteri globali, ma solo per i siti specificati nei criteri di archiviazione. È possibile modificare o eliminare i criteri sito.
    
- **Criteri utente (facoltativo)** Puoi specificare uno o più criteri di archiviazione degli utenti, ognuno dei quali puoi configurare per abilitare e disabilitare l'archiviazione per comunicazioni interne o esterne per un utente specifico. Un criterio utente ha la precedenza sui criteri globali e i criteri sito, ma solo per gli utenti a cui si assegna un criterio utente. È possibile modificare o eliminare i criteri utente.
    
> [!NOTE]
> Se si usa l'integrazione di Exchange per archiviare i dati di archiviazione in Microsoft Exchange, i criteri di Exchange controllano l'archiviazione per gli utenti ospitati in Exchange. Per abilitare l'archiviazione per tali utenti, la cassetta postale dell'utente deve essere posizionata sul blocco sul posto. 
  
Per configurare le impostazioni per un criterio di archiviazione nuovo o esistente, è necessario specificare le opzioni seguenti:
- **Nome** Ogni criterio di archiviazione richiede un nome. Il nome è determinato dal tipo di criterio che si sta aggiungendo o modificando:
    
  - **Criteri globali** Il nome predefinito è Global. È possibile modificarlo in un nome più descrittivo. Ad esempio, contoso North American Organization.
    
  - **Criteri sito** I siti elencati in questa finestra di dialogo includono tutti i siti disponibili nella distribuzione. Fare clic su un singolo sito per selezionarlo. Ad esempio, Redmond Data Center.
    
  - **Criteri utente** Specificare un nome appropriato, ad esempio il nome di un utente specifico o il nome di un gruppo di utenti o di un team nell'organizzazione. Ad esempio, dipartimento legale.
    
- **Descrizione** Questa opzione è facoltativa. Usalo per ottenere dettagli aggiuntivi, ad esempio l'ambito o l'uso dei criteri. Ad esempio, coordina i servizi legali di altri siti.
    
- **Archiviare le comunicazioni interne** Selezionare questa casella di controllo per abilitare l'archiviazione delle comunicazioni nella rete interna. Per impostazione predefinita, questa opzione non è abilitata in alcun criterio.
    
- **Archiviare le comunicazioni esterne** Selezionare questa casella di controllo per consentire l'archiviazione delle comunicazioni che includono utenti esterni, ad esempio utenti remoti (inclusi gli utenti anonimi e PIC-setting) e partner federati. Per impostazione predefinita, questa opzione non è abilitata in alcun criterio.
    
Per informazioni dettagliate sulla funzionalità e le funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [pianificare l'archiviazione in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [distribuire l'archiviazione per Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)e [gestire l'archiviazione in Skype for Business Server](../../../manage/archiving/archiving.md).

