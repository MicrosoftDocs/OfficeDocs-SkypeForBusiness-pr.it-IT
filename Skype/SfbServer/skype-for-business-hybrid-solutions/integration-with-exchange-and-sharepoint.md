---
title: Integrazione con Exchange e SharePoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 9d5f665d5bffede2de10c77735ea76fe55337af8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799806"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integrazione con Exchange e SharePoint

**Riepilogo:** Informazioni sull'integrazione di Skype for Business Server 2015 con Exchange e SharePoint.

È possibile configurare le distribuzioni di Skype for Business Server 2015 per l'integrazione con Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 e SharePoint Server, sia in locale che online. Le caratteristiche elencate nella tabella seguente sono supportate con tutti i client, se non diversamente specificato. Per altre informazioni sul supporto client, vedere [confronto delle caratteristiche client desktop per](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) le tabelle di confronto dei client Skype for business e Skype for business online presso [i client di Skype for business online](https://go.microsoft.com/fwlink/p/?LinkId=281902).

## <a name="integration-with-exchange-server"></a>Integrazione con Exchange Server

Le tabelle seguenti elencano le caratteristiche supportate in una distribuzione ibrida quando sono integrate con Microsoft Exchange Server.

 **Skype for Business Server in locale e Exchange in locale**


|**Funzionalità**|**Note**|
|:-----|:-----|
|Messaggistica istantanea/presenza in Outlook  <br/> |Per altre informazioni, Vedi [messaggistica istantanea e presenza](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx).  <br/> |
|Pianificare e partecipare a una riunione online tramite Outlook  <br/> |Per altre informazioni, vedere [integrare Skype for Business server 2015 con Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Messaggistica istantanea/presenza in Outlook Web App  <br/> |Per altre informazioni, vedere [configurare un ambiente ibrido in Skype for Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Pianificare e partecipare a una riunione online tramite Outlook Web App  <br/> ||
|Messaggistica istantanea/presenza nei client mobili  <br/> ||
|Partecipare a riunioni online nei client mobili  <br/> |Per altre informazioni, vedere [distribuzione della mobilità](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> ||
|Elenco contatti (tramite l'archivio contatti unificato)  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> È necessario un client desktop Lync 2013 o Skype for business.  <br/>  Per altre informazioni, vedere [Configurare Skype for Business Server 2015 per l'uso dell'archivio contatti unificato](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Foto di contatto ad alta risoluzione in client Lync 2013, client Skype for business e Lync Web App.  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> Per altre informazioni, vedere [configurare l'uso di foto ad alta risoluzione in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Per le foto nell'app Skype for business per MAC e per dispositivi mobili, è necessario configurare l'integrazione tra Skype for Business Server 2015 ed Exchange Server come descritto in [configurare le applicazioni partner in Skype for Business Server ed Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure vengono ospitati in locale. Per altre informazioni, Vedi [soluzioni ibride di Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> Per altre informazioni, vedere [elenco di controllo della distribuzione per l'archiviazione](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Cercare contenuto archiviato  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> |
|Segreteria telefonica  <br/> |Per altre informazioni, vedere la pagina [relativa alla distribuzione della messaggistica unificata locale di Exchange per specificare la segreteria telefonica di Lync Server 2013](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx).  <br/> |

 **Skype for Business Server in locale ed Exchange Online**


|**Funzionalità**|**Note**|
|:-----|:-----|
|Messaggistica istantanea/presenza in Outlook  <br/> |Per altre informazioni, vedere [configurare l'integrazione tra Skype for Business Server 2015 e Outlook Web App locale](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Pianificare e partecipare a una riunione online tramite Outlook  <br/> ||
|Messaggistica istantanea/presenza in Outlook Web App  <br/> |Per altre informazioni, vedere [configurare l'integrazione tra Skype for Business Server 2015 e Outlook Web App locale](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Pianificare e partecipare a una riunione online da Outlook Web App  <br/> |Per altre informazioni, vedere [configurare l'integrazione tra Skype for Business Server 2015 e Outlook Web App locale](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Messaggistica istantanea/presenza nei client mobili  <br/> ||
|Partecipare a una riunione online nei client mobili  <br/> ||
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> ||
|Elenco contatti (tramite archivio contatti unificato).  <br/> |Solo Lync Server 2013. È necessario un client desktop Lync 2013 o Skype for business.  <br/> Per altre informazioni, vedere [Configurare Skype for Business Server 2015 per l'uso dell'archivio contatti unificato](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Foto di contatto ad alta risoluzione in client Lync 2013, client Skype for business e Lync Web App.  <br/> |Per altre informazioni, vedere [configurare l'uso di foto ad alta risoluzione in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Per le foto nell'app Skype for business per MAC e per dispositivi mobili, è necessario configurare l'integrazione tra Skype for Business Server 2015 ed Exchange Server come descritto in [configurare l'integrazione tra Skype for Business Server e Outlook Web App in locale](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure vengono ospitati in locale. Per altre informazioni, Vedi [soluzioni ibride di Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange  <br/> |Per altre informazioni, vedere [elenco di controllo della distribuzione per l'archiviazione](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Cercare contenuto archiviato  <br/> |Per altre informazioni, vedere [configurare Exchange per SharePoint eDiscovery Center](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Segreteria telefonica  <br/> |Per altre informazioni, vedere fornitura della segreteria [telefonica di Lync Server 2013 agli utenti nella messaggistica unificata di Exchange ospitata](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype for business online e Exchange in locale**


|**Funzionalità**|**Note**|
|:-----|:-----|
|Presenza in Outlook  <br/> ||
|Rispondere tramite messaggistica istantanea, chiamata PSTN, chiamata Skype o videochiamata da un messaggio di posta elettronica di Outlook  <br/> ||
|Pianificare e partecipare a riunioni online tramite Outlook  <br/> ||
|Messaggistica istantanea/presenza nei client mobili  <br/> ||
|Partecipare a riunioni online nei client mobili  <br/> ||
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> ||
|La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Foto di contatto ad alta risoluzione in Lync 2013 o client Skype for business.  <br/> |Richiede Exchange 2016 o Exchange 2013. Questa operazione non è supportata in Lync Web App quando gli utenti vengono ospitati in Skype for business online.  <br/> |
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure vengono ospitati in locale. Per altre informazioni, Vedi [soluzioni ibride di Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Cronologia delle conversazioni lato server  <br/> ||

 **Skype for business online ed Exchange Online**


|**Funzionalità**|**Note**|
|:-----|:-----|
|Messaggistica istantanea/presenza in Outlook  <br/> ||
|Pianificare e partecipare a riunioni online tramite Outlook  <br/> ||
|Messaggistica istantanea/presenza in Outlook Web App  <br/> ||
|Pianificare e partecipare a una riunione online da Outlook Web App  <br/> ||
|Messaggistica istantanea/presenza nei client mobili  <br/> ||
|Partecipare a una riunione online nei client mobili  <br/> ||
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> ||
|La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Elenco contatti (tramite l'archivio contatti unificato)  <br/> |Client Lync Server 2013 o Skype for business obbligatorio  <br/> |
|Foto di contatto ad alta risoluzione in Lync 2013, client Skype for business e Lync Web App  <br/> ||
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure vengono ospitati in locale. Per altre informazioni, Vedi [soluzioni ibride di Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange  <br/> ||
|Cercare contenuto archiviato  <br/> ||
|Segreteria telefonica  <br/> ||

## <a name="integration-with-sharepoint"></a>Integrazione con SharePoint

La tabella seguente elenca le caratteristiche supportate in una distribuzione ibrida quando è integrata in SharePoint.

||**SharePoint locale**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 locale** <br/> | Ricerca di competenze <br/>  Presenza in SharePoint <br/> | Presenza in SharePoint <br/> |
|**Skype for business online** <br/> | Presenza in SharePoint <br/> | Presenza in SharePoint <br/> |


