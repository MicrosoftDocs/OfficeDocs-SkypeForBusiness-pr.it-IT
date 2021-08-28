---
title: Configurare Azure AD Connessione
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni per la configurazione di Azure AD Connessione in un ambiente ibrido.
ms.openlocfilehash: 47c158928a9536b0be40833deaddf3fb9967be73
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625788"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configurare Azure AD Connect per Teams e Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Le organizzazioni che hanno Skype for Business Server (o Lync Server) locale e che pianificano di usare Teams devono configurare Azure AD Connessione per sincronizzare la directory locale con Microsoft 365. Questo requisito include le organizzazioni che si spostano direttamente da Skype for Business locale a Teams. Le organizzazioni con Skype for Business locale devono assicurarsi che gli attributi msRTCSIP adeguati siano sincronizzati in Azure AD.

> [!NOTE]
> Gli utenti Teams esistenti che dispongono anche di Skype for Business locale dovranno spostare il proprio account Skype for Business locale nel cloud per ottenere funzionalità complete, ad esempio la possibilità di interagire con gli utenti di Skype for Business e di comunicare con gli utenti nelle organizzazioni federate. Anche se l'utente userà solo Teams, questo account di Skype for Business online è richiesto dall'infrastruttura per garantire le funzionalità aggiuntive. Per eseguire questa migrazione, è necessario verificare che Azure AD Connect sia configurato correttamente affinché sia possibile abilitare l'opzione ibrida.
 

## <a name="background-information"></a>Informazioni complementari

Azure Active Directory Connessione active directory locale viene costantemente sincronizzato con Microsoft 365. La directory locale rimane l'origine autorevole di identità e le modifiche dell'ambiente locale vengono sincronizzate in Azure AD. Per ulteriori informazioni, vedere [Azure AD Connessione Sync](/azure/active-directory/hybrid/how-to-connect-sync-whatis).  

Se non si spostano tutti gli utenti dall'ambiente locale al cloud, tutti gli utenti che usano Teams o Skype for Business locale devono essere sincronizzati da locale ad Azure AD per garantire la comunicazione tra utenti locali e utenti online. *Gli utenti dell'organizzazione saranno rappresentati nella directory locale e nella directory online.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configurazione di Azure AD se si dispone di Skype for Business Server 

Indipendentemente dal fatto che si abbia una foresta di Active Directory locale o più foreste, è possibile usare Azure AD Connessione in un'ampia gamma di topologie [supportate,](/azure/active-directory/hybrid/plan-connect-topologies)come descritto in Topologie per Azure AD Connessione . Dal punto di vista della Skype for Business Server, esistono tre varianti: 

1. Una foresta singola, che contiene le identità utente autorevoli e ospita Skype for Business Server. 

2. Più foreste, di cui solo una ospita Skype for Business Server, mentre una o più foreste aggiuntive contengono le identità utente autorevoli (le foreste di account). 

3. Più distribuzioni di Skype for Business Server in più foreste. Se vengono soddisfatti determinati requisiti, le organizzazioni possono consolidare queste distribuzioni multiple in un'Microsoft 365 singola.

### <a name="single-forest"></a>Foresta singola 

Se gli account utente e Skype for Business sono ospitati in una foresta singola, è necessario verificare che Azure AD Connect sia configurato per sincronizzare gli utenti di questa foresta in Azure AD.  Anche se l'installazione guidata di Azure AD Connect include una serie di opzioni, gli attributi appropriati verranno automaticamente sincronizzati in Azure Active Directory. I clienti sono invitati a non modificare le regole di sincronizzazione predefinite e/o i connettori che gestiscono la configurazione (cosa che non è possibile dall'installazione guidata).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Più foreste con una distribuzione di Skype for Business 

Questo scenario è spesso definito come topologia di foresta di risorse. Le identità autorevoli degli utenti sono ospitate in una o più foreste di account e Skype for Business è distribuito in una foresta di risorse separata (che potrebbe anche ospitare le identità utente autorevoli). In generale, le identità autorevoli degli utenti di Skype for Business possono trovarsi nella stessa foresta di Skype for Business Server e/o in un'altra foresta, purché: 

- Gli utenti con identità autorevoli dalle foreste di account sono rappresentati nella foresta di risorse (in cui Skype for Business Server vengono distribuiti) come oggetti utente disabilitati. L'attributo msRTCSIP-OriginatorSID nella foresta di risorse deve corrispondere al SID nella foresta di account. Per ulteriori informazioni, vedere [Configure a multi-forest environment for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- La foresta di risorse che ospita Skype for Business Server considera attendibili la foresta (o le foreste) di account.  

- Tutti gli oggetti utente e gli attributi pertinenti sia per l'identità (dalle foreste di account) che per Skype for Business (dalla foresta di risorse) vengono sincronizzati in Azure AD con i valori corretti tramite Azure AD Connessione.  

  Per ottenere la sincronizzazione corretta di oggetti e attributi in Azure AD in uno [scenario](configure-a-multi-forest-environment-for-hybrid.md)locale a più foreste, Microsoft consiglia vivamente di usare Azure AD Connessione per eseguire la sincronizzazione da tutte le foreste che hanno abilitato gli account utente e la foresta che contiene Skype for Business. Presupponendo che siano state sincronizzate tutte le foreste, è quindi necessario configurare Azure AD Connect in modo da unire tali identità e sincronizzarle in Azure AD. Azure AD Connect è progettato per gestire questo scenario e fornisce un'apposita opzione integrata nell'installazione guidata, compresa l'impostazione per configurare gli ancoraggi per l'aggiunta di identità. Scegliere quanto segue: Le identità utente esistono in più **directory** e corrispondono agli attributi **--> ObjectSID e msExchangeMasterAccountSID**.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Più distribuzioni di Skype for Business Server in più foreste 

In questo scenario, sono presenti più foreste, ognuna contenente Skype for Business Server e una singola Microsoft 365 organizzazione. Ogni foresta contenente Skype for Business Server può essere sincronizzata in Azure AD per tale organizzazione usando AAD Connessione. Nella maggior parte dei casi, solo una foresta può essere configurata per Skype for business ibrido in un determinato momento. Prima di abilitare la distribuzione ibrida in una foresta, tutti i domini SIP di tutte le altre foreste devono essere disabilitati [utilizzando disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain). Per ulteriori informazioni, vedere [Consolidamento del cloud per Teams e Skype for Business](cloud-consolidation.md).

## <a name="general-requirements"></a>Requisiti generali 

I Teams richiedono che gli attributi di Active Directory corretti esistano e siano popolati in Azure AD. Microsoft consiglia di sincronizzare tutte le foreste che contengono identità utente e tutte le foreste che contengono Skype for Business Server.

 Se le identità degli utenti si trovano in più foreste, Azure AD Connect deve eseguire l'unione. Una volta rispettate queste indicazioni, Azure AD Connect sincronizza automaticamente gli attributi corretti, purché non vengano modificati i connettori o le regole di sincronizzazione in Azure AD Connect. 
  
Se non si esegue la sincronizzazione da tutte le foreste che contengono identità utente e la distribuzione di Skype for Business Server, è necessario verificare che l'identità e gli attributi Skype for Business pertinenti vengano inseriti correttamente in Azure AD per qualsiasi utente che usa Teams o Skype for Business (in locale o online). Questa operazione richiederà probabilmente un'ulteriore sincronizzazione della directory locale. Per ulteriori informazioni, vedere [Azure AD Connessione sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

In tali scenari, è responsabilità del cliente garantire una configurazione appropriata per popolare gli attributi in Azure AD. Tenere presente quanto segue: 

- L'uso di una configurazione non standard per la sincronizzazione con Azure AD è rischioso poiché potrebbe comportare una configurazione errata, che potrebbe causare il danneggiamento dei dati nella directory online.

- Con l'evolversi dei prodotti, Microsoft continuerà a verificare le configurazioni di sincronizzazione standard in cui vengono sincronizzate tutte le foreste pertinenti. I clienti con configurazioni di sincronizzazione personalizzate devono verificare che le loro configurazioni forniscano i valori e gli attributi corretti in Azure AD. 

## <a name="related-information"></a>Informazioni correlate

- [Che cos'è l'identità ibrida](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Sincronizzazione Connessione Azure AD: comprendere e personalizzare la sincronizzazione](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologie per Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies)

- [Sincronizzazione Connessione azure AD: attributi sincronizzati con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)