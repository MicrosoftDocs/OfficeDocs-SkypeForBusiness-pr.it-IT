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
description: "Sintesi: informazioni sull'integrazione di Skype for Business Server 2015 con Exchange e SharePoint."
ms.openlocfilehash: 943392fbd63238621825edad380ac9c140935635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821106"
---
# <a name="integration-with-exchange-and-sharepoint"></a>Integrazione con Exchange e SharePoint

**Riepilogo:** Informazioni sull'integrazione di Skype for Business Server 2015 con Exchange e SharePoint.

È possibile configurare le distribuzioni di Skype for Business Server 2015 per l'integrazione con Microsoft Exchange Server 2016, Microsoft Exchange Server 2013, Microsoft Exchange Server 2010 e SharePoint Server, sia in locale che online. Le funzionalità elencate nella tabella seguente sono supportate con tutti i client, se non diversamente specificato. Per ulteriori informazioni sul supporto client, vedere [confronto delle funzionalità client desktop per](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) le tabelle di confronto dei client per Skype for business e Skype for business online nei client [per Skype for business online](https://go.microsoft.com/fwlink/p/?LinkId=281902).

## <a name="integration-with-exchange-server"></a>Integrazione con Exchange Server

Nelle tabelle seguenti sono elencate le funzionalità supportate in una distribuzione ibrida se sono integrate con Microsoft Exchange Server.

 **Skype for Business Server in locale ed Exchange in locale**


|**Caratteristica**|**Note**|
|:-----|:-----|
|Messaggistica istantanea/presenza in Outlook  <br/> |Per ulteriori informazioni, vedere [messaggistica istantanea e presenza](https://technet.microsoft.com/library/6a93ae95-3b64-410b-ab72-74dea232f065.aspx).  <br/> |
|Pianificare e partecipare a una riunione online tramite Outlook  <br/> |Per ulteriori informazioni, vedere [integrazione di Skype for Business server 2015 con Exchange Server](../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Messaggistica istantanea/presenza in Outlook Web App  <br/> |Per ulteriori informazioni, vedere [configurazione di un ambiente ibrido in Skype for Business Server 2015](../manage/authentication/configure-a-hybrid-environment.md).  <br/> |
|Pianificare e partecipare a una riunione online tramite Outlook Web App  <br/> ||
|Messaggistica istantanea/presenza nei client mobili  <br/> ||
|Partecipare a riunioni online nei client mobili  <br/> |Per ulteriori informazioni, vedere [Deploying Mobility](https://technet.microsoft.com/library/f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f.aspx).  <br/> |
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> ||
|Elenco contatti (tramite archivio contatti unificato)  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> È necessario un client desktop Lync 2013 o Skype for business.  <br/>  Per ulteriori informazioni, vedere [Configurare Skype for Business Server 2015 per l'utilizzo dell'archivio contatti unificato](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md).  <br/> |
|Foto dei contatti ad alta risoluzione in client Lync 2013, client Skype for business e Lync Web App.  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> Per ulteriori informazioni, vedere [configurare l'utilizzo di foto ad alta risoluzione in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Per le foto sull'app Skype for business per MAC e dispositivi mobili, è necessario che l'integrazione tra Skype for Business Server 2015 ed Exchange Server sia configurata come descritto in [configurare le applicazioni partner in Skype for Business Server e Exchange Server](../deploy/integrate-with-exchange-server/configure-partner-applications.md). <br/> |
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure entrambi sono ospitati in locale. Per ulteriori informazioni, vedere [soluzioni ibride di Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|La cronologia delle conversazioni perse e i log delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Contenuto di archiviazione (messaggistica istantanea e riunione) in Exchange  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> Per ulteriori informazioni, vedere [elenco di controllo di distribuzione per l'archiviazione](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Ricerca contenuto archiviato  <br/> |Richiede Exchange 2016 o Exchange 2013.  <br/> |
|Posta vocale  <br/> |Per ulteriori informazioni, vedere [Deploying on-premises Exchange Messaggistica unificata per fornire Lync Server 2013](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)segreteria telefonica.  <br/> |

 **Skype for Business Server in locale ed Exchange Online**


|**Caratteristica**|**Note**|
|:-----|:-----|
|Messaggistica istantanea/presenza in Outlook  <br/> |Per ulteriori informazioni, vedere [Configure Integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Pianificare e partecipare a una riunione online tramite Outlook  <br/> ||
|Messaggistica istantanea/presenza in Outlook Web App  <br/> |Per ulteriori informazioni, vedere [Configure Integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Pianificazione e partecipazione alla riunione online da Outlook Web App  <br/> |Per ulteriori informazioni, vedere [Configure Integration between on-premises Skype for Business Server 2015 and Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md) <br/> |
|Messaggistica istantanea/presenza nei client mobili  <br/> ||
|Partecipare a una riunione online nei client mobili  <br/> ||
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> ||
|Elenco contatti (tramite archivio contatti unificato).  <br/> |Solo Lync Server 2013. È necessario un client desktop Lync 2013 o Skype for business.  <br/> Per ulteriori informazioni, vedere [Configurare Skype for Business Server 2015 per l'utilizzo dell'archivio contatti unificato](../deploy/integrate-with-exchange-server/use-the-unified-contact-store.md) <br/> |
|Foto dei contatti ad alta risoluzione in client Lync 2013, client Skype for business e Lync Web App.  <br/> |Per ulteriori informazioni, vedere [configurare l'utilizzo di foto ad alta risoluzione in Skype for Business Server 2015](../deploy/integrate-with-exchange-server/high-resolution-photos.md).  <br/> Per le foto sull'app Skype for business per MAC e dispositivi mobili, è necessario che l'integrazione tra Skype for Business Server 2015 ed Exchange Server sia configurata come descritto in [Configure Integration between on-premises Skype for Business Server e Outlook Web App](../deploy/integrate-with-exchange-server/outlook-web-app.md). <br/> |
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure entrambi sono ospitati in locale. Per ulteriori informazioni, vedere [soluzioni ibride di Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|La cronologia delle conversazioni perse e i log delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Contenuto di archiviazione (messaggistica istantanea e riunione) in Exchange  <br/> |Per ulteriori informazioni, vedere [elenco di controllo di distribuzione per l'archiviazione](https://technet.microsoft.com/library/7479734d-be01-40d9-ad82-320a09d19d04.aspx).  <br/> |
|Ricerca contenuto archiviato  <br/> |Per ulteriori informazioni, vedere at [Configure Exchange for SharePoint eDiscovery Center](https://go.microsoft.com/fwlink/p/?LinkId=285448) <br/> |
|Posta vocale  <br/> |Per ulteriori informazioni, vedere [providing Lync Server 2013 Users Voice mail sulla messaggistica unificata di Exchange ospitata](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx).  <br/> |

 **Skype for business online e Exchange in locale**


|**Caratteristica**|**Note**|
|:-----|:-----|
|Presenza in Outlook  <br/> ||
|Rispondere tramite messaggistica istantanea, chiamata PSTN, chiamata Skype o chiamata video da un messaggio di posta elettronica di Outlook  <br/> ||
|Pianificare e partecipare a riunioni online tramite Outlook  <br/> ||
|Messaggistica istantanea/presenza nei client mobili  <br/> ||
|Partecipare a riunioni online nei client mobili  <br/> ||
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> ||
|La cronologia delle conversazioni perse e i log delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Foto dei contatti ad alta risoluzione in Lync 2013 o client Skype for business.  <br/> |Richiede Exchange 2016 o Exchange 2013. Questo non è supportato in Lync Web App quando gli utenti sono ospitati in Skype for business online.  <br/> |
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure entrambi sono ospitati in locale. Per ulteriori informazioni, vedere [soluzioni ibride di Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|La cronologia delle conversazioni perse e i log delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Cronologia delle conversazioni sul fianco del server  <br/> ||

 **Skype for business online ed Exchange Online**


|**Caratteristica**|**Note**|
|:-----|:-----|
|Messaggistica istantanea/presenza in Outlook  <br/> ||
|Pianificare e partecipare a riunioni online tramite Outlook  <br/> ||
|Messaggistica istantanea/presenza in Outlook Web App  <br/> ||
|Pianificazione e partecipazione alla riunione online da Outlook Web App  <br/> ||
|Messaggistica istantanea/presenza nei client mobili  <br/> ||
|Partecipare a una riunione online nei client mobili  <br/> ||
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> ||
|La cronologia delle conversazioni perse e i log delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> ||
|Elenco contatti (tramite archivio contatti unificato)  <br/> |Lync Server 2013 o client Skype for business necessario  <br/> |
|Foto dei contatti ad alta risoluzione in Lync 2013, client Skype for business e Lync Web App  <br/> ||
|Delega riunione  <br/> |Supportato solo quando entrambi gli utenti sono ospitati online nella stessa foresta oppure entrambi sono ospitati in locale. Per ulteriori informazioni, vedere [soluzioni ibride di Skype for business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/skype-for-business-hybrid-solutions). <br/> |
|Contenuto di archiviazione (messaggistica istantanea e riunione) in Exchange  <br/> ||
|Ricerca contenuto archiviato  <br/> ||
|Messaggi vocali  <br/> ||

## <a name="integration-with-sharepoint"></a>Integrazione con SharePoint

Nella tabella seguente sono elencate le funzionalità supportate in una distribuzione ibrida quando sono integrate con SharePoint.

||**SharePoint locale**|**SharePoint Online**|
|:-----|:-----|:-----|
|**Skype for Business Server 2015 in locale** <br/> | Ricerca di competenze <br/>  Presenza in SharePoint <br/> | Presenza in SharePoint <br/> |
|**Skype for Business online** <br/> | Presenza in SharePoint <br/> | Presenza in SharePoint <br/> |


