---
title: Gestire l'autenticazione da server a server (OAuth) e le applicazioni partner in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Riepilogo: gestire OAuth e le applicazioni partner in Skype for Business Server.'
ms.openlocfilehash: 1f2b963ad8a116236e3a0bdb33307e9f9d4a95f7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608203"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gestire l'autenticazione da server a server (OAuth) e le applicazioni partner in Skype for Business Server
 
**Riepilogo:** Gestire le applicazioni OAuth e partner in Skype for Business Server.
  
Skype for Business Server essere in grado di comunicare in modo sicuro e senza problemi con altre applicazioni e prodotti server. Ad esempio, è possibile configurare Skype for Business Server in modo che i dati di contatto e/o di archiviazione vengono archiviati in Microsoft Exchange Server 2013; Tuttavia, questa operazione può essere eseguita solo se Skype for Business Server e Exchange sono in grado di comunicare in modo sicuro tra loro. Allo stesso modo, è possibile pianificare una Skype for Business Server conferenza dall'Office Web Apps Server; anche in questo caso, questa operazione può essere eseguita solo se i due server (SharePoint e Skype for Business Server) si fidano l'uno dell'altro. Sebbene sia possibile utilizzare un meccanismo di autenticazione per le comunicazioni tra Skype for Business Server e Exchange, ma un meccanismo separato per le comunicazioni tra Skype for Business Server e SharePoint, un approccio migliore ed efficiente consiste nell'utilizzare un metodo standardizzato per tutte le autorizzazioni e l'autenticazione da server a server.
  
L'utilizzo di un singolo metodo standardizzato per l'autenticazione da server a server è l'approccio assunto da Skype for Business Server. Iniziato con il rilascio di Office Servers 2013, Skype for Business Server (così come altri prodotti Microsoft Server, tra cui Exchange Server e SharePoint Server) supportava il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server. Con OAuth, un protocollo di autorizzazione standard usato da diversi siti Web principali, le password e le credenziali utente non vengono trasferite da un computer all'altro. L'autorizzazione e l'autenticazione si basano, invece, sullo scambio di token di sicurezza che garantiscono l'accesso a un insieme di risorse per un periodo di tempo specifico.
  
L'autenticazione OAuth in genere coinvolge tre parti: un singolo server di autorizzazione e le due aree di autenticazione che devono comunicare tra loro. È inoltre possibile eseguire l'autenticazione da server a server senza utilizzare un server di autorizzazione, un processo che verrà descritto più avanti in questo documento. I token di sicurezza vengono emessi dal server di autorizzazione (noto anche come server token di sicurezza) per le due aree di autenticazione che devono comunicare; questi token verificano che le comunicazioni provenienti da un'area di autenticazione siano attendibili dall'altra area di autenticazione. Ad esempio, il server di autorizzazione potrebbe emettere token che verificano che gli utenti di una specifica area di autenticazione di Skype for Business Server siano in grado di accedere a un'area di autenticazione Exchange specificata e viceversa.
  
> [!NOTE]
> Un'area non è altro che un contenitore di sicurezza. Per impostazione predefinita, Skype for Business Server il dominio SIP predefinito come area di autenticazione OAuth. Ulteriori spazi dei nomi SIP vengono aggiunti all'elenco Nome soggetto alternativo nel certificato OAuth. 
  
Skype for Business Server supporta tre scenari di autenticazione da server a server. Con Skype for Business Server, è possibile:
  
- Configurare l'autenticazione da server a server tra un'installazione locale di Skype for Business Server e un'installazione locale di Exchange e/o SharePoint Server.
    
- Configurare l'autenticazione da server a server tra una coppia di componenti di Microsoft 365 o Office 365 (ad esempio, tra Microsoft Exchange Server e Skype for Business Server o tra Skype for Business Server e SharePoint).
    
- Configurare l'autenticazione da server a server in un ambiente cross-premise( ovvero l'autenticazione da server a server tra un server locale e un componente Microsoft 365 o Office 365).
    
Si noti che, a questo punto, solo Exchange 2013, SharePoint Server, Lync Server 2013, Skype for Business Server 2015 e Skype for Business 2019 supportano l'autenticazione da server a server; se non si esegue uno di questi server, non sarà possibile implementare completamente l'autenticazione OAuth.
  
È inoltre necessario notare che l'autenticazione da server a server è facoltativa: se Skype for Business Server non deve comunicare con altri server (ad esempio Exchange), l'autenticazione da server a server può essere ignorata del tutto. Se l'autenticazione da server a server è già configurata per Lync Server 2013 e altre applicazioni, non è necessario eseguire di nuovo questa operazione per Skype for Business Server. 
  
Tuttavia, l'autenticazione da server a server è necessaria se si desidera utilizzare alcune delle funzionalità di Skype for Business Server, ad esempio l'"archivio contatti unificato". Con l'archivio contatti unificato, Skype for Business Server le informazioni di contatto vengono archiviate in Exchange anziché in Skype for Business Server; in questo modo gli utenti possono disporre di un unico set di contatti facilmente accessibile da Skype for Business, Outlook o Outlook Web Access. Poiché l'archivio contatti unificato richiede Skype for Business Server condividere le informazioni con Exchange, è necessario utilizzare l'autenticazione da server a server per distribuire la funzionalità. L'autenticazione da server a server è necessaria anche se si sceglie di utilizzare l'archiviazione Exchange, in cui le trascrizioni delle sessioni di messaggistica istantanea vengono salvate come messaggi di posta elettronica Exchange anziché come singoli record di database.
  
Perché la Microsoft 365 o Office 365 di Skype for Business Server comunichi con la controparte Exchange, Skype for Business Server deve prima ottenere un token di sicurezza dal server di autorizzazione. Skype for Business Server quindi usa quel token di sicurezza per identificarsi per Exchange. Le Microsoft 365 o Office 365 di Exchange devono eseguire lo stesso processo per comunicare con Skype for Business Server.
  
Per l'autenticazione server-server in locale tra due server Microsoft, non è invece necessario usare un server di token di terze parti. I prodotti server come Skype for Business Server e Exchange dispongono di un server token incorporato che può essere utilizzato per l'autenticazione con altri server Microsoft (ad esempio SharePoint Server) che supportano l'autenticazione da server a server. Ad esempio, Skype for Business Server emettere e firmare un token di sicurezza da solo, quindi usare tale token per comunicare con Exchange. In questo caso, non è necessario un server di token di terze parti.
  
Per configurare l'autenticazione da server a server per un'implementazione locale di Skype for Business Server, è necessario eseguire due operazioni:
  
- Assegnare un certificato all'autorità emittente di token Skype for Business Server integrata.
    
- Configurare il server con cui Skype for Business Server comunicherà come "applicazione partner". Ad esempio, se Skype for Business Server deve comunicare con Exchange, sarà necessario configurare Exchange essere un'applicazione partner.
    
> [!NOTE]
> Un"applicazione partner" è qualsiasi applicazione Skype for Business Server può scambiare direttamente token di sicurezza senza dover passare attraverso un server di token di sicurezza di terze parti. 
  
Tieni presente che OAuth è una parte fondamentale del prodotto e non può essere disabilitato o rimosso.
  
## <a name="see-also"></a>Vedere anche

[Assegnare un certificato di autenticazione da server a server Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[Configurare un ambiente ibrido in Skype for Business Server](configure-a-hybrid-environment.md)
