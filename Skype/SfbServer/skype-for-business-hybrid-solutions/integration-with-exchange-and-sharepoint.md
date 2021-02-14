---
title: Integrazione con Exchange e SharePoint
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
- SPO_Content
ms.custom: ''
ms.assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
description: "Riepilogo: informazioni sull'integrazione di Skype for Business Server 2015 con Exchange e SharePoint."
ms.openlocfilehash: 943392fbd63238621825edad380ac9c140935635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821106"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integrazione con Exchange e SharePoint

**Riepilogo:** Informazioni sull'integrazione di Skype for Business Server 2015 con Exchange e SharePoint.

È possibile configurare le distribuzioni di Skype for Business Server 2015 per l'integrazione con Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 e SharePoint Server, sia in locale che online. Se non diversamente specificato, le funzionalità elencate nella tabella seguente sono supportate con tutti i client. Per ulteriori informazioni sul supporto client, vedere Confronto delle funzionalità client desktop per le tabelle di confronto dei [client Skype for Business](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) e Skype for Business online in Client per Skype for Business [online.](https://go.microsoft.com/fwlink/p/?LinkId=281902)

## <a name="integration-with-exchange-server"></a>Integrazione con Exchange Server

Nelle tabelle seguenti sono elencate le funzionalità supportate in una distribuzione ibrida se integrate con Microsoft Exchange Server.

 **Skype for Business Server locale ed Exchange locale**


|**Caratteristica**|**Note**|
|:-----|:-----|
|Messaggistica istantanea/presenza in Outlook  <br/> |Per ulteriori informazioni, vedere [Messaggistica istantanea e presenza.](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx)  <br/> |
|Pianificare e partecipare a una riunione online tramite Outlook  <br/> |Per ulteriori informazioni, vedere [Integrare Skype for Business Server 2015 con Exchange Server.](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)  <br/> |
|Messaggistica istantanea/presenza in Outlook Web App  <br/> |Per ulteriori informazioni, vedere [Configurare un ambiente ibrido in Skype for Business Server 2015.](../manage/authentication/configure-a-hybrid-environment.md)  <br/> |
|Pianificare e partecipare a una riunione online tramite Outlook Web App  <br/> ||
|Messaggistica istantanea/presenza nei client mobili  <br/> ||
|Partecipare a riunioni online nei client mobili  <br/> |Per ulteriori informazioni, vedere [Deploying Mobility.](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx)  <br/> |
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> ||
|Elenco contatti (tramite l'archivio contatti unificato)  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> È necessario un client desktop Lync 2013 o Skype for Business.  <br/>  Per ulteriori informazioni, vedere [Configurare Skype for Business Server 2015 per l'utilizzo dell'archivio contatti unificato.](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md)  <br/> |
|Foto di contatto ad alta risoluzione nel client Lync 2013, nel client Skype for Business e in Lync Web App.  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> Per ulteriori informazioni, vedere Configurare l'uso di foto ad alta [risoluzione in Skype for Business Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Per le foto nell'app Skype for Business per MAC e Mobile, l'integrazione tra Skype for Business Server 2015 e Exchange Server deve essere configurata come descritto in Configurare le applicazioni [partner in Skype for Business Server e Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta o entrambi sono ospitati in locale. Per ulteriori informazioni, vedere [Soluzioni ibride di Skype for Business.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|La cronologia delle conversazioni perse e i registri chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> Per ulteriori informazioni, vedere [Deployment Checklist for Archiving.](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)  <br/> |
|Eseguire ricerche nel contenuto archiviato  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> |
|Posta vocale  <br/> |Per ulteriori informazioni, vedere [Deploying On-Premises Exchange UM to Provide Lync Server 2013 Voice Mail.](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)  <br/> |

 **Skype for Business Server locale ed Exchange Online**


|**Caratteristica**|**Note**|
|:-----|:-----|
|Messaggistica istantanea/presenza in Outlook  <br/> |Per ulteriori informazioni, vedere Configurare l'integrazione tra [Skype for Business Server 2015 locale e Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Pianificare e partecipare a una riunione online tramite Outlook  <br/> ||
|Messaggistica istantanea/presenza in Outlook Web App  <br/> |Per ulteriori informazioni, vedere Configurare l'integrazione tra [Skype for Business Server 2015 locale e Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Pianificare e partecipare a una riunione online da Outlook Web App  <br/> |Per ulteriori informazioni, vedere Configurare l'integrazione tra [Skype for Business Server 2015 locale e Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Messaggistica istantanea/presenza nei client mobili  <br/> ||
|Partecipare a una riunione online nei client mobili  <br/> ||
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> ||
|Elenco contatti (tramite l'archivio contatti unificato).  <br/> |Solo Lync Server 2013. È necessario un client desktop Lync 2013 o Skype for Business.  <br/> Per ulteriori informazioni, vedere [Configurare Skype for Business Server 2015 per l'utilizzo dell'archivio contatti unificato](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Foto di contatto ad alta risoluzione nel client Lync 2013, nel client Skype for Business e in Lync Web App.  <br/> |Per ulteriori informazioni, vedere Configurare l'uso di foto ad alta [risoluzione in Skype for Business Server 2015.](../deploy/integrate-with-exchange-server/high-resolution-photos.md)  <br/> Per le foto nell'app Skype for Business per MAC e Mobile, l'integrazione tra Skype for Business Server 2015 e Exchange Server deve essere configurata come descritto in Configurare l'integrazione tra Skype for Business Server locale e [Outlook Web App.](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta o entrambi sono ospitati in locale. Per ulteriori informazioni, vedere [Soluzioni ibride di Skype for Business.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|La cronologia delle conversazioni perse e i registri chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange  <br/> |Per ulteriori informazioni, vedere [Deployment Checklist for Archiving.](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx)  <br/> |
|Eseguire ricerche nel contenuto archiviato  <br/> |Per ulteriori informazioni, vedere configure [Exchange for SharePoint eDiscovery Center](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Posta vocale  <br/> |Per ulteriori informazioni, vedere [Providing Lync Server 2013 Users Voice Mail on Hosted Exchange UM.](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)  <br/> |

 **Skype for Business online ed Exchange in locale**


|**Caratteristica**|**Note**|
|:-----|:-----|
|Presenza in Outlook  <br/> ||
|Rispondere tramite messaggistica istantanea, chiamata PSTN, chiamata Skype o videochiamata da un messaggio di posta elettronica di Outlook  <br/> ||
|Pianificare e partecipare a riunioni online tramite Outlook  <br/> ||
|Messaggistica istantanea/presenza nei client mobili  <br/> ||
|Partecipare a riunioni online nei client mobili  <br/> ||
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> ||
|La cronologia delle conversazioni perse e i registri chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Foto di contatto ad alta risoluzione nel client Lync 2013 o Skype for Business.  <br/> |Richiede Exchange 2016 o Exchange 2013. Ciò non è supportato in Lync Web App quando gli utenti sono ospitati in Skype for Business online.  <br/> |
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta o entrambi sono ospitati in locale. Per ulteriori informazioni, vedere [Soluzioni ibride di Skype for Business.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|La cronologia delle conversazioni perse e i registri chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Cronologia conversazioni lato server  <br/> ||

 **Skype for Business online ed Exchange Online**


|**Caratteristica**|**Note**|
|:-----|:-----|
|Messaggistica istantanea/presenza in Outlook  <br/> ||
|Pianificare e partecipare a riunioni online tramite Outlook  <br/> ||
|Messaggistica istantanea/presenza in Outlook Web App  <br/> ||
|Pianificare e partecipare a una riunione online da Outlook Web App  <br/> ||
|Messaggistica istantanea/presenza nei client mobili  <br/> ||
|Partecipare a una riunione online nei client mobili  <br/> ||
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> ||
|La cronologia delle conversazioni perse e i registri chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Elenco contatti (tramite l'archivio contatti unificato)  <br/> |Lync Server 2013 o il client Skype for Business richiesto  <br/> |
|Foto di contatto ad alta risoluzione in Lync 2013, client Skype for Business e Lync Web App  <br/> ||
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta o entrambi sono ospitati in locale. Per ulteriori informazioni, vedere [Soluzioni ibride di Skype for Business.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions) <br/> |
|Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange  <br/> ||
|Eseguire ricerche nel contenuto archiviato  <br/> ||
|Messaggi vocali  <br/> ||

## <a name="integration-with-sharepoint"></a>Integrazione con SharePoint

Nella tabella seguente sono elencate le funzionalità supportate in una distribuzione ibrida se integrate con SharePoint.

||**SharePoint locale**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 locale** <br/> | Ricerca competenze <br/>  Presenza in SharePoint <br/> | Presenza in SharePoint <br/> |
|**Skype for Business online** <br/> | Presenza in SharePoint <br/> | Presenza in SharePoint <br/> |


