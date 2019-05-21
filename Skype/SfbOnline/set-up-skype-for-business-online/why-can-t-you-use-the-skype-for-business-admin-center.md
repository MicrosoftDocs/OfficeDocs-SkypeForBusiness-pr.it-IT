---
title: Perché non è possibile usare l'interfaccia di amministrazione di Skype for business online in questo momento?
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.lync.lac.TenantInMigration
ms.custom:
- Setup
description: "Informazioni su cosa è possibile e non si può usare nell'interfaccia di amministrazione di Skype for business e altre funzionalità quando il servizio viene migrato in un altro centro dati Microsoft. "
ms.openlocfilehash: 006caf6542abfeeb38e9563b6866fb119c47b88f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284878"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a>Perché non è possibile usare l'interfaccia di amministrazione di Skype for business online in questo momento?

Sappiamo che è frustrante quando non è possibile eseguire il lavoro, quindi spiegheremo cosa sta succedendo e perché varrà l'attesa. 
  
Prima di tutto, ecco la spiegazione tecnica:
  
Stiamo migrando il servizio Skype for business online (ovvero gli utenti e le impostazioni dell'organizzazione) in un altro centro dati Microsoft più vicino. Questo migliorerà il servizio e ridurrà la latenza. 
  
Per altri dettagli tecnici, vedere [durante e dopo lo stato di trasferimento dei dati]( https://go.microsoft.com/fwlink/?LinkId=526418).
  
## <a name="ok-so-what-does-that-mean"></a>OK, cosa significa?

Per prima cosa, analizziamo alcuni termini.
  
- **Data Center** Questa è la posizione fisica in cui sono archiviate le informazioni dell'organizzazione di Office 365, ad esempio i file e i messaggi di posta elettronica. Se si vuole veramente analizzare i dati di Office 365, vedere[questo articolo](https://www.microsoft.com/online/legal/v2/?docid=25).
    
- **Migrazione** Questo è più o meno uguale a "spostamento". In questo caso, significa che stiamo spostando gli utenti e le impostazioni di Skype for business online da un centro dati a un altro più vicino a te per migliorare il servizio.
    
- **Latenza** Questo è il periodo di tempo necessario per accedere all'interfaccia di amministrazione di Office 365, apportare una modifica alle impostazioni e quindi salvare le modifiche.
    
- **ID correlazione** Potrebbe essere visualizzato questo elenco nel messaggio appena uscito. Queste informazioni vengono usate dagli ingegneri del supporto Microsoft per aiutarti a risolvere un errore. Se si contatta il supporto Microsoft, è possibile che venga richiesto l'ID di correlazione.
    
Questo significa che stiamo spostando tutti gli utenti e le impostazioni di servizio di Skype for business online in un'altra posizione più vicina a te. Maggiore è il miglioramento. La buona notizia è che dopo questo breve periodo di tempo, il servizio Skype for business online migliorerà.
  
![Migrazione del servizio in Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a>Quali funzionalità di Skype for business online funzionano ancora?

Anche se non è possibile accedere all'interfaccia di amministrazione di Skype for business online, le caratteristiche seguenti di Skype for business online continueranno a funzionare durante la migrazione:
  
- Riunioni online
    
- Informazioni sulla presenza
    
## <a name="can-i-get-other-work-done"></a>È possibile eseguire altre operazioni?

Sicuro. Mentre si sta migrando il servizio Skype for business online, è comunque possibile usare gli altri centri di amministrazione di Office 365, ad esempio Office 365 ed Exchange Admin Centers. Tuttavia, insieme all'interfaccia di amministrazione di Skype for business online, non potrai usare i cmdlet di PowerShell remoto di Skype for business online durante la migrazione. 
  
## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
