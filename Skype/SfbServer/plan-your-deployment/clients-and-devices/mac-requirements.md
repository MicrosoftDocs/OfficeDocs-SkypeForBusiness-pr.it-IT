---
title: Requisiti client Skype for business per Mac
ms.author: v-lanac
author: lanachin
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
description: Leggere questo argomento per informazioni sui requisiti di hardware, software e infrastrutture per l'uso di Skype for business in un Mac.
ms.openlocfilehash: 08f3aeabbfd88b432c28f05727ec7cf009e297a7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803596"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Requisiti client Skype for business per Mac
 
Leggere questo argomento per informazioni sui requisiti di hardware, software e infrastrutture per l'uso di Skype for business in un Mac.
  
Il [client Skype for business per Mac](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) è disponibile per il download.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Requisiti hardware e software per Skype for business per Mac

Il client Skype for business per Mac richiede Mac OS X El Capitan e versioni successive e usa almeno 100 MB di spazio su disco. Supportiamo l'uso di tutti i dispositivi audio e video predefiniti. I dispositivi esterni devono essere nel [Catalogo di soluzioni Skype for business](https://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
> [!NOTE]
> Questo elenco è preliminare e alcuni dispositivi possono essere qualificati per Lync, ma non supportati in Skype for business per Mac. Vedere i [requisiti di sistema](https://products.office.com/en-us/office-system-requirements) per l'hardware minimo necessario.
  
### <a name="legacy-mac-clients"></a>Client Mac legacy

Skype for Business Server 2015 supporta anche i client legacy seguenti nei computer in cui sono in uso sistemi operativi Mac OS 10.5.8 o ultimo Service Pack o Release (basato su Intel) (il sistema operativo Mac OS 10,9 non è attualmente supportato). Per informazioni dettagliate sulle caratteristiche supportate, vedere [confronto tra funzionalità client desktop per Skype for business](desktop-feature-comparison.md).
  
- Microsoft Lync per Mac 2011 (vedere [Guida alla distribuzione di Lync per mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator per Mac 2011 (vedere [Guida alla distribuzione di Communicator per mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Questi client non sono supportati da Skype for Business Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Requisiti per l'infrastruttura per Skype for business per Mac
<a name="Infrastructure"> </a>

Il client Skype for business per Mac sfrutta sia la piattaforma UCMP (Unified Communications Management Platform) che l'API Unified Communications Web (UCWA) che i client di mobilità usano.
  
Il client ha gli stessi requisiti dei client di mobilità in quanto è necessario disporre di un server perimetrale di Access e di un proxy inverso distribuito in una configurazione supportata. 
  
### <a name="authentication"></a>Autenticazione

Il client Skype for business per Mac supporta l'autenticazione basata su cert, l'autenticazione Microsoft Modern e l'autenticazione a più fattori quando vengono distribuiti e abilitati.
  
> [!NOTE]
> A causa di una limitazione corrente, le credenziali di Exchange dell'utente devono essere le stesse delle credenziali di Skype for business. 
  
### <a name="certificates"></a>Certificati

I certificati in uso in Access Edge, proxy inverso e server front end non devono usare l'algoritmo hash SHA-512.
  
L'elenco di revoche di certificati HTTP deve essere definito e accessibile dal client. Ad esempio, non è supportata una voce LDAP nel certificato come elenco di revoche di certificati.
  
### <a name="dns"></a>DNS

La mobilità deve essere distribuita correttamente affinché il client Skype for business sul Mac funzioni correttamente. Uno scenario di errore comune consiste nell'avere entrambe le voci DNS seguenti risolvibili nella rete interna:
  
- lyncdiscoverinternal. \<SipDomain\>
    
- Lyncdiscover. \<SipDomain\>
    
Per altre informazioni, vedere: [distribuzione della mobilità in Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)e guida alla [mobilità di Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Vedere anche
<a name="Infrastructure"> </a>

[Requisiti DNS per Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Domande frequenti](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemi noti](https://go.microsoft.com/fwlink/p/?LinkId=798228)
