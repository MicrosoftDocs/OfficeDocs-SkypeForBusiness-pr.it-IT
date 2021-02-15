---
title: Requisiti del client Skype for Business su Mac
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Leggi questo argomento per informazioni sui requisiti hardware, software e infrastruttura per l'esecuzione di Skype for Business in un Mac.
ms.openlocfilehash: 5f967bab3a5dcc41a3419324c9fe09b48a8fb674
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832166"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Requisiti del client Skype for Business su Mac
 
Leggi questo argomento per informazioni sui requisiti hardware, software e infrastruttura per l'esecuzione di Skype for Business in un Mac.
  
Il [client Skype for Business su Mac](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) è disponibile per il download.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Requisiti hardware e software per Skype for Business su Mac

Il client Skype for Business su Mac richiede Mac OS X El Suo e versioni successive e utilizza almeno 100 MB di spazio su disco. Supportiamo l'uso di tutti i dispositivi audio e video incorporati. I dispositivi esterni devono essere nel [Catalogo soluzioni Skype for Business.](https://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
> [!NOTE]
> Questo elenco è preliminare e alcuni dispositivi possono essere qualificati per Lync, ma non sono supportati in Skype for Business sul Mac. Fare riferimento ai requisiti [di sistema](https://products.office.com/office-system-requirements) per l'hardware minimo necessario.
  
### <a name="legacy-mac-clients"></a>Client Mac legacy

Skype for Business Server 2015 supporta anche i client legacy seguenti nei computer che eseguono i sistemi operativi Mac OS 10.5.8 o versione più recente (basata su Intel) (il sistema operativo Mac OS 10.9 non è attualmente supportato). Per informazioni dettagliate sulle funzionalità supportate, vedere [Confronto delle funzionalità del client desktop per Skype for Business.](desktop-feature-comparison.md)
  
- Microsoft Lync per Mac 2011 (vedere la Guida alla distribuzione di [Lync per Mac 2011)](https://go.microsoft.com/fwlink/p/?LinkId=268786)
    
- Microsoft Communicator per Mac 2011 (vedere [Communicator per Mac 2011 Deployment Guide)](https://go.microsoft.com/fwlink/p/?LinkId=268787)
 
Questi client non sono supportati da Skype for Business Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Requisiti dell'infrastruttura per Skype for Business su Mac
<a name="Infrastructure"> </a>

Il client Skype for Business su Mac sfrutta sia UCMP (Unified Communications Management Platform) che UCWA (Unified Communications Web API) usate dai client per dispositivi mobili.
  
Il client ha gli stessi requisiti dei client per dispositivi mobili in quanto è necessario disporre di un access edge server e di un proxy inverso distribuiti in una configurazione supportata. 
  
### <a name="authentication"></a>Autenticazione

Il client Skype for Business su Mac supporta l'autenticazione basata su certificato, l'autenticazione moderna Microsoft e l'autenticazione a più fattori quando viene distribuita e abilitata.
  
> [!NOTE]
> A causa di una limitazione corrente, le credenziali di Exchange dell'utente devono essere le stesse delle credenziali di Skype for Business. 
  
### <a name="certificates"></a>Certificati

I certificati in uso nei server Access Edge, Proxy inverso e Front End Server non devono utilizzare l'algoritmo hash SHA-512.
  
L'elenco di revoche di certificati HTTP deve essere definito e accessibile dal client. Ad esempio, non è possibile supportare una voce LDAP nel certificato come elenco di revoche di certificati.
  
### <a name="dns"></a>DNS

La mobilità deve essere distribuita correttamente per il corretto funzionamento di Skype for Business sul client Mac. Uno scenario di errore comune consiste nell'avere entrambe le voci DNS seguenti risolvibili nella rete interna:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Per ulteriori informazioni, vedere: Distribuzione di dispositivi mobili [in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)e Guida per dispositivi mobili di [Microsoft Lync Server 2010.](https://go.microsoft.com/fwlink//p/?LinkId=798226)
  
## <a name="see-also"></a>Vedere anche
<a name="Infrastructure"> </a>

[Requisiti DNS per Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Domande frequenti](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemi noti](https://go.microsoft.com/fwlink/p/?LinkId=798228)
