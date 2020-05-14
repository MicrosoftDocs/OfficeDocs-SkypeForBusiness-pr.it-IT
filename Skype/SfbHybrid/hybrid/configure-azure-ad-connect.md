---
title: Configurare Azure AD Connect
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni per la configurazione di Azure AD Connect in un ambiente ibrido.
ms.openlocfilehash: 7a0c458692da1381f2ed3f52dfef8c1d360d74e2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221470"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configurare Azure AD Connect per Teams e Skype for Business
 
Le organizzazioni che dispongono di Skype for Business Server (o Lync Server) in locale e che stanno pianificando l'utilizzo di team o Skype for business online devono configurare Azure AD Connect per sincronizzare la propria directory locale con Microsoft 365 o Office 365, come descritto in questo documento.  Sono incluse le organizzazioni che si muovono direttamente da Skype for business in locale a teams. In particolare, le organizzazioni con Skype for Business in locale devono verificare che gli attributi msRTCSIP appropriati siano sincronizzati in Azure AD. 

> [!NOTE]
> Gli utenti di Teams esistenti che hanno anche Skype for Business in locale dovranno spostare l'account di Skype for Business in locale nel cloud per ottenere le funzionalità complete, come la possibilità di interagire con gli utenti di Skype for Business, e per comunicare con gli utenti nelle organizzazioni federate. Anche se l'utente userà solo Teams, questo account di Skype for Business online è richiesto dall'infrastruttura per garantire le funzionalità aggiuntive.  Per eseguire questa migrazione, è necessario verificare che Azure AD Connect sia configurato correttamente affinché sia possibile abilitare l'opzione ibrida.
 

## <a name="background-information"></a>Informazioni complementari

Azure Active Directory Connect mantiene la sincronizzazione continuativa di Active Directory locale con Microsoft 365 o Office 365.  La directory locale rimane l'origine autorevole di identità e le modifiche dell'ambiente locale vengono sincronizzate in Azure AD. Per ulteriori informazioni, vedere [sincronizzazione di Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Anche se non si sta spostando tutti gli utenti da locale al cloud, tutti gli utenti che utilizzano Team, Skype for business locale o Skype for business online devono essere sincronizzati da locale ad Azure ad per garantire la comunicazione tra gli utenti locali e online. *Gli utenti dell'organizzazione saranno rappresentati nella directory locale e nella directory online.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configurazione di Azure AD se si dispone di Skype for Business Server 

Se si dispone di una foresta di Active Directory locale o di più foreste, è possibile utilizzare Azure AD Connect in una vasta gamma di topologie supportate, come descritto in [topologie di Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies).  Per quanto riguarda Skype for Business Server, sono disponibili tre varianti principali: 

1. Una foresta singola, che contiene le identità utente autorevoli e ospita Skype for Business Server. 

2. Più foreste, di cui solo una ospita Skype for Business Server, mentre una o più foreste aggiuntive contengono le identità utente autorevoli (le foreste di account). 

3. Più distribuzioni di Skype for Business Server in più foreste. Se vengono soddisfatti determinati requisiti, le organizzazioni possono consolidare queste più distribuzioni in un'unica organizzazione Microsoft 365 o Office 365.

### <a name="single-forest"></a>Foresta singola 

Se gli account utente e Skype for Business sono ospitati in una foresta singola, è necessario verificare che Azure AD Connect sia configurato per sincronizzare gli utenti di questa foresta in Azure AD.  Anche se l'installazione guidata di Azure AD Connect include una serie di opzioni, gli attributi appropriati verranno automaticamente sincronizzati in Azure Active Directory. Si consiglia ai clienti di modificare le regole di sincronizzazione e/o i connettori incorporati che gestiscono la configurazione (cosa non possibile dall'installazione guidata).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Più foreste con una distribuzione di Skype for Business 

Questo scenario è spesso definito come topologia di foresta di risorse. Le identità autorevoli degli utenti sono ospitate in una o più foreste di account e Skype for Business è distribuito in una foresta di risorse separata (che potrebbe anche ospitare le identità utente autorevoli). In generale, le identità autorevoli degli utenti di Skype for Business possono trovarsi nella stessa foresta di Skype for Business Server e/o in un'altra foresta, purché: 

- Gli utenti con identità autorevoli della foresta (o delle foreste) di account siano rappresentati nella foresta di risorse (dove è distribuito Skype for Business Server) come oggetti utente disabilitati e l'attributo msRTCSIP-OriginatorSID nella foresta di risorse corrisponda al SID nella foresta di account. Per ulteriori informazioni, vedere [configurare un ambiente con più foreste per la versione ibrida di Skype for business](configure-a-multi-forest-environment-for-hybrid.md).

- La foresta di risorse che ospita Skype for Business Server considera attendibili la foresta (o le foreste) di account.  

- Tutti gli attributi e gli oggetti utente pertinenti per identità (di foreste di account) e Skype for Business (della foresta di risorse) sono sincronizzati in Azure AD con i valori corretti tramite Azure AD Connect.  

 Per ottenere la corretta sincronizzazione degli oggetti e degli attributi in Azure AD in uno [scenario locale](configure-a-multi-forest-environment-for-hybrid.md)a più foreste, Microsoft consiglia vivamente di utilizzare Azure ad Connect per eseguire la sincronizzazione da tutte le foreste che hanno abilitato gli account utente e la foresta che contiene Skype for business.  Presupponendo che siano state sincronizzate tutte le foreste, è quindi necessario configurare Azure AD Connect in modo da unire tali identità e sincronizzarle in Azure AD. Azure AD Connect è progettato per gestire questo scenario e fornisce un'apposita opzione integrata nell'installazione guidata, compresa l'impostazione per configurare gli ancoraggi per l'aggiunta di identità.  Scegliere quanto segue: le identità degli utenti esistono tra più directory. Corrispondenza con gli attributi--> attributo objectSID e msExchangeMasterAccountSID.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Più distribuzioni di Skype for Business Server in più foreste 

In questo scenario, sono presenti più foreste, ognuna delle quali contiene Skype for Business Server, e un'unica organizzazione Microsoft 365 o Office 365.  Ogni foresta che contiene Skype for Business Server può essere sincronizzata in Azure AD per tale organizzazione tramite AAD Connect. Nella maggior parte dei casi, solo una foresta può essere configurata per Skype for business ibrido in un determinato momento. Prima di abilitare l'ambiente ibrido in una foresta, tutti i domini SIP di tutte le altre foreste devono essere disattivati utilizzando [Disable-csonlineSipDomain](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain). Per ulteriori informazioni su come consolidare un ambiente di questo tipo in Microsoft 365 o Office 365, vedere [cloud Consolidation for teams e Skype for business](cloud-consolidation.md).

## <a name="general-requirements"></a>Requisiti generali 

Sia i team che i servizi Skype for business online richiedono che gli attributi di Active Directory corretti esistano e siano popolati in Azure AD.  La raccomandazione generale di Microsoft consiste nel sincronizzare tutte le foreste che contengono identità degli utenti e tutte le foreste che contengono Skype for Business Server.

 Se le identità degli utenti si trovano in più foreste, Azure AD Connect deve eseguire l'unione. Dopo aver seguito queste linee guida, Azure AD Connect sincronizza automaticamente gli attributi corretti, purché non vengano modificati i connettori o le regole di sincronizzazione in Azure AD Connect. 
  
Se non si esegue la sincronizzazione da tutte le foreste che contengono identità utente e la distribuzione di Skype for Business Server, è necessario verificare che gli attributi Identity e Skype for business siano stati correttamente inseriti in Azure AD per qualsiasi utente che utilizza Team o Skype for business (sia in locale che online)--che probabilmente richiederà una sincronizzazione della directory locale. Per ulteriori informazioni, vedere [sincronizzazione di Azure ad Connect: attributi sincronizzati con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

In questi scenari, è responsabilità del cliente garantire la corretta configurazione per la compilazione degli attributi in Azure AD. Tenere presente quanto segue: 

- L'uso di una configurazione non standard per la sincronizzazione con Azure AD è rischioso poiché potrebbe comportare una configurazione errata, che potrebbe causare il danneggiamento dei dati nella directory online.

- Con l'evolversi dei prodotti, Microsoft continuerà a verificare le configurazioni di sincronizzazione standard in cui vengono sincronizzate tutte le foreste pertinenti. I clienti con configurazioni di sincronizzazione personalizzate devono verificare che le loro configurazioni forniscano i valori e gli attributi corretti in Azure AD. 

## <a name="related-information"></a>Informazioni correlate

- [Che cos'è l'identità ibrida](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Sincronizzazione di Azure AD Connect: comprendere e personalizzare la sincronizzazione](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologie per Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)

- [Sincronizzazione di Azure AD Connect: attributi sincronizzati con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
