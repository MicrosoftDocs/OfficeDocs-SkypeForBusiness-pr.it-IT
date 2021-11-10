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
search.appverid: MET150
description: Istruzioni per la configurazione Azure AD Connessione in un ambiente ibrido.
ms.openlocfilehash: cfb290ecc6892001a9e20d9260c54c076a51dfe3
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887214"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configurare Azure AD Connect per Teams e Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Per utilizzare Teams, le organizzazioni con una distribuzione locale di Skype for Business Server o Lync Server 2013 devono configurare Azure AD Connessione per sincronizzare la directory locale con Microsoft 365. Le organizzazioni con Skype for Business Server locale devono assicurarsi che gli attributi msRTCSIP adeguati siano sincronizzati Azure AD. In questo articolo, qualsiasi riferimento a "Skype for Business Server" si applica anche a Lync Server 2013.

> [!NOTE]
> - Per ottenere tutte le funzionalità, gli utenti Teams esistenti che hanno anche Skype for Business locale dovranno spostare il proprio account Skype for Business locale nel cloud. Ad esempio, per ottenere funzionalità quali la possibilità di interagire con Skype for Business utenti e di comunicare con gli utenti di organizzazioni federate. Se l'utente locale usa solo Teams, è comunque necessario spostare l'utente nel cloud per fornire la funzionalità Teams completa come utente TeamsOnly. Per eseguire questa migrazione, è necessario configurare Azure AD Connessione in modo da poter abilitare l'ambiente ibrido.
> - Se non si prevede di spostare gli utenti dall'ambiente locale al cloud presto, è comunque necessario configurare Azure AD Connessione in modo che gli account Teams e Skype for Business Server coesistere.
 

## <a name="background-information"></a>Informazioni complementari

Azure Active Directory Connessione active directory locale viene costantemente sincronizzato con Microsoft 365. La directory locale rimane l'origine autorevole dell'identità, mentre le modifiche dall'ambiente locale vengono sincronizzate in Azure AD. Per ulteriori informazioni, vedere [Azure AD Connessione Sync](/azure/active-directory/hybrid/how-to-connect-sync-whatis).  *Gli utenti dell'organizzazione saranno rappresentati sia* nelle directory locali che online.  Tutti gli utenti che Teams o Skype for Business locale devono essere sincronizzati da locale a Azure AD per garantire la coesistenza di questi account. Inoltre, è possibile facilitare la comunicazione tra utenti locali e online tramite la connettività ibrida Skype for Business, che richiede anche la configurazione di Azure AD Connessione.


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configurazione di Azure AD se si dispone di Skype for Business Server 

### <a name="general-requirements"></a>Requisiti generali 

Per la coesistenza di una distribuzione locale di Skype for Business Server con Teams, alcuni attributi di Active Directory dalla distribuzione locale devono essere sincronizzati in Azure AD utilizzando Azure AD Connessione. Il programma di Azure AD Connessione configura automaticamente gli attributi necessari per la sincronizzazione per impostazione predefinita quando rileva la presenza di Skype for Business Server nell'ambiente locale. Questi attributi includono attributi di identità generali, ad esempio il nome dell'entità utente, nonché attributi preceduti da "msRTCSIP", specifici di Skype For Business Server. Il set completo di attributi è elencato in [Azure AD Connessione sincronizzazione: Attributi sincronizzati con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#teams-and-skype-for-business-online).

Se si sceglie di personalizzare le impostazioni di sincronizzazione in Azure AD Connessione, è necessario verificare che gli attributi seguenti siano sincronizzati per gli oggetti utente:
</br>

|Attributo|Descrizione|
|---|---|
|msRTCSIP-PrimaryUserAddress| Indirizzo SIP dell'utente nell'ambiente locale|
|msRTCSIP-DeploymentLocator| Indica se l'utente si trova in locale o nel cloud|
|msRTCSIP-UserEnabled| Indica se l'utente è abilitato per la funzionalità SIP|
|||

</br>
</br>
Inoltre, se si gestiscono gli attributi del sistema telefonico tramite la distribuzione locale, è necessario sincronizzare anche gli attributi seguenti:

|Attributo|Descrizione|
|:---|:---|
|msRTCSIP-Line| Numero di telefono dell'utente|
|msRTCSIP-OptionFlags| Indica se l'utente è abilitato per la funzionalità vocale|
|msRTCSIP-OwnerUrn| Usato per identificare gli endpoint dell'applicazione ibrida|
|||

</br>
Microsoft consiglia di sincronizzare tutte le foreste che contengono identità utente e tutte le foreste che contengono Skype for Business Server. Se le identità degli utenti si trovano in più foreste, Azure AD Connect deve eseguire l'unione. Una volta rispettate queste indicazioni, Azure AD Connect sincronizza automaticamente gli attributi corretti, purché non vengano modificati i connettori o le regole di sincronizzazione in Azure AD Connect. 
  
Se non si esegue la sincronizzazione da tutte le foreste che contengono identità utente e la distribuzione di Skype for Business Server, è necessario verificare che l'identità e gli attributi Skype for Business pertinenti siano inseriti correttamente in Azure AD per qualsiasi utente che utilizza Teams o Skype for Business (in locale o online). Questa operazione richiederà probabilmente un'ulteriore sincronizzazione della directory locale. Per ulteriori informazioni, vedere [Azure AD Connessione sincronizzazione: attributi sincronizzati con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

È responsabilità del cliente garantire una configurazione appropriata per popolare gli attributi in Azure AD. Tenere presente quanto segue: 

- L'utilizzo di una configurazione non standard per la sincronizzazione con Azure AD è rischioso. Le configurazioni non standard potrebbero causare il danneggiamento dei dati nella directory online.

- Con l'evolversi dei prodotti, Microsoft continuerà a verificare le configurazioni di sincronizzazione standard in cui vengono sincronizzate tutte le foreste pertinenti. I clienti con configurazioni di sincronizzazione personalizzate devono verificare che le loro configurazioni forniscano i valori e gli attributi corretti in Azure AD. 

Sia che si abbia una foresta di Active Directory locale o più foreste, è possibile utilizzare Azure AD Connessione in un'ampia gamma di topologie supportate, come descritto in [Topologie per Azure AD Connessione](/azure/active-directory/hybrid/plan-connect-topologies). Dal punto di vista della Skype for Business Server, esistono tre varianti: 

1. Una foresta singola, che contiene le identità utente autorevoli e ospita Skype for Business Server. 

2. Più foreste, di cui solo una ospita Skype for Business Server, mentre una o più foreste aggiuntive contengono le identità utente autorevoli (le foreste di account). 

3. Più distribuzioni di Skype for Business Server in più foreste. Se vengono soddisfatti determinati requisiti, le organizzazioni possono consolidare queste distribuzioni multiple in un'Microsoft 365 singola.

### <a name="single-forest"></a>Foresta singola 

Se gli account utente e Skype for Business sono ospitati in una foresta singola, è necessario verificare che Azure AD Connect sia configurato per sincronizzare gli utenti di questa foresta in Azure AD.  Per impostazione predefinita, gli attributi appropriati verranno sincronizzati automaticamente Azure Active Directory. I clienti sono invitati a non modificare le regole di sincronizzazione predefinite e/o i connettori che gestiscono la configurazione (cosa che non è possibile dall'installazione guidata).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Più foreste con una distribuzione di Skype for Business 

Questo scenario è spesso definito come topologia di foresta di risorse. Le identità autorevoli degli utenti sono ospitate in una o più foreste di account e Skype for Business è distribuito in una foresta di risorse separata (che potrebbe anche ospitare le identità utente autorevoli). In generale, le identità autorevoli degli utenti di Skype for Business possono trovarsi nella stessa foresta di Skype for Business Server e/o in un'altra foresta, purché: 

- Gli utenti con identità autorevoli dalle foreste di account sono rappresentati nella foresta di risorse (in cui è distribuito Skype for Business Server) come oggetti utente disabilitati. L'attributo msRTCSIP-OriginatorSID nella foresta di risorse deve corrispondere al SID nella foresta di account. Per ulteriori informazioni, [vedere Configure a multi-forest environment for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- La foresta di risorse che ospita Skype for Business Server considera attendibili la foresta (o le foreste) di account.  

- Tutti gli oggetti utente e gli attributi pertinenti sia per l'identità (dalle foreste di account) che per Skype for Business (dalla foresta di risorse) vengono sincronizzati in Azure AD con i valori corretti tramite Azure AD Connessione.  

  Per ottenere la sincronizzazione corretta di oggetti e attributi in Azure AD in uno [scenario](configure-a-multi-forest-environment-for-hybrid.md)locale a più foreste, è consigliabile utilizzare Azure AD Connessione per sincronizzare tutte le foreste con account utente abilitati e la foresta che contiene Skype for Business. Presupponendo che siano state sincronizzate tutte le foreste, è quindi necessario configurare Azure AD Connect in modo da unire tali identità e sincronizzarle in Azure AD. Azure AD Connect è progettato per gestire questo scenario e fornisce un'apposita opzione integrata nell'installazione guidata, compresa l'impostazione per configurare gli ancoraggi per l'aggiunta di identità. Scegliere le opzioni seguenti: Le identità utente esistono in più **directory** e corrispondono agli attributi **--> ObjectSID e msExchangeMasterAccountSID**.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Più distribuzioni di Skype for Business Server in più foreste 

In questo scenario, sono presenti più foreste, ognuna contenente Skype for Business Server e una singola Microsoft 365 organizzazione. Ogni foresta contenente Skype for Business Server può essere sincronizzata in Azure AD per tale organizzazione utilizzando Azure AD Connessione. Nella maggior parte dei casi, solo una foresta può essere configurata per Skype for business ibrido in un determinato momento. Prima di abilitare la distribuzione ibrida in una foresta, tutti i domini SIP di tutte le altre foreste devono essere disabilitati [utilizzando disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain). Per ulteriori informazioni, vedere [Consolidamento cloud per Teams e Skype for Business](cloud-consolidation.md).


## <a name="related-information"></a>Informazioni correlate

- [Che cos'è l'identità ibrida](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD Connessione: comprendere e personalizzare la sincronizzazione](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologie per Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connessione sincronizzazione: attributi sincronizzati con Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
