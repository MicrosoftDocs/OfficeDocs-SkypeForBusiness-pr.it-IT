---
title: Requisiti minimi di rete per l’app Riunioni Skype
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Riepilogo: informazioni per le organizzazioni che non usano Microsoft 365 o Office 365 e devono accedere alle riunioni ospitate dalle organizzazioni che lo usano.'
ms.openlocfilehash: bdc3c6a3fba4968dd679a2039064c19786bd4661
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674528"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisiti minimi di rete per l’app Riunioni Skype

**Riepilogo:** Informazioni per le organizzazioni che non usano Microsoft 365 o Office 365 e devono accedere alle riunioni ospitate dalle organizzazioni che lo fanno. Questo articolo non è destinato agli utenti finali Office 365 o Microsoft 365.

Gli utenti dell'app Skype Riunioni nelle organizzazioni che non usano Microsoft 365 o Office 365 potrebbero dover partecipare a riunioni ospitate in Skype for Business Online. Per partecipare a queste riunioni, gli amministratori di rete devono consentire i seguenti FQDN, indirizzi IP e porte tramite il firewall.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisiti per la connettività dell'app Skype Meetings

Le informazioni elencate di seguito sono un sottoinsieme delle informazioni in [Office 365 URL e intervalli di indirizzi IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Questo argomento è molto più approfondito e sarà sempre aggiornato.

|App|FQDN di destinazione|Indirizzi IP|Porte|
|---|---------|---------|---------|
|**Skype Meetings App**|\*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com<span></span> <br/>\*powerpoint.officeapps.live.com<span></span> <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>|Questi indirizzi IP vengono aggiornati di frequente. Vedere [gli intervalli IP Skype for Business e Microsoft Teams](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), nonché [gli intervalli IP Office](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP: 80 & 443<br/>UDP: 3478-3481|
|**Teams**|\*<span></span>.microsoft.com <br/>\*<span></span>.skype.com|Questi indirizzi IP vengono aggiornati di frequente. Vedere [gli intervalli IP Skype for Business e Microsoft Teams](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), nonché [gli intervalli IP Office](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP: 443 <br/> UDP: 3478-3481|

## <a name="see-also"></a>Vedere anche
<a name="BKMK_Conferencing"> </a>

[Pianificare i client delle riunioni (app Web e app riunioni)](meetings-clients.md)

[Distribuire client scaricabili dal Web in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Piattaforme supportate per l'app riunioni Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
