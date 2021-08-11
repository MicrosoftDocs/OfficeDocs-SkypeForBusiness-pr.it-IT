---
title: Infrastruttura a chiave pubblica per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype for Business Server si basa sui certificati per l'autenticazione del server e per stabilire una catena di trust tra client e server e tra i diversi ruoli del server. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 e Windows Server 2008 Public Key Infrastructure (PKI) fornisce l'infrastruttura per stabilire e convalidare questa catena di trust.
ms.openlocfilehash: 7b955aa07143cead900a0140ac8ee64fa02ba34ed3945553e376123c7260909d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329490"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Infrastruttura a chiave pubblica per Skype for Business Server
 
Skype for Business Server si basa sui certificati per l'autenticazione del server e per stabilire una catena di trust tra client e server e tra i diversi ruoli del server. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 e Windows Server 2008 Public Key Infrastructure (PKI) fornisce l'infrastruttura per stabilire e convalidare questa catena di trust.
  
I certificati sono ID digitali. Identificano un server per nome e ne specificano le proprietà. Per assicurarsi che le informazioni su un certificato siano valide, il certificato deve essere emesso da un'autorità di certificazione attendibile dai client o da altri server che si connettono al server. Se il server si connette solo ad altri client e server su una rete privata, la CA può essere una CA globale (enterprise). Se il server interagisce con entità all'esterno della rete privata, potrebbe essere necessaria una CA pubblica.
  
Anche se le informazioni del certificato sono valide, deve esistere la possibilità di verificare che il server che presenta il certificato sia effettivamente quello rappresentato dal certificato. È qui che entra Windows'infrastruttura AKI.
  
Ogni certificato è collegato a una chiave pubblica. Il server denominato nel certificato contiene una chiave privata corrispondente nota solo a esso. Un client o un server che stabilisce la connessione utilizza la chiave pubblica per crittografare in modo casuale alcune informazioni e le invia al server. Se il server decrittografa le informazioni e le restituisce come testo normale, l'entità che si connette può essere sicura che il server conserci la chiave privata al certificato e quindi sia il server denominato nel certificato.
  
> [!NOTE]
> Non tutte le CA pubbliche sono conformi ai requisiti dei Skype for Business Server certificati. È consigliabile fare riferimento all'elenco dei fornitori certificati di autorità di certificazione pubblica per le esigenze dei certificati pubblici. Per informazioni dettagliate, vedere [Unified Communications Certificate Partners.](https://go.microsoft.com/fwlink/p/?LinkId=140898) 
  
## <a name="crl-distribution-points"></a>Punti di distribuzione CRL

Skype for Business Server tutti i certificati server devono contenere uno o più punti di distribuzione dell'elenco di revoche di certificati (CRL). I punti di distribuzione CRL sono percorsi da cui è possibile scaricare gli elenchi CRL allo scopo di verificare che il certificato non sia stato revocato dal momento in cui è stato emesso e che il certificato sia ancora entro il periodo di validità. Un punto di distribuzione CRL viene specificato nelle proprietà del certificato come URL ed è in genere HTTP sicuro.
  
## <a name="enhanced-key-usage"></a>Utilizzo chiavi avanzato

Skype for Business Server richiede che tutti i certificati server supportino l'utilizzo chiavi avanzato (EKU) ai fini dell'autenticazione del server. La configurazione del campo EKU per l'autenticazione server significa che il certificato è valido allo scopo di autenticare i server. Questo EKU è essenziale per MTLS. È possibile avere più di una voce nell'EKU, abilitando il certificato per più scopi.
  

