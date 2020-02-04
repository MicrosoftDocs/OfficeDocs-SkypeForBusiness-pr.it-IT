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
ms.openlocfilehash: 01de2856b8923fff76cf33dda7d7e6ba21889c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-05-14_

Microsoft Lync Server 2013 deve essere in grado di comunicare in modo sicuro e trasparente con altre applicazioni e prodotti server. Ad esempio, è possibile configurare Lync Server 2013 in modo che i dati dei contatti e/o i dati di archiviazione vengano archiviati in Microsoft Exchange Server 2013. Tuttavia, questa operazione può essere eseguita solo se Lync Server e Exchange sono in grado di comunicare in modo sicuro tra loro. Analogamente, è possibile pianificare una conferenza di Lync Server da Microsoft SharePoint Server; di nuovo, tuttavia, questa operazione può essere eseguita solo se i due server (SharePoint e Lync Server) si fidano a vicenda. Anche se è possibile usare un meccanismo di autenticazione per la comunicazione Lync-to-Exchange e un meccanismo separato per la comunicazione da Lync a SharePoint, un approccio migliore e più efficiente consiste nell'usare un metodo standardizzato per tutti i server a server autenticazione e autorizzazione.

L'approccio adottato da Lync Server 2013 è l'uso di un singolo metodo standardizzato per l'autenticazione da server a server. Per la versione di 2013, Lync Server 2013, oltre ad altri prodotti Microsoft Server, inclusi Exchange 2013 e Microsoft SharePoint Server, supporta il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server. Con OAuth, un protocollo di autorizzazione standard usato da numerosi siti Web principali, le credenziali utente e le password non vengono passate da un computer a un altro. L'autenticazione e l'autorizzazione si basano invece sullo scambio di token di sicurezza. questi token concedono l'accesso a un set di risorse specifico per un determinato periodo di tempo.

L'autenticazione OAuth include in genere tre parti: un singolo server di autorizzazione e i due ambiti che devono comunicare tra loro. È anche possibile eseguire l'autenticazione da server a server senza usare un server di autorizzazione, un processo che verrà illustrato più avanti in questo documento. I token di sicurezza vengono emessi dal server di autorizzazioni (noto anche come server token di sicurezza) ai due ambiti che devono comunicare. questi token verificano che le comunicazioni provenienti da un reame debbano essere considerate attendibili dall'altro Realm. Ad esempio, il server di autorizzazione può emettere token che verificano che gli utenti di un reame specifico di Lync Server 2013 siano in grado di accedere a un'area di autenticazione di Exchange 2013 specificata e viceversa.

<div>


> [!NOTE]
> Un Realm è semplicemente un contenitore di sicurezza. Per impostazione predefinita, Lync Server 2013 usa il dominio SIP predefinito come area di autenticazione OAuth. Gli spazi dei nomi SIP aggiuntivi vengono aggiunti all'elenco nome alternativo oggetto nel certificato OAuth.



</div>

Lync Server 2013 supporta tre scenari di autenticazione da server a server. Con Lync Server 2013 è possibile:

  - Configurare l'autenticazione da server a server tra un'installazione locale di Lync Server 2013 e un'installazione locale di Exchange 2013 e/o Microsoft SharePoint Server.

  - Configurare l'autenticazione da server a server tra una coppia di componenti di Office 365, ad esempio tra Microsoft Exchange e Microsoft Lync Server o tra Microsoft Lync Server e Microsoft SharePoint.

  - Configurare l'autenticazione da server a server in un ambiente interlocale, ovvero l'autenticazione da server a server tra un server locale e un componente di Office 365.

Tieni presente che, in questo momento, solo Exchange 2013, SharePoint Server e Lync Server 2013 supportano l'autenticazione da server a server; Se non si esegue uno di questi server, non sarà possibile implementare completamente l'autenticazione OAuth.

Occorre anche sottolineare che non è necessario usare l'autenticazione da server a server: non è necessaria l'autenticazione da server a server per distribuire Lync Server 2013. Se Lync Server 2013 non deve comunicare con altri server, ad esempio Exchange 2013, non è necessaria l'autenticazione da server a server.

Tuttavia, è necessaria l'autenticazione da server a server se si vogliono usare alcune delle nuove funzionalità di Lync Server, come l'"archivio contatti unificato". Con l'archivio contatti unificato, le informazioni di contatto di Lync Server 2013 sono archiviate in Exchange 2013 anziché in Lync Server; Ciò consente agli utenti di avere un singolo set di contatti facilmente accessibile dall'interno di Lync, Microsoft Outlook o Microsoft Outlook Web Access. Poiché l'archivio contatti unificato richiede Lync Server 2013 per condividere informazioni con Exchange 2013, è necessario usare l'autenticazione da server a server per distribuire la funzionalità. È necessaria anche l'autenticazione da server a server se si sceglie di usare l'archiviazione di Exchange, in cui le trascrizioni delle sessioni di messaggistica istantanea vengono salvate come messaggi di posta elettronica di Exchange 2013 anziché come singoli record di database.

Per la versione di Office 365 di Lync Server per comunicare con la controparte di Exchange, Lync Server 2013 deve prima ottenere un token di sicurezza dal server di autorizzazione. Lync Server usa quindi il token di sicurezza per identificarsi in Exchange. La versione di Exchange di Office 365 deve passare allo stesso processo per comunicare con Lync Server 2013.

Tuttavia, per l'autenticazione da server a server locale tra due server Microsoft non è necessario usare un server di token di terze parti. I prodotti server, ad esempio Lync Server 2013 ed Exchange 2013, hanno un server token incorporato che può essere usato per scopi di autenticazione con altri server Microsoft, ad esempio SharePoint Server, che supportano l'autenticazione da server a server. Ad esempio, Lync Server 2013 può emettere e firmare un token di sicurezza da solo, quindi usare il token per comunicare con Exchange 2013. In un caso come questo, non è necessario un server di token di terze parti.

Per configurare l'autenticazione da server a server per un'implementazione locale di Lync Server 2013, è necessario eseguire due operazioni:

  - Assegnare un certificato all'autorità di certificazione predefinita del token di Lync Server.

  - Configurare il server con cui Lync Server 2013 comunicherà come "applicazione partner". Se ad esempio Lync Server 2013 deve comunicare con Exchange 2013, sarà necessario configurare Exchange in modo che sia un'applicazione partner.

<div>


> [!NOTE]
> Un'applicazione partner è un'applicazione in cui Lync Server 2013 può scambiare direttamente i token di sicurezza, senza dover passare a un server token di sicurezza di terze parti.



</div>

Tieni presente che OAuth è una parte centrale del prodotto e non può essere disabilitato o rimosso.

<div>

## <a name="see-also"></a>Vedere anche


[Assegnazione di un certificato di autenticazione da server a server a Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[Configurazione di Microsoft Lync Server 2013 in un ambiente tra più locali](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

