---
title: Conservazione di file di grandi dimensioni allegati a una riunione Skype for Business
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
description: È possibile allegare file a una riunione Skype for Business, che i partecipanti possono quindi aprire e scaricare. I file allegati alle riunioni Skype for Business vengono conservati nelle cassette postali di qualsiasi partecipante la cui cassetta postale è applicata al blocco per controversia legale, a cui è applicato un criterio di conservazione di Microsoft 365 o Office 365 o a un blocco associato a un caso di eDiscovery nel Centro conformità di Microsoft 365. Questo contenuto viene salvato nelle cartelle Elementi ripristinabili dei partecipanti nelle loro cassette postali.
ms.openlocfilehash: 515f8b68db04a7acfc8eab2d7c639157cdb0da8d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100572"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Conservazione di file di grandi dimensioni allegati a una riunione Skype for Business

È possibile allegare file a una riunione Skype for Business, che i partecipanti possono quindi aprire e scaricare. I file allegati alle riunioni Skype for Business vengono conservati nelle cassette postali di qualsiasi partecipante la cui cassetta postale è applicata al blocco per controversia legale, a cui è applicato un criterio di conservazione di Microsoft 365 o Office 365 o a un blocco associato a un caso di eDiscovery nel Centro conformità di Microsoft 365. Questo contenuto viene salvato nelle cartelle **Elementi ripristinabili dei** partecipanti nelle loro cassette postali.
  
I file che vengono conservati nelle cassette postali con blocco vengono indicizzati e possono quindi essere cercati quando si esegue una ricerca di contenuto nel Centro sicurezza durante la ricerca nella cassetta postale &amp; di un partecipante. Tuttavia, i file allegati di dimensioni superiori a 30 MB vengono suddivisi in due o più file più piccoli e salvati come file compressi (zip). Il  *contenuto*  di questi file più piccoli non è indicizzato per la ricerca e potrebbe non essere restituito in una ricerca contenuto. Tuttavia, i *metadati di*  questi file, ad esempio il nome del file e l'autore, vengono indicizzati per la ricerca e potrebbero essere restituiti in una ricerca contenuto.
  
> [!IMPORTANT]
> Le impostazioni MaxReceiveSize e MaxSendSize per una cassetta postale di Exchange Online possono influire sulla possibilità di conservare file di grandi dimensioni dalle riunioni Skype for Business. Le impostazioni predefinite per MaxReceiveSize e MaxSendSize sono rispettivamente 36 MB e 35 MB. Tuttavia, queste impostazioni predefinite sono troppo piccole per conservare qualsiasi file di una riunione Skype for Business di dimensioni superiori a 30 MB. Questo perché Exchange Online usa la codifica Base64 degli allegati dei messaggi e di altri dati binari. Quando un messaggio è codificato, le sue dimensioni vengono aumentate di circa il 33%. Pertanto, per assicurarsi che i file di grandi dimensioni delle riunioni Skype for Business siano mantenuti, è consigliabile aumentare il valore sia per MaxReceiveSize che per MaxSendSize a 39 MB (ovvero circa il 33% più grande del limite di dimensioni di 30 MB spiegato in precedenza) per gli utenti a cui è stato posto un blocco. In caso contrario, un file di grandi dimensioni allegato a una riunione Skype for Business potrebbe non essere mantenuto. Per altre informazioni sull'uso dei comandi **Set-Mailbox -MaxReceiveSize** e **Set-Mailbox -MaxSendSize** in PowerShell di Exchange Online, vedere [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Le cassette postali che non sono in attesa non avranno i dati della riunione salvati. Ad esempio, in una riunione di tre persone in cui le cassette postali di due partecipanti sono contrassegnate per la conservazione, i dati della riunione vengono salvati nelle cassette postali di questi due partecipanti, ma non nella cassetta postale del terzo partecipante, la cui cassetta postale non è in attesa.
  
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Bloccare i trasferimenti di file punto a punto](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)
  
  
