---
title: Requisiti minimi di rete per l'app Riunioni Skype
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Riepilogo: informazioni per le organizzazioni che non utilizzano Microsoft 365 o Office 365 e devono accedere alle riunioni ospitate da organizzazioni che lo fanno.'
ms.openlocfilehash: 656f8fa52f4a1080cca0b8464becf77c8c2a0ef0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219726"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisiti minimi di rete per l'app Riunioni Skype
 
**Riepilogo:**  Informazioni per le organizzazioni che non utilizzano Microsoft 365 o Office 365 e devono accedere alle riunioni ospitate da organizzazioni che lo fanno. Questo articolo non è destinato agli utenti di queste app.
  
Per consentire agli utenti di utilizzare l'app Skype meetings per partecipare a riunioni ospitate in Skype for business online, gli amministratori di rete di organizzazioni che non utilizzano Microsoft 365 o Office 365 devono whitelist o in altro modo rendere disponibili le FQDN, gli indirizzi IP e le porte indicate di seguito.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisiti per la connettività delle app per le riunioni Skype

Le informazioni elencate di seguito sono un sottoinsieme degli [intervalli di indirizzi IP e URL di Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), che forniscono maggiore profondità e saranno sempre i più aggiornati.
                    
 
|App |FQDN di destinazione  |Indirizzi IP  |Porte  |
|---|---------|---------|---------|
|**App Riunioni Skype** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*Broadcast <span></span> . officeapps.Live.com <br/>\*PowerPoint <span></span> . officeapps.Live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*. s-microsoft.com<br/>        |   Questi indirizzi IP vengono aggiornati di frequente.  Vedere gli intervalli di [indirizzi IP Skype for business](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) e gli [intervalli di indirizzi IP di Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | Questi indirizzi IP vengono aggiornati di frequente.  Vedere gli intervalli di [indirizzi IP Skype for business](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) e gli [intervalli di indirizzi IP di Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Vedere anche
<a name="BKMK_Conferencing"> </a>

[Pianificare i client di riunioni (app per le riunioni e le app Web)](meetings-clients.md)

[Distribuire i client scaricabili Web in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Piattaforme supportate per l'app incontri Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
