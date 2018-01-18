---
title: Conservazione dei file di grandi dimensioni collegati a un Skype per le riunioni aziendali
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "È possibile allegare file a un Skype per le riunioni aziendali, quali i partecipanti possono quindi aperta e download. File allegati a Skype per le riunioni aziendali vengono mantenuti nelle cassette postali di qualsiasi partecipante la cui cassetta postale viene messa in attesa di conservazione per controversia, è applicato un criterio di conservazione Office 365 o viene messa in attesa associata a un caso eDiscovery in Office 365 Security &amp; Centro conformità. Tale contenuto viene salvato nelle cassette postali di cartelle degli elementi recuperabili dei partecipanti."
ms.openlocfilehash: bf6a3d0df568a043bc569d78ca0942682e936158
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Conservazione dei file di grandi dimensioni collegati a un Skype per le riunioni aziendali

È possibile allegare file a un Skype per le riunioni aziendali, quali i partecipanti possono quindi aperta e download. File allegati a Skype per le riunioni aziendali vengono mantenuti nelle cassette postali di qualsiasi partecipante la cui cassetta postale viene messa in attesa di conservazione per controversia, è applicato un criterio di conservazione Office 365 o viene messa in attesa associata a un caso eDiscovery in Office 365 Security &amp; Centro conformità. Tale contenuto viene salvato nelle cassette postali di cartelle **Degli elementi recuperabili** dei partecipanti.
  
I file che vengono mantenuti nelle cassette postali in attesa sono indicizzati e pertanto possono essere ricercati quando si esegue una ricerca di contenuto per la protezione &amp; centro conformità durante la ricerca delle cassette postali del partecipante. Tuttavia, file allegati che superano MB 39 sono divisa in due o più file di dimensioni ridotte e salvati come file compresso (zip). Il *contenuto* di questi file di dimensioni ridotte non è indicizzato per la ricerca e potrebbe non essere restituito in una ricerca di contenuto. Tuttavia, i *metadati* di questi file (ad esempio il nome di file e l'autore) sono indicizzato per la ricerca e potrebbero essere restituito in una ricerca di contenuto.
  
> [!NOTE]
> Se la cassetta postale è piena o amministratore tenant è configurato per essere minore del valore MB 39 MaxSendSize, caricamento file di dati non verranno mantenuti affatto. Il valore predefinito MaxSendSize è 150 MB, ma gli amministratori tenant possono configurare MaxSendSize sia di circa 1 MB. 
  
Cassette postali che non sono in attesa non avrà eventuali dati delle riunioni salvati. Ad esempio, in una riunione di tre persone nelle cassette postali tra due partecipanti contrassegnate per la conservazione, vengono salvati i dati di riunione per le cassette postali tra i due partecipanti, ma non per la cassetta postale del terzo partecipante, la cui cassetta postale non è in attesa.
  
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzati](create-custom-external-access-policies.md)

[Trasferimenti di file bloccati punto-punto](block-point-to-point-file-transfers.md)

[Impostare i criteri client per l'organizzazione](set-up-client-policies-for-your-organization.md)

[Impostare i criteri relativi alle conferenze nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)
  