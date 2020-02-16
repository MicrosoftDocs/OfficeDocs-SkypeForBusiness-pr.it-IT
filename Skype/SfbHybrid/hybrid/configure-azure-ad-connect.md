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
ms.openlocfilehash: 7ae6fb7d3df6d955437a51224637264033bfa662
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982991"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configurare Azure AD Connect per i team e Skype for business
 
Le organizzazioni che dispongono di Skype for Business Server (o Lync Server) in locale e che stanno pianificando l'utilizzo di team o Skype for business online devono configurare Azure AD Connect per sincronizzare la propria directory locale con Office 365, come descritto in questo documento.  Sono incluse le organizzazioni che si muovono direttamente da Skype for business in locale a teams. In particolare, le organizzazioni con Skype for business locale devono garantire che gli attributi msRTCSIP corretti siano sincronizzati in Azure AD. 

> [!NOTE]
> Gli utenti di team esistenti che dispongono anche di Skype for business in locale dovranno essere spostati nel cloud con il proprio account Skype for business in locale per ottenere funzionalità complete, ad esempio la possibilità di interagire con gli utenti di Skype for business e di comunicare con gli utenti in organizzazioni federative. Anche se l'utente utilizzerà solo i team, questo account Skype for business online è richiesto dall'infrastruttura per fornire le funzionalità aggiuntive.  Affinché sia possibile eseguire la migrazione, è necessario assicurarsi che Azure AD Connect sia configurato correttamente in modo da poter abilitare l'ambiente ibrido.
 

## <a name="background-information"></a>Informazioni complementari

Azure Active Directory Connect mantiene la sincronizzazione continuativa di Active Directory locale con Office 365.  La directory locale rimane l'origine autorevole dell'identità e le modifiche apportate dall'ambiente locale vengono sincronizzate in Azure AD. Per ulteriori informazioni, vedere [sincronizzazione di Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Anche se non si sta spostando tutti gli utenti da locale al cloud, tutti gli utenti che utilizzano Team, Skype for business locale o Skype for business online devono essere sincronizzati da locale ad Azure ad per garantire la comunicazione tra gli utenti locali e online. *Gli utenti dell'organizzazione saranno rappresentati sia nelle directory locali che in quelle online.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configurazione di Azure AD quando si dispone di Skype for Business Server 

Se si dispone di una foresta di Active Directory locale o di più foreste, è possibile utilizzare Azure AD Connect in una vasta gamma di topologie supportate, come descritto in [topologie di Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies).  Dal punto di vista di Skype for Business Server, esistono tre varianti principali: 

1. Una singola foresta, che contiene identità utente autorevoli e ospita Skype for Business Server. 

2. Più foreste, solo una delle quali ospita Skype for Business Server, nonché una o più altre foreste che contengono identità utente autorevoli (le foreste dell'account). 

3. Più distribuzioni di Skype for Business Server in più foreste. Se vengono soddisfatti determinati requisiti, le organizzazioni possono consolidare queste più distribuzioni in un singolo tenant di Office 365.

### <a name="single-forest"></a>Foresta singola 

Se gli account utente e Skype for business sono tutti ospitati in una singola foresta, è necessario assicurarsi che Azure AD Connect sia configurato per sincronizzare gli utenti da questa foresta in Azure AD.  Anche se nell'installazione guidata di Azure AD Connect sono disponibili diverse opzioni, gli attributi corretti verranno sincronizzati automaticamente in Azure Active Directory. Si consiglia ai clienti di modificare le regole di sincronizzazione e/o i connettori incorporati che gestiscono la configurazione (cosa non possibile dall'installazione guidata).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Più foreste con una distribuzione di Skype for business 

Questo scenario è spesso definito come topologia di foresta di risorse. Le identità autorevoli degli utenti sono ospitate in una o più foreste di account e Skype for business è distribuito in una foresta di risorse distinte (che può ospitare anche identità utente autorevoli). In generale, le identità autorevoli degli utenti di Skype for business possono trovarsi nella stessa foresta di Skype for Business Server e/o in un'altra foresta, purché: 

- Gli utenti con identità autorevoli provenienti dalla foresta di account sono rappresentati nella foresta di risorse (in cui è distribuito Skype for Business Server) come oggetti utente disabilitati e l'attributo msRTCSIP-OriginatorSID nella foresta di risorse corrisponde al SID nell' foresta account. Per ulteriori informazioni, vedere [configurare un ambiente con più foreste per la versione ibrida di Skype for business](configure-a-multi-forest-environment-for-hybrid.md).

- La foresta di risorse che ospita Skype for Business Server considera attendibili gli insiemi di strutture account.  

- Tutti gli oggetti e gli attributi degli utenti rilevanti per entrambe le identità (dalle foreste degli account) e Skype for business (dalla foresta di risorse) vengono sincronizzati in Azure AD con i valori corretti tramite Azure AD Connect.  

 Per ottenere la corretta sincronizzazione degli oggetti e degli attributi in Azure AD in uno [scenario locale](configure-a-multi-forest-environment-for-hybrid.md)a più foreste, Microsoft consiglia vivamente di utilizzare Azure ad Connect per eseguire la sincronizzazione da tutte le foreste che hanno abilitato gli account utente e la foresta che contiene Skype for business.  Presupponendo che la sincronizzazione venga configurata da tutte le foreste, è necessario configurare Azure AD Connect per unire queste identità e sincronizzarle ad Azure AD. Azure AD Connect è progettato per gestire questo scenario e fornisce un'opzione incorporata nell'installazione guidata per configurarla, inclusa la configurazione di ancoraggi per l'aggiunta delle identità.  Scegliere quanto segue: le identità degli utenti esistono tra più directory. Corrispondenza con gli attributi--> attributo objectSID e msExchangeMasterAccountSID.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Più distribuzioni di Skype for Business Server in più foreste 

In questo scenario, sono presenti più foreste, ognuna delle quali contiene Skype for Business Server, e un singolo tenant di Office 365.  Ogni foresta che contiene Skype for Business Server può essere sincronizzata in Azure AD per il tenant che utilizza AAD Connect. Al massimo, solo una foresta può essere configurata per l'ambiente ibrido di Skype for business in un determinato momento. Prima di abilitare l'ambiente ibrido in una foresta, tutti i domini SIP di tutte le altre foreste devono essere disattivati utilizzando [Disable-csonlineSipDomain](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain). Per ulteriori informazioni su come consolidare un ambiente di questo tipo in Office 365, vedere [cloud Consolidation for teams e Skype for business](cloud-consolidation.md).

## <a name="general-requirements"></a>Requisiti generali 

Sia i team che i servizi Skype for business online richiedono che gli attributi di Active Directory corretti esistano e siano popolati in Azure AD.  La raccomandazione generale di Microsoft consiste nel sincronizzare tutte le foreste che contengono identità degli utenti e tutte le foreste che contengono Skype for Business Server.

 Se le identità degli utenti esistono tra più foreste, Azure AD Connect deve eseguire l'Unione. Dopo aver seguito queste linee guida, Azure AD Connect sincronizza automaticamente gli attributi corretti, purché non vengano modificati i connettori o le regole di sincronizzazione in Azure AD Connect. 
  
Se non si esegue la sincronizzazione da tutte le foreste che contengono identità utente e la distribuzione di Skype for Business Server, è necessario verificare che gli attributi Identity e Skype for business siano stati correttamente inseriti in Azure AD per qualsiasi utente che utilizza teams o Skype per le aziende (sia in locale che online)--che probabilmente richiederà una sincronizzazione della directory locale. Per ulteriori informazioni, vedere [sincronizzazione di Azure ad Connect: attributi sincronizzati con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

In questi scenari, è responsabilità del cliente garantire la corretta configurazione per la compilazione degli attributi in Azure AD. Tenere presente quanto segue: 

- L'utilizzo di una configurazione non standard per la sincronizzazione di Azure AD è rischioso perché potrebbe provocare una configurazione errata, che potrebbe causare il danneggiamento dei dati nella directory online.

- Man mano che si evolvono i prodotti, Microsoft continuerà a verificare le configurazioni di sincronizzazione standard in cui vengono sincronizzate tutte le foreste rilevanti. I clienti con configurazioni di sincronizzazione personalizzate sono responsabili di garantire che le configurazioni consegnino gli attributi e i valori corretti in Azure AD. 

## <a name="related-information"></a>Informazioni correlate

- [Che cos'è l'identità ibrida](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Sincronizzazione di Azure AD Connect: comprendere e personalizzare la sincronizzazione](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologie per Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)

- [Sincronizzazione di Azure AD Connect: attributi sincronizzati con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
