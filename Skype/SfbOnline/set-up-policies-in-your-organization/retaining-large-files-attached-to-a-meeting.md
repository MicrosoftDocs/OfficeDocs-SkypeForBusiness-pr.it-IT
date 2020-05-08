---
title: Mantenere file di grandi dimensioni allegati a una riunione Skype for business
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: È possibile allegare file a una riunione Skype for business, che i partecipanti possono aprire e scaricare. I file allegati alle riunioni Skype for business vengono conservati nelle cassette postali di qualsiasi partecipante la cui cassetta postale è inserita nel blocco per controversia legale, ha un criterio di conservazione di Microsoft 365 o Office 365 applicato o viene inserito in un blocco associato a un caso di eDiscovery nel centro conformità di Microsoft 365. Questo contenuto viene salvato nelle cartelle elementi ripristinabili dei partecipanti nelle cassette postali.
ms.openlocfilehash: 23566272cec4f1afef2a0a067fdebdd2f497e312
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164075"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Mantenere file di grandi dimensioni allegati a una riunione Skype for business

È possibile allegare file a una riunione Skype for business, che i partecipanti possono aprire e scaricare. I file allegati alle riunioni Skype for business vengono conservati nelle cassette postali di qualsiasi partecipante la cui cassetta postale è inserita nel blocco per controversia legale, ha un criterio di conservazione di Microsoft 365 o Office 365 applicato o viene inserito in un blocco associato a un caso di eDiscovery nel centro conformità di Microsoft 365. Questo contenuto viene salvato nelle cartelle **elementi ripristinabili** dei partecipanti nelle cassette postali.
  
I file conservati nelle cassette postali in blocco vengono indicizzati e possono quindi essere cercati durante l'esecuzione di una ricerca &amp; contenuto nel centro conformità della sicurezza durante la ricerca nella cassetta postale di un partecipante. Tuttavia, i file allegati di dimensioni maggiori di 30 MB vengono divisi in due o più file più piccoli e salvati come file compressi (con estensione zip). Il *contenuto* di questi file più piccoli non viene indicizzato per la ricerca e potrebbe non essere restituito in una ricerca contenuto. Tuttavia, i *metadati* di questi file, ad esempio il nome e l'autore del file, vengono indicizzati per la ricerca e potrebbero essere restituiti in una ricerca contenuto.
  
> [!IMPORTANT]
> Le impostazioni di MaxReceiveSize e MaxSendSize per una cassetta postale di Exchange Online possono influire sulla possibilità di mantenere i file di grandi dimensioni dalle riunioni Skype for business. Le impostazioni predefinite per MaxReceiveSize e MaxSendSize sono rispettivamente 36 MB e 35 MB. Tuttavia, queste impostazioni predefinite sono troppo piccole per conservare qualsiasi file da una riunione Skype for business di dimensioni maggiori di 30 MB. Il motivo è che Exchange Online USA la codifica Base64 degli allegati dei messaggi e di altri dati binari. Quando un messaggio viene codificato, la relativa dimensione viene aumentata di circa 33%. Per fare in modo che i file di grandi dimensioni provenienti da riunioni Skype for business vengano mantenuti, ti consigliamo di aumentare il valore sia per MaxReceiveSize che per MaxSendSize in 39 MB (che è approssimativamente 33% più grande del limite di 30 MB che è stato precedentemente spiegato) per gli utenti che sono stati messi in attesa. In caso contrario, un file di grandi dimensioni allegato a una riunione Skype for business potrebbe non essere mantenuto. Per altre informazioni sull'uso dei comandi **Set-Mailbox-MaxReceiveSize** e **Set-Mailbox-MaxSendSize** in Exchange Online PowerShell, vedere [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Le cassette postali non bloccate non avranno salvato i dati della riunione. Ad esempio, in una riunione di tre persone in cui le cassette postali di due partecipanti sono contrassegnate per la conservazione, i dati della riunione vengono salvati nelle cassette postali di questi due partecipanti, ma non nella cassetta postale del terzo partecipante, la cui cassetta postale non è in attesa.
  
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Bloccare i trasferimenti di file Point-to-Point](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)
  
  
 
