---
title: Integrazione con Exchange e SharePoint
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: "Riepilogo: informazioni sull'Skype for Business Server 2015 con Exchange e SharePoint."
ms.openlocfilehash: b599567742cf55d43c1c20c0efcce07a88c86d6c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863193"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integrazione con Exchange e SharePoint

**Riepilogo:** Informazioni sull'Skype for Business Server 2015 con Exchange e SharePoint.

È possibile configurare le distribuzioni di Skype for Business Server 2015 per l'integrazione con Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 e SharePoint Server, sia locali che online. Le funzionalità elencate nella tabella seguente sono supportate con tutti i client, se non diversamente specificato. Per ulteriori informazioni sul supporto client, vedere [Desktop client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) and Skype for Business Online client comparison tables at Clients for Skype for Business [Online](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

## <a name="integration-with-exchange-server"></a>Integrazione con Exchange Server

Nelle tabelle seguenti sono elencate le funzionalità supportate in una distribuzione ibrida se integrate con Microsoft Exchange Server.

 **Skype for Business Server locale e locale Exchange locale**


|**Funzionalità**|2^31 (2 miliardi di termini)|
|:-----|:-----|
|Messaggistica istantanea/Presenza in Outlook  <br/> |Per ulteriori informazioni, vedere [Messaggistica istantanea e presenza](/previous-versions/office/lync-server-2013/lync-server-2013-im-and-presence).  <br/> |
|Pianificare e partecipare a una riunione online tramite Outlook  <br/> |Per ulteriori informazioni, vedere [Integrate Skype for Business Server 2015 with Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Messaggistica istantanea/Presenza in Outlook Web App  <br/> |Per ulteriori informazioni, vedere [Configure a hybrid environment in Skype for Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Pianificare e partecipare a una riunione online tramite Outlook Web App  <br/> ||
|Messaggistica istantanea/Presenza nei client mobili  <br/> ||
|Partecipare a riunioni online nei client mobili  <br/> |Per ulteriori informazioni, vedere [Deploying Mobility.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)  <br/> |
|Pubblicare lo stato in base Outlook informazioni sulla disponibilità del calendario  <br/> ||
|Elenco contatti (tramite l'archivio contatti unificato)  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> È necessario un client desktop Lync 2013 o Skype for Business desktop.  <br/>  Per ulteriori informazioni, vedere [Configure Skype for Business Server 2015 to use the unified contact store.](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)  <br/> |
|Foto di contatto ad alta risoluzione in lync 2013 client, Skype for Business client e Lync Web App.  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> Per ulteriori informazioni, vedere [Configure the use of high-resolution photos in Skype for Business Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Per le foto nell'app Skype for Business per MAC e Mobile, l'integrazione tra Skype for Business Server 2015 e Exchange Server deve essere configurata come descritto [in Configure partner applications in Skype for Business Server and Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta o entrambi sono ospitati in locale. Per ulteriori informazioni, vedere [Configure hybrid connectivity between Skype for Business Server and Teams](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md). <br/> |
|La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> Per ulteriori informazioni, vedere [Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Ricerca contenuto archiviato  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> |
|Posta vocale  <br/> |Per ulteriori informazioni, vedere [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail).  <br/> |

 **Skype for Business Server locale e Exchange Online**


|**Funzionalità**|2^31 (2 miliardi di termini)|
|:-----|:-----|
|Messaggistica istantanea/Presenza in Outlook  <br/> |Per ulteriori informazioni, vedere [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Pianificare e partecipare a una riunione online tramite Outlook  <br/> ||
|Messaggistica istantanea/Presenza in Outlook Web App  <br/> |Per ulteriori informazioni, vedere [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Pianificare e partecipare a una riunione online da Outlook Web App  <br/> |Per ulteriori informazioni, vedere [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Messaggistica istantanea/Presenza nei client mobili  <br/> ||
|Partecipare a una riunione online nei client mobili  <br/> ||
|Pubblicare lo stato in base Outlook informazioni sulla disponibilità del calendario  <br/> ||
|Elenco contatti (tramite l'archivio contatti unificato).  <br/> |Solo Lync Server 2013. È necessario un client desktop Lync 2013 o Skype for Business desktop.  <br/> Per ulteriori informazioni, vedere [Configure Skype for Business Server 2015 to use the unified contact store](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Foto di contatto ad alta risoluzione in lync 2013 client, Skype for Business client e Lync Web App.  <br/> |Per ulteriori informazioni, vedere [Configure the use of high-resolution photos in Skype for Business Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Per le foto nell'app Skype for Business per MAC e Mobile, l'integrazione tra Skype for Business Server 2015 e Exchange Server deve essere configurata come descritto in [Configure integration between on-premises Skype for Business Server and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta o entrambi sono ospitati in locale. Per ulteriori informazioni, vedere [Skype for Business soluzioni ibride.](/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|La cronologia delle conversazioni senza accesso e i registri delle chiamate vengono scritti nella cassetta postale dell'Exchange utente  <br/> ||
|Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange  <br/> |Per ulteriori informazioni, vedere [Deployment Checklist for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-checklist-for-archiving).  <br/> |
|Ricerca contenuto archiviato  <br/> |Per ulteriori informazioni, vedere [Configure Exchange for SharePoint eDiscovery Center](/exchange/configure-exchange-for-sharepoint-ediscovery-center-exchange-2013-help) <br/> |
|Posta vocale  <br/> |Per ulteriori informazioni, vedere [Providing Lync Server 2013 Users Voice Mail on Hosted Exchange UM](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um).  <br/> |


## <a name="integration-with-sharepoint"></a>Integrazione con SharePoint

Nella tabella seguente sono elencate le funzionalità supportate in una distribuzione ibrida se integrate con SharePoint.

||**SharePoint locale**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 locale** <br/> | Ricerca competenze <br/>  Presenza in SharePoint <br/> | Presenza in SharePoint <br/> |
|**Skype for Business online** <br/> | Presenza in SharePoint <br/> | Presenza in SharePoint <br/> |
