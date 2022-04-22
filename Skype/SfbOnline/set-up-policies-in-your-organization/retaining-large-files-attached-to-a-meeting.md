---
title: Conservare file di grandi dimensioni allegati a una riunione Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, v-tophillips
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: È possibile allegare file a una Skype for Business riunione, che i partecipanti possono quindi aprire e scaricare. I file allegati a riunioni Skype for Business vengono conservati nelle cassette postali di qualsiasi partecipante la cui cassetta postale è applicata a un blocco per controversia legale, a cui è applicato un criterio di conservazione Microsoft 365 o Office 365 o a un blocco associato a un caso di eDiscovery nel portale di conformità Microsoft Purview. Questo contenuto viene salvato nelle cartelle Elementi ripristinabili dei partecipanti nelle loro cassette postali.
ms.openlocfilehash: b799c1a471ac3884aa1b22cc1a681e53ee8284e9
ms.sourcegitcommit: 7d5266ae7e4a440ee45ab1873a30f4056bdcca1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031871"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Conservare file di grandi dimensioni allegati a una riunione Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

È possibile allegare file a una Skype for Business riunione, che i partecipanti possono quindi aprire e scaricare. I file allegati a riunioni Skype for Business vengono conservati nelle cassette postali di qualsiasi partecipante la cui cassetta postale è applicata a un blocco per controversia legale, a cui è applicato un criterio di conservazione Microsoft 365 o Office 365 o a un blocco associato a un caso di eDiscovery nel portale di conformità Microsoft Purview. Questo contenuto viene salvato nelle cartelle **Elementi ripristinabili** dei partecipanti nelle loro cassette postali.
  
I file conservati nelle cassette postali bloccate vengono indicizzati e pertanto possono essere cercati durante l'esecuzione di una ricerca contenuto nel Centro conformità sicurezza &amp; durante la ricerca nella cassetta postale di un partecipante. Tuttavia, i file allegati di dimensioni superiori a 30 MB vengono suddivisi in due o più file più piccoli e salvati come file compressi (.zip). Il  *contenuto*  di questi file più piccoli non viene indicizzato per la ricerca e potrebbe non essere restituito in una ricerca contenuto. Tuttavia, i *metadati*  di questi file, ad esempio il nome file e l'autore, vengono indicizzati per la ricerca e possono essere restituiti in una ricerca contenuto.
  
> [!IMPORTANT]
> Le impostazioni MaxReceiveSize e MaxSendSize per una cassetta postale di Exchange Online possono influire sulla possibilità di conservare file di grandi dimensioni da Skype for Business riunioni. Le impostazioni predefinite per MaxReceiveSize e MaxSendSize sono rispettivamente di 36 MB e 35 MB. Tuttavia, queste impostazioni predefinite sono troppo piccole per conservare qualsiasi file di una riunione Skype for Business di dimensioni maggiori di 30 MB. Il motivo è che Exchange Online usa la codifica Base64 per gli allegati dei messaggi e altri dati binari. Quando un messaggio viene codificato, le sue dimensioni vengono aumentate di circa il 33%. Pertanto, per assicurarsi che i file di grandi dimensioni di Skype for Business riunioni vengano mantenuti, è consigliabile aumentare il valore sia per MaxReceiveSize che per MaxSendSize a 39 MB (circa il 33% in più del limite di dimensioni di 30 MB illustrato in precedenza) per gli utenti a cui è stato applicato un blocco. In caso contrario, un file di grandi dimensioni allegato a una riunione di Skype for Business potrebbe non essere conservato. Per altre informazioni sull'uso dei comandi **Set-Mailbox -MaxReceiveSize** e **Set-Mailbox -MaxSendSize** in Exchange Online PowerShell, vedere [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Le cassette postali non bloccate non avranno alcun dato sulla riunione salvato. Ad esempio, in una riunione con tre persone in cui le cassette postali di due partecipanti sono contrassegnate per la conservazione, i dati della riunione vengono salvati nelle cassette postali di questi due partecipanti, ma non nella cassetta postale del terzo partecipante, la cui cassetta postale non è in attesa.
  
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Bloccare i trasferimenti di file punto a punto](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)
  
  
