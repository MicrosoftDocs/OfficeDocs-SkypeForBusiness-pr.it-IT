---
title: Gestire l'autenticazione da server a server (OAuth) e le applicazioni partner in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Riepilogo: gestire le applicazioni OAuth e partner in Skype for Business Server.'
ms.openlocfilehash: 37c2af8a089bcae4b974761616e1ecd67c9e500b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194961"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gestire l'autenticazione da server a server (OAuth) e le applicazioni partner in Skype for Business Server
 
**Riepilogo:** Gestire le applicazioni OAuth e partner in Skype for Business Server.
  
Skype for Business Server deve essere in grado di comunicare in modo sicuro e trasparente con altre applicazioni e prodotti server. Ad esempio, puoi configurare Skype for Business Server in modo che i dati dei contatti e/o i dati di archiviazione vengano archiviati in Microsoft Exchange Server 2013; Tuttavia, questa operazione può essere eseguita solo se Skype for Business Server e Exchange sono in grado di comunicare in modo sicuro tra loro. Analogamente, è possibile pianificare una conferenza di Skype for Business Server da Office Web Apps Server; anche in questo caso, questa operazione può essere eseguita solo se i due server (SharePoint e Skype for Business Server) si fidano a vicenda. Anche se è possibile usare un meccanismo di autenticazione per la comunicazione tra Skype for Business Server e Exchange, ma un meccanismo separato per Skype for Business Server e la comunicazione di SharePoint, un approccio migliore e più efficiente consiste nell'usare un Metodo standardizzato per tutte le autorizzazioni e l'autenticazione da server a server.
  
L'approccio adottato da Skype for Business Server è l'uso di un unico metodo standardizzato per l'autenticazione da server a server. Iniziato con Office Servers 2013 Release, Skype for Business Server (oltre ad altri prodotti di Microsoft Server, incluso Exchange Server e SharePoint Server) ha supportato il protocollo OAuth (Open Authorization) per l'autenticazione da server a server e autorizzazione. Con OAuth, un protocollo di autorizzazione standard usato da numerosi siti Web principali, le credenziali utente e le password non vengono passate da un computer a un altro. L'autenticazione e l'autorizzazione si basano invece sullo scambio di token di sicurezza. questi token concedono l'accesso a un set di risorse specifico per un determinato periodo di tempo.
  
L'autenticazione OAuth include in genere tre parti: un singolo server di autorizzazione e i due ambiti che devono comunicare tra loro. È anche possibile eseguire l'autenticazione da server a server senza usare un server di autorizzazione, un processo che verrà illustrato più avanti in questo documento. I token di sicurezza vengono emessi dal server di autorizzazioni (noto anche come server token di sicurezza) ai due ambiti che devono comunicare. questi token verificano che le comunicazioni provenienti da un reame debbano essere considerate attendibili dall'altro Realm. Ad esempio, il server di autorizzazione può emettere token che verificano che gli utenti di un reame di Skype for Business Server specifico siano in grado di accedere a un ambito Exchange specificato e viceversa.
  
> [!NOTE]
> Un Realm è semplicemente un contenitore di sicurezza. Per impostazione predefinita, Skype for Business Server usa il dominio SIP predefinito come area di autenticazione OAuth. Gli spazi dei nomi SIP aggiuntivi vengono aggiunti all'elenco nome alternativo oggetto nel certificato OAuth. 
  
Skype for Business Server supporta tre scenari di autenticazione da server a server. Con Skype for Business Server è possibile:
  
- Configurare l'autenticazione da server a server tra un'installazione locale di Skype for Business Server e un'installazione locale di Exchange e/o SharePoint Server.
    
- Configurare l'autenticazione da server a server tra una coppia di componenti di Office 365, ad esempio tra Microsoft Exchange Server e Skype for Business Server o tra Skype for Business Server e SharePoint.
    
- Configurare l'autenticazione da server a server in un ambiente interlocale, ovvero l'autenticazione da server a server tra un server locale e un componente di Office 365.
    
Tieni presente che, in questo momento, solo Exchange 2013, SharePoint Server, Lync Server 2013, Skype for Business Server 2015 e Skype for business 2019 supportano l'autenticazione da server a server; Se non si esegue uno di questi server, non sarà possibile implementare completamente l'autenticazione OAuth.
  
È inoltre necessario sottolineare che l'autenticazione da server a server è facoltativa: se Skype for Business Server non deve comunicare con altri server, ad esempio Exchange, l'autenticazione da server a server può essere ignorata completamente. Se l'autenticazione da server a server è già configurata per Lync Server 2013 e altre applicazioni, non è necessario eseguirla di nuovo per Skype for Business Server. 
  
Tuttavia, è necessaria l'autenticazione da server a server se si vogliono usare alcune delle funzionalità di Skype for Business Server, ad esempio "archivio contatti unificato". Con l'archivio contatti unificato, le informazioni di contatto di Skype for Business Server sono archiviate in Exchange anziché in Skype for Business Server; Questo consente agli utenti di avere un singolo set di contatti facilmente accessibile dall'interno di Skype for business, Outlook o Outlook Web Access. Dato che l'archivio contatti unificato richiede Skype for Business Server per condividere informazioni con Exchange, è necessario usare l'autenticazione da server a server per distribuire la funzionalità. È necessaria anche l'autenticazione da server a server se si sceglie di usare l'archiviazione di Exchange, in cui le trascrizioni delle sessioni di messaggistica istantanea vengono salvate come messaggi di posta elettronica di Exchange anziché come singoli record di database.
  
Per la versione di Office 365 di Skype for Business Server per comunicare con la controparte di Exchange, Skype for Business Server deve prima ottenere un token di sicurezza dal server di autorizzazione. Skype for Business Server usa quindi il token di sicurezza per identificarsi in Exchange. La versione di Exchange di Office 365 deve passare alla stessa procedura per comunicare con Skype for Business Server.
  
Tuttavia, per l'autenticazione da server a server locale tra due server Microsoft non è necessario usare un server di token di terze parti. I prodotti server come Skype for Business Server ed Exchange hanno un server token predefinito che può essere usato per scopi di autenticazione con altri server Microsoft, come SharePoint Server, che supportano l'autenticazione da server a server. Ad esempio, Skype for Business Server può emettere e firmare un token di sicurezza da solo, quindi usare il token per comunicare con Exchange. In un caso come questo, non è necessario un server di token di terze parti.
  
Per configurare l'autenticazione da server a server per un'implementazione locale di Skype for Business Server, è necessario eseguire due operazioni:
  
- Assegna un certificato all'emittente di token di Skype for Business Server predefinito.
    
- Configurare il server con cui Skype for Business Server comunicherà come "applicazione partner". Ad esempio, se Skype for Business Server deve comunicare con Exchange, è necessario configurare Exchange in modo che sia un'applicazione partner.
    
> [!NOTE]
> Un'applicazione partner è un'applicazione in cui Skype for Business Server può scambiare direttamente i token di sicurezza, senza dover passare a un server di token di sicurezza di terze parti. 
  
Tieni presente che OAuth è una parte centrale del prodotto e non può essere disabilitato o rimosso.
  
## <a name="see-also"></a>Vedere anche

[Assegnare un certificato di autenticazione da server a server a Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[Configurare un ambiente ibrido in Skype for Business Server](configure-a-hybrid-environment.md)
