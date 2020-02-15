---
title: Requisiti client Skype for business su Mac
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
description: Leggere questo argomento per informazioni sui requisiti hardware, software e dell'infrastruttura per l'esecuzione di Skype for business su un Mac.
ms.openlocfilehash: f4f62246a86dabeb628755d3c75a10bc285ede12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42013459"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Requisiti client Skype for business su Mac
 
Leggere questo argomento per informazioni sui requisiti hardware, software e dell'infrastruttura per l'esecuzione di Skype for business su un Mac.
  
Il [client Skype for business su Mac](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) è disponibile per il download.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Requisiti hardware e software per Skype for business su Mac

Il client Skype for business su Mac richiede Mac OS X El Capitan e versioni successive e utilizza almeno 100 MB di spazio su disco. È supportato l'utilizzo di tutti i dispositivi audio e video incorporati. I dispositivi esterni devono trovarsi nel [Catalogo di soluzioni Skype for business](https://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
> [!NOTE]
> Questo elenco è preliminare e alcuni dispositivi possono essere qualificati per Lync, ma non sono supportati su Skype for business sul Mac. Fare riferimento ai [requisiti di sistema](https://products.office.com/office-system-requirements) per l'hardware minimo necessario.
  
### <a name="legacy-mac-clients"></a>Client Mac legacy

Skype for Business Server 2015 supporta anche i client legacy seguenti nei computer che eseguono sistemi operativi Mac OS 10.5.8 o Service Pack o release più recenti (basati su processore Intel) (il sistema operativo Mac OS 10,9 non è attualmente supportato). Per informazioni dettagliate sulle funzionalità supportate, vedere [confronto delle caratteristiche dei client desktop per Skype for business](desktop-feature-comparison.md).
  
- Microsoft Lync per Mac 2011 (vedere [Guida alla distribuzione di Lync per mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator per Mac 2011 (vedere [Guida alla distribuzione di Communicator per mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Questi client non sono supportati da Skype for Business Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Requisiti dell'infrastruttura per Skype for business su Mac
<a name="Infrastructure"> </a>

Il client Skype for business su Mac sfrutta sia la piattaforma Unified Communications Management (UCMP), sia l'API Unified Communications Web (UCWA) utilizzata dai client per dispositivi mobili.
  
Il client ha gli stessi requisiti dei client per dispositivi mobili, in quanto è necessario disporre di un server Access Edge e di un proxy inverso distribuito in una configurazione supportata. 
  
### <a name="authentication"></a>Autenticazione

Il client Skype for business su Mac supporta l'autenticazione basata su cert, l'autenticazione moderna Microsoft e l'autenticazione a più fattori quando vengono distribuite e abilitate.
  
> [!NOTE]
> A causa di una limitazione corrente, le credenziali di Exchange dell'utente devono corrispondere alle credenziali Skype for business. 
  
### <a name="certificates"></a>Certificati

I certificati in uso sul server perimetrale di accesso, il proxy inverso e front end non devono utilizzare l'algoritmo hash SHA-512.
  
È necessario che l'elenco di revoche di certificati HTTP sia definito e accessibile dal client. Ad esempio, non è supportata una voce LDAP nel certificato come elenco di revoche di certificati.
  
### <a name="dns"></a>DNS

La mobilità deve essere distribuita correttamente affinché il client Skype for business sul Mac funzioni correttamente. Uno scenario di errore comune consiste nel fatto che entrambe le voci DNS seguenti sono risolvibili nella rete interna:
  
- LyncdiscoverInternal. \<SipDomain\>
    
- Lyncdiscover. \<SipDomain\>
    
Per ulteriori informazioni, vedere la sezione relativa alla [distribuzione di dispositivi mobili in Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)e alla [Guida per dispositivi mobili di Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Vedere anche
<a name="Infrastructure"> </a>

[Requisiti DNS per Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Domande frequenti](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemi noti](https://go.microsoft.com/fwlink/p/?LinkId=798228)
