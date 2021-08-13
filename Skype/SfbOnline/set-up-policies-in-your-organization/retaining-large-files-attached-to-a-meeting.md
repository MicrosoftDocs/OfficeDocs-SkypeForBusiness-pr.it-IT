---
title: Conservazione di file di grandi dimensioni allegati a una Skype for Business riunione
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
description: È possibile allegare file a una Skype for Business riunione, che i partecipanti possono quindi aprire e scaricare. I file allegati alle riunioni di Skype for Business vengono conservati nelle cassette postali di qualsiasi partecipante la cui cassetta postale è applicata al blocco per controversia legale, a cui è applicato un criterio di conservazione Microsoft 365 o Office 365 oppure a un blocco associato a un caso di eDiscovery nel Centro conformità di Microsoft 365. Questo contenuto viene salvato nelle cartelle Elementi ripristinabili dei partecipanti nelle loro cassette postali.
ms.openlocfilehash: 10d793afce0485de749a5609b77f2c769c55fa9d5305a4a815351ef62ff9a8b3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54316492"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Conservazione di file di grandi dimensioni allegati a una Skype for Business riunione

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

È possibile allegare file a una Skype for Business riunione, che i partecipanti possono quindi aprire e scaricare. I file allegati alle riunioni di Skype for Business vengono conservati nelle cassette postali di qualsiasi partecipante la cui cassetta postale è applicata al blocco per controversia legale, a cui è applicato un criterio di conservazione Microsoft 365 o Office 365 oppure a un blocco associato a un caso di eDiscovery nel Centro conformità di Microsoft 365. Questo contenuto viene salvato nelle cartelle **Elementi ripristinabili dei** partecipanti nelle loro cassette postali.
  
I file che vengono conservati nelle cassette postali con blocco vengono indicizzati e possono quindi essere cercati quando si esegue una ricerca di contenuto nel Centro sicurezza durante la ricerca nella cassetta postale &amp; di un partecipante. Tuttavia, i file allegati di dimensioni superiori a 30 MB vengono suddivisi in due o più file più piccoli e salvati come file compressi (.zip). Il  *contenuto*  di questi file più piccoli non è indicizzato per la ricerca e potrebbe non essere restituito in una ricerca contenuto. Tuttavia, i *metadati di*  questi file, ad esempio il nome del file e l'autore, vengono indicizzati per la ricerca e potrebbero essere restituiti in una ricerca contenuto.
  
> [!IMPORTANT]
> Le impostazioni MaxReceiveSize e MaxSendSize per una cassetta postale di Exchange Online possono influire sulla possibilità di conservare file di grandi dimensioni Skype for Business riunioni. Le impostazioni predefinite per MaxReceiveSize e MaxSendSize sono rispettivamente 36 MB e 35 MB. Tuttavia, queste impostazioni predefinite sono troppo piccole per conservare qualsiasi file Skype for Business riunione con dimensioni superiori a 30 MB. Questo perché Exchange Online codifica Base64 degli allegati dei messaggi e di altri dati binari. Quando un messaggio è codificato, le sue dimensioni vengono aumentate di circa il 33%. Pertanto, per assicurarsi che i file di grandi dimensioni delle riunioni di Skype for Business siano mantenuti, è consigliabile aumentare il valore sia per MaxReceiveSize che per MaxSendSize a 39 MB (ovvero circa il 33% più grande del limite di dimensioni di 30 MB spiegato in precedenza) per gli utenti a cui è stato aggiunto un blocco. In caso contrario, un file di grandi dimensioni allegato a Skype for Business riunione potrebbe non essere mantenuto. Per altre informazioni sull'uso dei comandi **Set-Mailbox -MaxReceiveSize** e **Set-Mailbox -MaxSendSize** in Exchange Online PowerShell, vedere [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Le cassette postali che non sono in attesa non avranno i dati della riunione salvati. Ad esempio, in una riunione di tre persone in cui le cassette postali di due partecipanti sono contrassegnate per la conservazione, i dati della riunione vengono salvati nelle cassette postali di questi due partecipanti, ma non nella cassetta postale del terzo partecipante, la cui cassetta postale non è in attesa.
  
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Bloccare i trasferimenti di file punto a punto](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)
  
  
