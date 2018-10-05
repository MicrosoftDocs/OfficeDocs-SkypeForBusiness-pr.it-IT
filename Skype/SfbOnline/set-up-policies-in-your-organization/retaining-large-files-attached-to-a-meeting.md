---
title: Conservazione dei file di grandi dimensioni collegati a un Skype per le riunioni aziendali
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: È possibile allegare file a un Skype per le riunioni aziendali, quali i partecipanti possono quindi aperta e download. File allegati a Skype per le riunioni aziendali vengono mantenuti nelle cassette postali di qualsiasi partecipante la cui cassetta postale viene messa in attesa di conservazione per controversia, è applicato un criterio di conservazione Office 365 o viene messa in attesa associata a un caso eDiscovery in Office 365 Security &amp; Centro conformità. Tale contenuto viene salvato nelle cassette postali di cartelle degli elementi recuperabili dei partecipanti.
ms.openlocfilehash: 103fa8b9602c4db1c5399a97a94613ac8e7b8621
ms.sourcegitcommit: 2e11749734ff26b18709a1442b2c417f33430144
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2018
ms.locfileid: "25429382"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Conservazione dei file di grandi dimensioni collegati a un Skype per le riunioni aziendali

È possibile allegare file a un Skype per le riunioni aziendali, quali i partecipanti possono quindi aperta e download. File allegati a Skype per le riunioni aziendali vengono mantenuti nelle cassette postali di qualsiasi partecipante la cui cassetta postale viene messa in attesa di conservazione per controversia, è applicato un criterio di conservazione Office 365 o viene messa in attesa associata a un caso eDiscovery in Office 365 Security &amp; Centro conformità. Tale contenuto viene salvato nelle cassette postali di cartelle **Degli elementi recuperabili** dei partecipanti.
  
I file che vengono mantenuti nelle cassette postali in attesa sono indicizzati e pertanto possono essere ricercati quando si esegue una ricerca di contenuto per la protezione &amp; centro conformità durante la ricerca delle cassette postali del partecipante. Tuttavia, file allegati di dimensioni superiori a 30 MB sono divisa in due o più file di dimensioni ridotte e salvati come file compresso (zip). Il *contenuto* di questi file di dimensioni ridotte non è indicizzato per la ricerca e potrebbe non essere restituito in una ricerca di contenuto. Tuttavia, i *metadati* di questi file (ad esempio il nome di file e l'autore) sono indicizzato per la ricerca e potrebbero essere restituito in una ricerca di contenuto.
  
> [!NOTE]
> Se la cassetta postale è piena o l'amministratore tenant configurato MaxSendSize per essere inferiore a 30 MB, i dati di file caricato non saranno conservati affatto. Il valore predefinito MaxSendSize è 150 MB, ma gli amministratori tenant possono configurare MaxSendSize sia di circa 1 MB. 
  
Cassette postali che non sono in attesa non avrà eventuali dati delle riunioni salvati. Ad esempio, in una riunione di tre persone nelle cassette postali tra due partecipanti contrassegnate per la conservazione, vengono salvati i dati di riunione per le cassette postali tra i due partecipanti, ma non per la cassetta postale del terzo partecipante, la cui cassetta postale non è in attesa.
  
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Trasferimenti di file bloccati punto-punto](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Impostare i criteri relativi alle conferenze nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)
  
  
 