---
title: Gestire l'autenticazione da server a server (OAuth) e le applicazioni partner in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Riepilogo: gestire OAuth e le applicazioni partner in Skype for Business Server.'
ms.openlocfilehash: f784dd0a2dab05fb3b97497fab7d3866dda1a753
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221670"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gestire l'autenticazione da server a server (OAuth) e le applicazioni partner in Skype for Business Server
 
**Riepilogo:** Gestire OAuth e le applicazioni partner in Skype for Business Server.
  
Skype for Business Server deve essere in grado di comunicare con altre applicazioni e prodotti server in modo sicuro e senza problemi. Ad esempio, è possibile configurare Skype for Business Server in modo che i dati dei contatti e/o i dati di archiviazione siano archiviati in Microsoft Exchange Server 2013; Tuttavia, questa operazione può essere svolta solo se Skype for Business Server ed Exchange sono in grado di comunicare in modo sicuro tra loro. Analogamente, è possibile pianificare una conferenza di Skype for Business Server dall'interno del server Office Web Apps. è possibile eseguire questa operazione solo se i due server (SharePoint e Skype for Business Server) sono attendibili gli uni degli altri. Anche se è possibile utilizzare un meccanismo di autenticazione per la comunicazione tra Skype for Business Server e Exchange, ma un meccanismo separato per le comunicazioni di Skype for Business Server e SharePoint, è consigliabile utilizzare un metodo standardizzato per tutte le autorizzazioni e l'autenticazione da server a server.
  
L'utilizzo di un unico metodo standardizzato per l'autenticazione da server a server è l'approccio adottato da Skype for Business Server. Iniziato con Office Servers 2013 Release, Skype for Business Server (così come altri prodotti server Microsoft, tra cui Exchange Server e SharePoint Server), hanno supportato il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server. Con OAuth, un protocollo di autorizzazione standard usato da diversi siti Web principali, le password e le credenziali utente non vengono trasferite da un computer all'altro. L'autorizzazione e l'autenticazione si basano, invece, sullo scambio di token di sicurezza che garantiscono l'accesso a un insieme di risorse per un periodo di tempo specifico.
  
L'autenticazione OAuth implica in genere tre parti: un singolo server di autorizzazione e i due ambiti che devono comunicare tra loro. È inoltre possibile eseguire l'autenticazione da server a server senza l'utilizzo di un server di autorizzazione, un processo che verrà descritto più avanti in questo documento. I token di sicurezza vengono emessi dal server di autorizzazione (noto anche come server token di sicurezza) ai due regni che devono comunicare. questi token verificano che le comunicazioni provenienti da un'area di autenticazione debbano essere considerate attendibili dall'altra area di autenticazione. Ad esempio, il server di autorizzazione potrebbe emettere token che verificano che gli utenti provenienti da un'area di autenticazione di Skype for Business Server specifica siano in grado di accedere a un'area di autenticazione di Exchange specificata e viceversa.
  
> [!NOTE]
> Un'area non è altro che un contenitore di sicurezza. Per impostazione predefinita, Skype for Business Server utilizza il dominio SIP predefinito come area di autenticazione OAuth. Gli spazi dei nomi SIP aggiuntivi vengono aggiunti all'elenco dei nomi alternativi del soggetto nel certificato OAuth. 
  
Skype for Business Server supporta tre scenari di autenticazione da server a server. Con Skype for Business Server, è possibile:
  
- Configurare l'autenticazione da server a server tra un'installazione locale di Skype for Business Server e un'installazione locale di Exchange e/o SharePoint Server.
    
- Configurare l'autenticazione da server a server tra una coppia di componenti di Microsoft 365 o Office 365 (ad esempio, tra Microsoft Exchange Server e Skype for Business Server o tra Skype for Business Server e SharePoint).
    
- Configurare l'autenticazione da server a server in un ambiente cross-premise, ovvero l'autenticazione da server a server tra un server locale e un componente Microsoft 365 o Office 365.
    
Si noti che, in questo momento, solo Exchange 2013, SharePoint Server, Lync Server 2013, Skype for Business Server 2015 e Skype for business 2019 supportano l'autenticazione da server a server; Se uno di questi server non è in esecuzione, non sarà possibile implementare completamente l'autenticazione OAuth.
  
È inoltre opportuno rilevare che l'autenticazione da server a server è facoltativa: se Skype for Business Server non deve comunicare con altri server (ad esempio Exchange), l'autenticazione da server a server può essere ignorata del tutto. Se l'autenticazione da server a server è già configurata per Lync Server 2013 e altre applicazioni, non è necessario eseguirla di nuovo per Skype for Business Server. 
  
Tuttavia, l'autenticazione da server a server è necessaria se si desidera utilizzare alcune delle funzionalità di Skype for Business Server, ad esempio "archivio contatti unificato". Con l'archivio contatti unificato, le informazioni di contatto di Skype for Business Server sono archiviate in Exchange invece che in Skype for Business Server; in questo modo gli utenti possono disporre di un unico gruppo di contatti facilmente accessibile dall'interno di Skype for business, Outlook o Outlook Web Access. Poiché l'archivio contatti unificato richiede che Skype for Business Server condivida le informazioni con Exchange, è necessario utilizzare l'autenticazione da server a server per distribuire la funzionalità. L'autenticazione da server a server è necessaria anche se si sceglie di utilizzare l'archiviazione di Exchange, in cui le trascrizioni delle sessioni di messaggistica istantanea vengono salvate come messaggi di posta elettronica di Exchange anziché come singoli record di database.
  
Affinché Microsoft 365 o Office 365 versione di Skype for Business Server comunichi con la propria controparte di Exchange, Skype for Business Server deve prima ottenere un token di sicurezza dal server di autorizzazione. In Skype for Business Server viene quindi utilizzato il token di sicurezza per identificarsi in Exchange. Le versioni di Exchange di Microsoft 365 o Office 365 devono passare attraverso lo stesso processo per comunicare con Skype for Business Server.
  
Per l'autenticazione server-server in locale tra due server Microsoft, non è invece necessario usare un server di token di terze parti. I prodotti server come Skype for Business Server ed Exchange dispongono di un server token incorporato che può essere utilizzato per l'autenticazione con altri server Microsoft, ad esempio SharePoint Server, che supportano l'autenticazione da server a server. Ad esempio, Skype for Business Server può emettere e firmare un token di sicurezza da solo, quindi utilizzarlo per comunicare con Exchange. In questo caso, non è necessario un server di token di terze parti.
  
Per configurare l'autenticazione da server a server per un'implementazione locale di Skype for Business Server, è necessario eseguire due operazioni:
  
- Assegnare un certificato all'autorità emittente di token del server Skype for business incorporato.
    
- Configurare il server che Skype for Business Server comunicherà con l'utilizzo come "applicazione partner". Ad esempio, se Skype for Business Server deve comunicare con Exchange, sarà necessario configurare Exchange in modo che sia un'applicazione partner.
    
> [!NOTE]
> Un'applicazione partner è qualsiasi applicazione che Skype for Business Server può scambiare direttamente con i token di sicurezza, senza dover passare attraverso un server di token di sicurezza di terze parti. 
  
Si noti che OAuth è una parte principale del prodotto e non può essere disabilitato o rimosso.
  
## <a name="see-also"></a>Vedere anche

[Assegnazione di un certificato di autenticazione da server a server a Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[Configurazione di un ambiente ibrido in Skype for Business Server](configure-a-hybrid-environment.md)
