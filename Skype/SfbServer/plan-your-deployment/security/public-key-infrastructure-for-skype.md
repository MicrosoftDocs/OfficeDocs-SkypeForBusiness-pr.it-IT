---
title: Infrastruttura a chiave pubblica per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype for Business Server si basa su certificati per l'autenticazione del server e per stabilire una catena di trust tra client e server e tra i diversi ruoli del server. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 e l'infrastruttura a chiave pubblica (PKI) di Windows Server 2008 forniscono l'infrastruttura per stabilire e convalidare questa catena di trust.
ms.openlocfilehash: 381afce84c1a58d15187547c9cb8fd6f98e84790
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194885"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Infrastruttura a chiave pubblica per Skype for Business Server
 
Skype for Business Server si basa su certificati per l'autenticazione del server e per stabilire una catena di trust tra client e server e tra i diversi ruoli del server. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 e l'infrastruttura a chiave pubblica (PKI) di Windows Server 2008 forniscono l'infrastruttura per stabilire e convalidare questa catena di trust.
  
I certificati sono ID digitali. Identificano un server per nome e ne specificano le proprietà. Per assicurarsi che le informazioni su un certificato siano valide, il certificato deve essere emesso da una CA considerata attendibile dai client o da altri server che si connettono al server. Se il server si connette solo con altri client e server su una rete privata, la CA può essere una CA aziendale. Se il server interagisce con entità esterne alla rete privata, potrebbe essere richiesta una CA pubblica.
  
Anche se le informazioni sul certificato sono valide, ci deve essere un modo per verificare che il server che presenta il certificato sia effettivamente quello rappresentato dal certificato stesso. È qui che entra in gioco la PKI di Windows.
  
Ogni certificato è collegato a una chiave pubblica. Il server indicato sul certificato contiene una chiave privata corrispondente di sua esclusiva conoscenza. Un client o un server che si connette utilizza la chiave pubblica per crittografare una parte di informazioni casuali e la invia al server. Se il server decrittografa le informazioni e le restituisce come testo normale, l'entità che si connette può essere certa che il server detenga la chiave privata corrispondente al certificato e pertanto sia il server indicato sul certificato.
  
> [!NOTE]
> Non tutte le CA pubbliche soddisfano i requisiti dei certificati di Skype for Business Server. Ti consigliamo di fare riferimento all'elenco dei fornitori di CA pubblici certificati per le tue esigenze per i certificati pubblici. Per informazioni dettagliate, vedere [partner certificati](https://go.microsoft.com/fwlink/p/?LinkId=140898)per le comunicazioni unificate. 
  
## <a name="crl-distribution-points"></a>Punti di distribuzione CLR

Skype for Business Server richiede che tutti i certificati del server contengano uno o più punti di distribuzione dell'elenco di revoche di certificati (CRL). I punti di distribuzione CRL (CDP) sono posizioni da cui è possibile scaricare i CRL per verificare che il certificato non sia stato revocato dal momento in cui è stato rilasciato e che rientri ancora nel periodo di validità. Un punto di distribuzione CRL viene indicato nelle proprietà del certificato come URL e in genere è protetto da HTTP.
  
## <a name="enhanced-key-usage"></a>Utilizzo chiavi avanzato

Skype for Business Server richiede tutti i certificati server per supportare l'uso di chiavi avanzate (EKU) ai fini dell'autenticazione del server. La configurazione del campo EKU per l'autenticazione del server indica che il certificato è valido ai fini dell'autenticazione dei server. Tale EKU è essenziale per MTLS. È possibile avere più di una voce in EKU, abilitando il certificato per più di uno scopo.
  

