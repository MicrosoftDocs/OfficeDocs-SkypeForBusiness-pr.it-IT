---
title: Skype for Business dei client Mac
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Leggere questo argomento per informazioni sui requisiti hardware, software e infrastruttura per l'Skype for Business in un Mac.
ms.openlocfilehash: e25995173b44cf4f5892c1a34f77529042125c58
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014470"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype for Business dei client Mac
 
Leggere questo argomento per informazioni sui requisiti hardware, software e infrastruttura per l'Skype for Business in un Mac.
  
Il [Skype for Business sul client Mac](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) è disponibile per il download.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Requisiti hardware e software per Skype for Business mac

Il Skype for Business sul client Mac richiede Mac OS X El Capitan e versioni successive e utilizza almeno 100 MB di spazio su disco. Supportiamo l'uso di tutti i dispositivi audio e video incorporati. I dispositivi esterni devono essere elencati [Microsoft Teams dispositivi](https://www.microsoft.com/microsoft-teams/across-devices/devices). 
  
> [!NOTE]
> Questo elenco è preliminare e alcuni dispositivi possono essere qualificati per Lync, ma non sono supportati Skype for Business sul Mac. Fare riferimento ai [requisiti di sistema](https://products.office.com/office-system-requirements) per l'hardware minimo necessario.
  
### <a name="legacy-mac-clients"></a>Client Mac legacy

Skype for Business Server 2015 supporta anche i client legacy seguenti nei computer che eseguono Sistemi operativi Mac OS 10.5.8 o versioni più recenti (basate su Intel) (il sistema operativo Mac OS 10.9 non è attualmente supportato). Per informazioni dettagliate sulle funzionalità supportate, vedere [Desktop client feature comparison for Skype for Business](desktop-feature-comparison.md).
  
- Microsoft Lync per Mac 2011 (vedere Guida alla distribuzione [di Lync per Mac 2011](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14)))
    
- Microsoft Communicator per Mac 2011 (vedere [Communicator per Mac 2011 Deployment Guide](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14)))
 
Questi client non sono supportati da Skype for Business Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Requisiti dell'infrastruttura Skype for Business su Mac
<a name="Infrastructure"> </a>

Il Skype for Business sul client Mac sfrutta sia UCMP (Unified Communications Management Platform) che UCWA (Unified Communications Web API) usate dai client per dispositivi mobili.
  
Il client ha gli stessi requisiti dei client per dispositivi mobili in quanto è necessario disporre di un server Access Edge e di un proxy inverso distribuiti in una configurazione supportata. 
  
### <a name="authentication"></a>Autenticazione

Il Skype for Business sul client Mac supporta l'autenticazione basata su certificato, l'autenticazione moderna Microsoft e l'autenticazione a più fattori quando viene distribuita e abilitata.
  
> [!NOTE]
> A causa di una limitazione corrente, le credenziali dell'Exchange dell'utente devono essere uguali a Skype for Business credenziali. 
  
### <a name="certificates"></a>Certificati

I certificati in uso nei server Access Edge, Proxy inverso e Front End server non devono utilizzare l'algoritmo hash SHA-512.
  
L'elenco di revoche di certificati HTTP deve essere definito e accessibile dal client. Ad esempio, non supportiamo una voce LDAP nel certificato come elenco di revoche di certificati.
  
### <a name="dns"></a>DNS

I dispositivi mobili devono essere distribuiti correttamente per Skype for Business sul client Mac per funzionare correttamente. Uno scenario di errore comune consiste nel fatto che entrambe le voci DNS seguenti possono essere risolvibili nella rete interna:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Per ulteriori informazioni, vedere: [Deploying Mobility in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)e [Microsoft Lync Server 2010 Mobility Guide](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Vedere anche
<a name="Infrastructure"> </a>

[Requisiti DNS per Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Domande frequenti](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problemi noti](https://go.microsoft.com/fwlink/p/?LinkId=798228)