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
description: Skype for Business Server si basa su certificati per l'autenticazione del server e per stabilire una catena di attendibilità tra client e server e tra i diversi ruoli del server. L'infrastruttura a chiave pubblica (PKI) di Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 e Windows Server 2008 fornisce l'infrastruttura per la creazione e la convalida della catena di attendibilità.
ms.openlocfilehash: 3ee9411b5a9259ba7c66c46bf657bb5ee43ab52e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832146"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Infrastruttura a chiave pubblica per Skype for Business Server
 
Skype for Business Server si basa su certificati per l'autenticazione del server e per stabilire una catena di attendibilità tra client e server e tra i diversi ruoli del server. L'infrastruttura a chiave pubblica (PKI) di Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 e Windows Server 2008 fornisce l'infrastruttura per la creazione e la convalida della catena di attendibilità.
  
I certificati sono ID digitali. Identificano un server per nome e ne specificano le proprietà. Per assicurarsi che le informazioni su un certificato siano valide, è necessario che il certificato venga emesso da un'autorità di certificazione attendibile dai client o da altri server che si connettono al server. Se il server si connette solo ad altri client e server su una rete privata, la CA può essere una CA globale (enterprise). Se il server interagisce con entità all'esterno della rete privata, potrebbe essere necessaria una CA pubblica.
  
Anche se le informazioni del certificato sono valide, deve esistere la possibilità di verificare che il server che presenta il certificato sia effettivamente quello rappresentato dal certificato. Questa è la posizione in cui viene fornita la PKI di Windows.
  
Ogni certificato è collegato a una chiave pubblica. Il server denominato nel certificato contiene una chiave privata corrispondente nota solo a esso. Un client o un server che stabilisce la connessione utilizza la chiave pubblica per crittografare in modo casuale alcune informazioni e le invia al server. Se il server esegue la decrittografia delle informazioni e lo restituisce come testo normale, l'entità di connessione può essere sicura che il server contenga la chiave privata per il certificato e che sia quindi il server denominato sul certificato.
  
> [!NOTE]
> Non tutte le autorità di certificazione pubbliche sono conformi ai requisiti dei certificati di Skype for Business Server. Si consiglia di fare riferimento all'elenco dei fornitori di autorità di certificazione pubblica certificati per le proprie esigenze di certificato pubblico. Per informazioni dettagliate, vedere [Unified Communications Certificate Partners](https://go.microsoft.com/fwlink/p/?LinkId=140898). 
  
## <a name="crl-distribution-points"></a>Punti di distribuzione CRL

Skype for Business Server richiede che tutti i certificati del server contengano uno o più punti di distribuzione dell'elenco di revoche di certificati (CRL). I punti di distribuzione CRL (CDP) sono percorsi da cui è possibile scaricare i CRL allo scopo di verificare che il certificato non sia stato revocato dal momento in cui è stato emesso e che il certificato sia ancora entro il periodo di validità. Un punto di distribuzione CRL è indicato nelle proprietà del certificato come URL ed è in genere HTTP sicuro.
  
## <a name="enhanced-key-usage"></a>Utilizzo chiavi avanzato

Skype for Business Server richiede che tutti i certificati del server supportino l'utilizzo delle chiavi avanzato (EKU, Enhanced Key Usage) ai fini dell'autenticazione del server. La configurazione del campo EKU per l'autenticazione del server indica che il certificato è valido ai fini dell'autenticazione dei server. Questo EKU è essenziale per MTLS. È possibile avere più di una voce in EKU, abilitando il certificato per più di uno scopo.
  

