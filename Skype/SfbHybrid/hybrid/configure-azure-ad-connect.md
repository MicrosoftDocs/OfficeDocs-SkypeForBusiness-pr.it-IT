---
title: Configurare Azure AD Connect
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
ms.openlocfilehash: 9df0e42224d3186c3d7b5b1748412e9ec9121897
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185483"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configurare Azure AD Connect per Teams e Skype for business
 
Le organizzazioni che hanno in locale Skype for Business Server (o Lync Server) e che hanno intenzione di usare teams o Skype for business online devono configurare Azure AD Connect per sincronizzare la propria directory locale con Office 365, come descritto in questo documento.  Sono incluse le organizzazioni che si muovono direttamente da Skype for business locale a teams. In particolare, le organizzazioni con Skype for business locale devono garantire la sincronizzazione degli attributi msRTCSIP corretti in Azure AD. 

> [!NOTE]
> Gli utenti di team esistenti che hanno anche Skype for business locale dovranno avere il proprio account di Skype for business locale spostato nel cloud per ottenere la piena funzionalità, ad esempio la possibilità di interagire con gli utenti di Skype for business e di comunicare con gli utenti nelle organizzazioni federate. Anche se l'utente userà solo teams, questo account Skype for business online è richiesto dall'infrastruttura per fornire le funzionalità aggiuntive.  Affinché la migrazione avvenga, devi assicurarti che Azure AD Connect sia configurato correttamente in modo che tu possa abilitare Hybrid.
 

## <a name="background-information"></a>Informazioni di base

Azure Active Directory Connect mantiene la sincronizzazione di Active Directory locale continuamente con Office 365.  La directory locale rimane l'origine autorevole dell'identità e le modifiche apportate dall'ambiente locale vengono sincronizzate in Azure AD. Per altre informazioni, Vedi [Azure ad Connect Sync](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Anche se non si spostano tutti gli utenti dal locale al cloud, tutti gli utenti che usano team, Skype for business locale o Skype for business online devono essere sincronizzati da locale ad Azure ad per garantire la comunicazione tra utenti locali e online . *Gli utenti dell'organizzazione verranno rappresentati sia nelle directory locali che online.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configurazione di Azure AD quando si ha Skype for Business Server 

Indipendentemente dal fatto che si disponga di una foresta di Active Directory locale o di più foreste, è possibile usare Azure AD Connect in diverse topologie supportate, come descritto in [topologie di Azure ad Connect](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies).  Dal punto di vista di Skype for Business Server esistono tre varianti principali: 

1. Una singola foresta, che contiene le identità degli utenti autorevoli e ospita Skype for Business Server. 

2. Più foreste, solo una delle quali ospita Skype for Business Server, oltre a uno o più altri insiemi di foreste che contengono identità utente autorevoli (le foreste dell'account). 

3. Più distribuzioni di Skype for Business Server in più foreste. Purché vengano soddisfatti determinati requisiti, le organizzazioni possono consolidare queste più distribuzioni in un unico tenant di Office 365.

### <a name="single-forest"></a>Singola foresta 

Se gli account utente e Skype for business sono tutti ospitati in una singola foresta, devi assicurarti che Azure AD Connect sia configurato per sincronizzare gli utenti di questa foresta in Azure AD.  Anche se l'installazione guidata di Azure AD Connect include una varietà di opzioni, gli attributi appropriati verranno sincronizzati automaticamente in Azure Active Directory. I clienti si sconsigliano di modificare le regole di sincronizzazione predefinite e/o i connettori che gestiscono la configurazione (che non è possibile dall'installazione guidata).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Più foreste con una distribuzione Skype for business 

Questo scenario è spesso indicato come topologia di foresta di risorse. Le identità autorevoli degli utenti sono ospitate in una o più foreste di account e Skype for business viene distribuito in una foresta di risorse separata, che può anche ospitare identità utente autorevoli. In generale, le identità autorevoli degli utenti di Skype for business possono essere nella stessa foresta di Skype for Business Server e/o in un'altra foresta, purché: 

- Gli utenti con identità autorevoli delle foreste dell'account sono rappresentati nella foresta delle risorse (dove è distribuito Skype for Business Server) come oggetti utente disabilitati e l'attributo msRTCSIP-OriginatorSID nella foresta di risorse corrisponde al SID nella foresta dell'account. Per altre informazioni, vedere [configurare un ambiente con più foreste per Skype for business ibrido](configure-a-multi-forest-environment-for-hybrid.md).

- La foresta delle risorse che ospita Skype for Business Server considera attendibili gli insiemi di strutture dell'account.  

- Tutti gli oggetti e gli attributi utente rilevanti per entrambe le identità (dalle foreste degli account) e Skype for business (da Resource Forest) vengono sincronizzati in Azure AD con i valori corretti tramite Azure AD Connect.  

 Per ottenere la sincronizzazione corretta degli oggetti e degli attributi in Azure AD in uno [scenario locale](configure-a-multi-forest-environment-for-hybrid.md)con più foreste, Microsoft consiglia vivamente di usare Azure ad Connect per la sincronizzazione da tutte le foreste che hanno abilitato gli account utente e la foresta che contiene Skype for business.  Supponendo che la sincronizzazione venga da tutte le foreste, è necessario configurare Azure AD Connect per unire queste identità e sincronizzarle con Azure AD. Azure AD Connect è progettato per gestire questo scenario e fornisce un'opzione predefinita nell'installazione guidata per configurarla, inclusa la configurazione di ancoraggi per l'aggiunta di identità.  Scegliere la seguente: le identità degli utenti sono presenti in più directory. Match using--> gli attributi ObjectSID e msExchangeMasterAccountSID.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Più distribuzioni di Skype for Business Server in più foreste 

In questo scenario esistono più foreste, ognuna contenente Skype for Business Server e un unico tenant di Office 365.  Ogni foresta che contiene Skype for Business Server può essere sincronizzata in Azure AD per il tenant che usa AAD Connect. Al massimo, una sola foresta può essere configurata per Skype for business Hybrid in un momento specifico. Prima di abilitare l'ibrido in una foresta, tutti i domini SIP di tutte le altre foreste devono essere disabilitati usando [Disable-csonlineSipDomain](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain). Per altre informazioni su come consolidare un ambiente di questo tipo in Office 365, vedere consolidamento [del cloud per Teams e Skype for business](cloud-consolidation.md).

## <a name="general-requirements"></a>Requisiti generali 

I servizi teams e Skype for business online richiedono che gli attributi Active Directory corretti siano presenti e popolati in Azure AD.  La raccomandazione generale di Microsoft consiste nel sincronizzare tutte le foreste che contengono le identità degli utenti e tutte le foreste che contengono Skype for Business Server.

 Se le identità degli utenti sono presenti in più foreste, Azure AD Connect deve eseguire la merge. Una volta seguite queste linee guida, Azure AD Connect sincronizza automaticamente gli attributi corretti, purché non modifichiate i connettori o le regole di sincronizzazione in Azure AD Connect. 
  
Se non si esegue la sincronizzazione da tutte le foreste che contengono le identità degli utenti e la distribuzione di Skype for Business Server, è comunque necessario garantire che l'identità pertinente e gli attributi di Skype for business vengano inseriti correttamente in Azure AD per qualsiasi utente che usa team o Skype per le aziende (sia in locale che online)--che probabilmente richiederà una sincronizzazione della directory locale aggiuntiva. Per altre informazioni, vedere [Azure ad Connect Sync: attributi sincronizzati con Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

In questi scenari, è responsabilità del cliente garantire la corretta configurazione per la compilazione degli attributi in Azure AD. Tieni presente quanto segue: 

- L'uso di una configurazione non standard per la sincronizzazione in Azure AD è rischioso perché potrebbe causare la configurazione errata, causando il danneggiamento dei dati nella directory online.

- Man mano che i prodotti evolvono, Microsoft continuerà a verificare le configurazioni di sincronizzazione standard in cui tutte le foreste rilevanti vengono sincronizzate. I clienti con configurazioni di sincronizzazione personalizzate sono responsabili di garantire che le loro configurazioni forniscano gli attributi e i valori corretti in Azure AD. 

## <a name="related-information"></a>Informazioni correlate

- [Cos'è l'identità ibrida](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Azure AD Connect Sync: comprendere e personalizzare la sincronizzazione](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologie di Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect Sync: attributi sincronizzati con Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
