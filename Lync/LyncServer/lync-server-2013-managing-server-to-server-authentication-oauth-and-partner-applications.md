---
title: Gestione dell'autenticazione da server a server (OAuth) e delle applicazioni partner
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0d554bc935ea24f7098472a5c893f58dc717839
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Gestione dell'autenticazione da server a server (OAuth) e delle applicazioni partner in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-05-14_

Microsoft Lync Server 2013 deve essere in grado di comunicare con altre applicazioni e prodotti server in modo sicuro e senza problemi. Ad esempio, è possibile configurare Lync Server 2013 in modo che i dati dei contatti e/o i dati di archiviazione siano archiviati in Microsoft Exchange Server 2013; Tuttavia, è possibile eseguire questa operazione solo se Lync Server e Exchange sono in grado di comunicare in modo sicuro tra loro. Analogamente, è possibile pianificare una conferenza di Lync Server dall'interno di Microsoft SharePoint Server. Tuttavia, è possibile eseguire questa operazione solo se i due server (SharePoint e Lync Server) vengono confidati tra loro. Anche se è possibile utilizzare un meccanismo di autenticazione per la comunicazione Lync-to-Exchange e un meccanismo separato per la comunicazione Lync-to-SharePoint, un approccio migliore e più efficiente consiste nell'utilizzare un metodo standardizzato per tutti i server-to-server autenticazione e autorizzazione.

L'utilizzo di un unico metodo standardizzato per l'autenticazione da server a server è l'approccio adottato da Lync Server 2013. Per la versione 2013, Lync Server 2013 (così come altri prodotti server Microsoft, tra cui Exchange 2013 e Microsoft SharePoint Server) supportano il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server. Con OAuth, un protocollo di autorizzazione standard usato da diversi siti Web principali, le password e le credenziali utente non vengono trasferite da un computer all'altro. L'autorizzazione e l'autenticazione si basano, invece, sullo scambio di token di sicurezza che garantiscono l'accesso a un insieme di risorse per un periodo di tempo specifico.

L'autenticazione OAuth implica in genere tre parti: un singolo server di autorizzazione e i due ambiti che devono comunicare tra loro. È inoltre possibile eseguire l'autenticazione da server a server senza l'utilizzo di un server di autorizzazione, un processo che verrà descritto più avanti in questo documento. I token di sicurezza vengono emessi dal server di autorizzazione (noto anche come server token di sicurezza) ai due regni che devono comunicare. questi token verificano che le comunicazioni provenienti da un'area di autenticazione debbano essere considerate attendibili dall'altra area di autenticazione. Ad esempio, il server di autorizzazione potrebbe emettere token che verificano che gli utenti provenienti da un'area di autenticazione Lync Server 2013 specifica siano in grado di accedere a un'area di autenticazione di Exchange 2013 specificata e viceversa.

<div>


> [!NOTE]
> Un'area non è altro che un contenitore di sicurezza. Per impostazione predefinita, Lync Server 2013 utilizza il dominio SIP predefinito come area di autenticazione OAuth. Gli spazi dei nomi SIP aggiuntivi vengono aggiunti all'elenco dei nomi alternativi del soggetto nel certificato OAuth.



</div>

Lync Server 2013 supporta tre scenari di autenticazione da server a server. Con Lync Server 2013 è possibile:

  - Configurare l'autenticazione da server a server tra un'installazione locale di Lync Server 2013 e un'installazione locale di Exchange 2013 e/o Microsoft SharePoint Server.

  - Configurare l'autenticazione da server a server tra una coppia di componenti di Office 365 (ad esempio, tra Microsoft Exchange e Microsoft Lync Server o tra Microsoft Lync Server e Microsoft SharePoint).

  - Configurare l'autenticazione server-server in un ambiente cross-premise, ovvero l'autenticazione server-server tra un server locale e un componente di Office 365..

Si noti che, in questo momento, solo Exchange 2013, SharePoint Server e Lync Server 2013 supportano l'autenticazione da server a server; Se uno di questi server non è in esecuzione, non sarà possibile implementare completamente l'autenticazione OAuth.

È inoltre opportuno sottolineare che non è necessario utilizzare l'autenticazione da server a server: non è necessaria l'autenticazione da server a server per la distribuzione di Lync Server 2013. Se Lync Server 2013 non deve comunicare con altri server (ad esempio, Exchange 2013), l'autenticazione da server a server non è necessaria.

Tuttavia, l'autenticazione da server a server è necessaria se si desidera utilizzare alcune delle nuove funzionalità di Lync Server, ad esempio "archivio contatti unificato". Con l'archivio contatti unificato, Lync Server 2013 le informazioni di contatto sono archiviate in Exchange 2013 anziché in Lync Server; in questo modo gli utenti possono disporre di un unico gruppo di contatti facilmente accessibile dall'interno di Lync, Microsoft Outlook o Microsoft Outlook Web Access. Poiché l'archivio contatti unificato richiede che Lync Server 2013 condivida informazioni con Exchange 2013, è necessario utilizzare l'autenticazione da server a server per distribuire la caratteristica. L'autenticazione da server a server è necessaria anche se si sceglie di utilizzare l'archiviazione di Exchange, in cui le trascrizioni delle sessioni di messaggistica istantanea vengono salvate come messaggi di posta elettronica di Exchange 2013 anziché come singoli record di database.

Per la versione di Office 365 di Lync Server per la comunicazione con la controparte di Exchange, Lync Server 2013 deve prima ottenere un token di sicurezza dal server di autorizzazione. Lync Server utilizza quindi tale token di sicurezza per identificarsi in Exchange. La versione di Exchange di Office 365 deve passare attraverso lo stesso processo per comunicare con Lync Server 2013.

Per l'autenticazione server-server in locale tra due server Microsoft, non è invece necessario usare un server di token di terze parti. I prodotti server come Lync Server 2013 ed Exchange 2013 dispongono di un server token incorporato che può essere utilizzato per l'autenticazione con altri server Microsoft (come SharePoint Server) che supportano l'autenticazione da server a server. Ad esempio, Lync Server 2013 può rilasciare e firmare un token di sicurezza in modo autonomo, quindi può utilizzare quel token per comunicare con Exchange 2013. In questo caso, non è necessario un server di token di terze parti.

Per configurare l'autenticazione da server a server per un'implementazione locale di Lync Server 2013, è necessario eseguire due operazioni:

  - Assegnare un certificato all'autorità emittente di token incorporata di Lync Server.

  - Configurare il server in cui Lync Server 2013 comunicherà per essere un'applicazione partner. Ad esempio, se Lync Server 2013 deve comunicare con Exchange 2013, sarà necessario configurare Exchange in modo che sia un'applicazione partner.

<div>


> [!NOTE]
> Un'applicazione partner è qualsiasi applicazione che Lync Server 2013 può scambiare direttamente con token di sicurezza, senza dover passare attraverso un server di token di sicurezza di terze parti.



</div>

Si noti che OAuth è una parte principale del prodotto e non può essere disabilitato o rimosso.

<div>

## <a name="see-also"></a>Vedere anche


[Assegnazione di un certificato di autenticazione da server a server a Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[Configurazione di Microsoft Lync Server 2013 in un ambiente cross-premise](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

