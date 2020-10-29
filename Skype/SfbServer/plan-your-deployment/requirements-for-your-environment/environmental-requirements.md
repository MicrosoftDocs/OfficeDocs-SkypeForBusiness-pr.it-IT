---
title: Requisiti ambientali per Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Riepilogo: configurare i requisiti non server per Skype for Business Server 2015. È possibile configurare una serie di operazioni prima di eseguire la distribuzione, tra cui Active Directory, DNS, certs e fileshares.'
ms.openlocfilehash: 00b7828cfc06dd9d0ea1d7097580c9c25317e95a
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790288"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisiti ambientali per Skype for Business Server 2015
 
**Riepilogo:** Configurare i requisiti non server per Skype for Business Server 2015. È possibile configurare una serie di operazioni prima di eseguire la distribuzione, tra cui Active Directory, DNS, certs e fileshares.
  
Che cos'è un requisito ambientale per Skype for Business Server 2015? Bene, abbiamo messo tutto quello che non è direttamente il server correlato in questo argomento, in modo da non dover fare tanto clic intorno. Se si cercano prerequisiti per i server, è possibile consultare i [requisiti del server per Skype for Business server 2015](server-requirements.md) doc. la [pianificazione della rete](../../plan-your-deployment/network-requirements/network-requirements.md) è documentata anche separatamente. In caso contrario, questo è ciò che è stato ottenuto in questo articolo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [DNS (Domain Name System)](environmental-requirements.md#DNS)
  
- [Certificati](environmental-requirements.md#Certs)
  
- [Condivisione file](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Mentre molti dati di configurazione per i server e i servizi sono archiviati nell'archivio di gestione centrale di Skype for Business Server 2015, esistono ancora alcuni elementi archiviati in Active Directory:
  
|**Objets Active Directory**|**Tipi di oggetti**|
|:-----|:-----|
|Estensioni dello schema  <br/> |Estensioni degli oggetti utente  <br/> |
||Extensions for Lync Server 2013 e Lync Server 2010, per mantenere la compatibilità con le versioni precedenti supportate.  <br/> |
|Dati  <br/> |URI SIP dell'utente e altre impostazioni utente  <br/> |
||Oggetti contatto per le applicazioni (come l'applicazione Response Group e l'applicazione Operatore Conferenza).  <br/> |
||Dati pubblicati per la compatibilità con le versioni precedenti.  <br/> |
||Un punto di controllo del servizio (SCP) per l'archivio di gestione centrale.  <br/> |
||Account di autenticazione Kerberos (un oggetto computer facoltativo).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operativo per i controller di dominio

Quali sono i sistemi operativi del controller di dominio che è possibile utilizzare? Sono presenti gli elenchi seguenti:

- Windows Server 2019 (è necessario avere Skype for Business Server 2015 Cumulative Update 5 o versione successiva)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
A questo punto, il livello di funzionalità del dominio di qualsiasi dominio in cui si distribuisce Skype for Business Server 2015 e il livello di funzionalità della foresta di qualsiasi foresta in cui si distribuisce Skype for Business Server 2015 devono essere uno dei seguenti:

- Windows Server 2019 (è necessario avere Skype for Business Server 2015 Cumulative Update 5 o versione successiva)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
È possibile disporre di controller di dominio di sola lettura in questi ambienti? Certo, purché vi siano anche controller di dominio scrivibile disponibili nello stesso sito del server Skype for business.
  
A questo punto, è importante sapere che Skype for Business Server 2015 non supporta i domini con etichetta singola. Cosa sono? Se si dispone di un dominio radice con l'etichetta contoso. local, andrà bene. Se si dispone di un dominio radice appena denominato local, questo non funzionerà e non sarà supportato come risultato. [In questo articolo della Knowledge base](https://support.microsoft.com/kb/300684/en-us)è stato scritto un po' di più.
  
Anche Skype for Business Server 2015 non supporta la ridenominazione dei domini. Se hai davvero avuto a che fare, allora devi disinstallare Skype for Business Server 2015, fare la rinomina del dominio e quindi reinstallare Skype for Business Server 2015.
  
Infine, è possibile che si tratti di un dominio con un ambiente di Active Directory bloccato e che sia tutto a posto. Sono presenti ulteriori informazioni su come distribuire Skype for Business Server 2015 in questo tipo di ambiente nei documenti di distribuzione.
  
### <a name="ad-topologies"></a>Topologie AD

Le topologie supportate di Skype for Business Server 2015 sono le seguenti:
  
- Foresta singola con singolo dominio
    
- Foresta singola con albero singolo e più domini
    
- Foresta singola con più alberi e spazi dei nomi disgiunti
    
- Più foreste in una topologia di foreste centralizzate
    
- Più foreste in una topologia di foresta di risorse
    
- Più foreste in una topologia di foresta di risorse di Skype for business con Exchange Online
    
- Più foreste in una topologia con foresta di risorse con Skype for business online e Azure Active Directory Connect
    
Sono presenti diagrammi e descrizioni che consentono di determinare la topologia nell'ambiente in uso o ciò che potrebbe essere necessario configurare prima dell'installazione di Skype for Business Server 2015. Per semplificare, è inclusa anche una chiave:
  
![La è una chiave per le icone utilizzate per i diagrammi di topologia di Skype for business](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Foresta singola con singolo dominio

![Diagramma di una foresta singola di Active Directory con un solo dominio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Non è più facile, è una singola foresta di dominio, questa è una topologia comune.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Foresta singola con albero singolo e più domini

![Diagramma di singoli insiemi di strutture, albero singolo e domini di mutiple](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Questo diagramma Visualizza una singola foresta, di nuovo, ma dispone anche di uno o più domini figlio (sono presenti tre in questo esempio specifico). In questo modo, il dominio in cui vengono creati gli utenti potrebbe essere diverso dal dominio in cui è distribuito Skype for Business Server 2015. Perché preoccuparsi di questo problema? È importante tenere presente che quando si distribuisce un pool Front End di Skype for Business Server, tutti i server del pool devono trovarsi in un unico dominio. È possibile disporre di amministrazione tra domini tramite il supporto di Skype for Business Server per i gruppi di amministratori universali di Windows.
  
Torna al diagramma precedente, è possibile vedere che gli utenti di un dominio sono in grado di accedere ai pool di Skype for Business Server dallo stesso dominio o da domini diversi, anche se gli utenti si trovano in un dominio figlio.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Foresta singola con più alberi e spazi dei nomi disgiunti

![Diagramma di una singola foresta, più alberi e spazi dei nomi disgiunti](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
È possibile che si disponga di una topologia simile a questo diagramma, in cui si dispone di una foresta, ma all'interno di tale foresta sono presenti più domini, con spazi dei nomi di Active Directory separati. Se questo è il caso, questo diagramma è una buona illustrazione, in quanto sono presenti utenti in tre diversi domini che accedono a Skype for Business Server 2015. Le linee solide indicano che stanno accedendo a un pool di Skype for Business Server nel proprio dominio, mentre una linea tratteggiata indica che andranno a un pool in un albero diverso del tutto.
  
Come si può notare, gli utenti dello stesso dominio, lo stesso albero o persino un albero diverso sono in grado di accedere ai pool con esito positivo.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Più foreste in una topologia di foreste centralizzate

![Più foreste in un diagramma della topologia di foresta centrale](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 supporta più insiemi di strutture configurati in una topologia a foresta centralizzata. Se non si è sicuri di essere in grado di utilizzare, la foresta centrale nella topologia utilizza oggetti in esso per rappresentare gli utenti nelle altre foreste e ospita gli account utente per tutti gli utenti nella foresta.
  
Funzionamento. Ebbene, un prodotto di sincronizzazione della directory (come Forefront Identity Manager o FIM) gestisce gli account utente dell'organizzazione per tutta la loro esistenza. Quando un account viene creato o eliminato da una foresta, la modifica viene sincronizzata con il contatto corrispondente nella foresta centrale.
  
Chiaramente, se l'infrastruttura di Active Directory è in locale, il passaggio a questa topologia potrebbe non essere semplice, ma se si è già presenti o si pianifica l'infrastruttura forestale, può essere una buona scelta. È possibile centralizzare la distribuzione di Skype for Business Server 2015 all'interno di una singola foresta, mentre gli utenti possono cercare, comunicare e visualizzare la presenza di altri utenti in qualsiasi foresta. Tutti gli aggiornamenti dei contatti utente vengono gestiti automaticamente con il software di sincronizzazione.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Più foreste in una topologia di foresta di risorse di Skype for business
<a name="BKMK_multipleforestopology"> </a>

![Più foreste in un diagramma della topologia con foresta di risorse](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
È supportata anche una topologia della foresta di risorse. è il luogo in cui una foresta è dedicata all'esecuzione delle applicazioni server, come Microsoft Exchange Server e Skype for Business Server 2015. Questa foresta di risorse ospita anche una rappresentazione sincronizzata degli oggetti utente attivi, ma non gli account utente abilitati per l'accesso. Pertanto, la foresta di risorse è un ambiente di servizi condivisi per le altre foreste in cui risiedono gli oggetti utente e dispone di una relazione di trust a livello di foresta con la foresta di risorse.
  
Si noti che Exchange Server può essere distribuito nella stessa foresta di risorse di Skype for Business Server o in una foresta diversa.
  
Per distribuire Skype for Business Server 2015 in questo tipo di topologia, è necessario creare un oggetto utente disabilitato nella foresta di risorse per ogni account utente nelle foreste degli utenti (se Microsoft Exchange Server è già presente nell'ambiente, potrebbe essere possibile eseguire questa operazione). Sarà quindi necessario uno strumento di sincronizzazione della directory (come Forefront Identity Manager o FIM) per gestire gli account utente tramite il proprio ciclo di vita.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Più foreste in una topologia di foresta di risorse di Skype for business con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Questa topologia è simile alla topologia descritta in [più foreste in una topologia di foresta di risorse di Skype for business](environmental-requirements.md#BKMK_multipleforestopology).
  
In questa topologia sono presenti una o più foreste di utenti e Skype for Business Server viene distribuito in una foresta di risorse dedicata. Exchange Server può essere distribuito in locale nella stessa foresta di risorse o in una foresta diversa e configurato per l'ambiente ibrido con Exchange Online oppure i servizi di posta elettronica possono essere forniti esclusivamente da Exchange Online per gli account locali. Per questa topologia non è disponibile alcun diagramma.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Più foreste in una topologia con foresta di risorse con Skype for business online e Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Vengono illustrati due insiemi di strutture AD, una foresta di utenti e una foresta di risorse. Le due foreste dispongono di una relazione di trust. Sono sincronizzati con Microsoft 365 o Office 365 tramite Azure AD Connect. Tutti gli utenti sono abilitati per Skype for business tramite Microsoft 365 o Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
In questo scenario, sono presenti più foreste in locale, con una topologia con foresta di risorse. Esiste una relazione di trust completa tra le foreste di Active Directory. Lo strumento Azure Active Directory Connect viene utilizzato per sincronizzare gli account tra le foreste di utenti locali e Microsoft 365 o Office 365.
  
 L'organizzazione ha anche Microsoft 365 o Office 365 e utilizza [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) per sincronizzare gli account locali con Microsoft 365 o Office 365. Gli utenti abilitati per Skype for business sono abilitati tramite Microsoft 365 o Office 365 e Skype for business online. Skype for Business Server non è distribuito in locale.
  
L'autenticazione Single Sign-on viene fornita da una farm di Active Directory Federation Services che si trova nella foresta di utenti.
  
In questo scenario, è supportata la distribuzione di Exchange locale, Exchange Online, una soluzione di Exchange ibrida o di non distribuire Exchange. Il diagramma Visualizza solo Exchange locale, ma anche le altre soluzioni Exchange sono completamente supportate.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Più foreste in una topologia con foresta di risorse con Skype for business ibrido
<a name="BKMK_multipleforestopology"> </a>

In questo scenario, esistono una o più foreste di utenti locali e Skype for business è distribuito in una foresta di risorse dedicata ed è configurato per la modalità ibrida con Skype for business online. Exchange Server può essere distribuito in locale nella stessa foresta di risorse o in una foresta diversa e può essere configurato per l'ambiente ibrido con Exchange Online. In alternativa, i servizi di posta elettronica possono essere forniti esclusivamente da Exchange Online per gli account locali.
  
Per ulteriori informazioni, vedere [configurare un ambiente con più foreste per la versione ibrida di Skype for business](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>DNS (Domain Name System)
<a name="DNS"> </a>

Skype for Business Server 2015 richiede DNS, per i motivi seguenti:
  
- DNS consente a Skype for Business Server 2015 di individuare i pool o i server interni, consentendo la comunicazione da server a server.
    
- DNS consente ai computer client di individuare il pool Front end o il server Standard Edition utilizzato per le transazioni SIP.
    
- Associa gli URL semplici per le conferenze ai server che ospitano tali conferenze.
    
- DNS consente agli utenti esterni e ai computer client di connettersi ai server perimetrali o al proxy inverso HTTP per la messaggistica istantanea o per le conferenze.
    
- Consente ai dispositivi per comunicazioni unificate non connessi di individuare il pool Front end o il server Standard Edition in cui è in esecuzione il servizio Web aggiornamento dispositivi per ottenere gli aggiornamenti e inviare i registri.
    
- L'utilizzo di DNS consente ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni dei dispositivi.
    
- Ed è utilizzato nel bilanciamento del carico DNS.
    
È importante tenere presente che Skype for Business Server 2015 non supporta i nomi di dominio internazionalizzati (Internationalized Domain Name).
  
Ed è estremamente importante tenere presente che qualsiasi nome in DNS deve essere identico al nome del computer configurato su qualsiasi server utilizzato da Skype for Business Server 2015. In particolare, non è possibile avere nomi di breve nell'ambiente e devono avere FQDN per il generatore di topologie.
  
Questo sembra che sarebbe logico per qualsiasi computer già aggiunto a un dominio, ma se si dispone di un server perimetrale che non è aggiunto al dominio, potrebbe avere un nome breve, senza suffisso di dominio. Verificare che non sia il caso, in DNS o nel server perimetrale, o in qualsiasi server o pool di Skype for Business Server 2015.
  
E sicuramente non usano caratteri Unicode o di sottolineatura. I caratteri standard (che sono A-Z, a-z, 0-9 e segni meno) sono quelli che verranno supportati da DNS esterni e autorità di certificazione pubbliche (è necessario assegnare FQDN al SN nel certificato, non dimenticare), quindi si risparmia molto dolore se si è in mente questo nome.
  
Per ulteriori informazioni sui requisiti DNS per la rete, vedere la sezione [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) della documentazione relativa alla pianificazione.
  
## <a name="certificates"></a>Certificati
<a name="Certs"> </a>

Una delle operazioni più importanti che è possibile eseguire prima della distribuzione è assicurarsi di disporre dei certificati in ordine. Skype for Business Server 2015 ha bisogno di un'infrastruttura a chiave pubblica (PKI) per le connessioni TLS (Transport Layer Security) e MTLS (Mutual Transport Layer Security). In sostanza, per comunicare in modo sicuro in maniera standardizzata, Skype for Business Server utilizza i certificati emessi dalle autorità di certificazione (CAs).
  
Di seguito sono riportate alcune delle operazioni che Skype for Business Server 2015 utilizza i certificati per:
  
- Connessioni TLS tra client e server
    
- Connessioni MTLS tra server
    
- Federazione con individuazione DNS automatica dei partner
    
- Accesso utente remoto per la messaggistica istantanea
    
- Accesso utente esterno alle sessioni audio/video (AV), alla condivisione di applicazioni e alle conferenze
    
- Comunicazione con le applicazioni Web e Outlook Web Access (OWA)
    
Quindi la pianificazione del certificato è un must. A questo punto, è possibile esaminare un elenco di alcune delle operazioni da tenere presenti quando si richiedono i certificati:
  
- Tutti i certificati del server devono supportare l'autorizzazione server (utilizzo chiavi avanzato del server).
    
- Tutti i certificati del server devono contenere un punto di distribuzione CRL (CDP).
    
- Tutti i certificati devono essere firmati utilizzando un algoritmo di firma supportato dal sistema operativo. Skype for Business Server 2015 supporta la famiglia di dimensioni digest SHA-1 e SHA-2 (224, 256, 384 e 512 bit) e soddisfa o supera i requisiti del sistema operativo.
    
- La registrazione automatica è supportata per i server interni che eseguono Skype for Business Server 2015.
    
- La registrazione automatica non è supportata per i server Edge di Skype for Business Server 2015.
    
- Quando si invia una richiesta di certificato Web a un'autorità di certificazione (CA) di Windows Server 2003, è necessario inviarla da un computer che esegue Windows Server 2003 con SP2 oppure Windows XP.
    
> [!NOTE]
> Anche se KB922706 fornisce supporto per la risoluzione dei problemi relativi alla registrazione di certificati Web su una registrazione Web di Servizi certificati di Windows Server 2003, non consente di utilizzare Windows Server 2008, Windows Vista o Windows 7 per richiedere un certificato da una CA di Windows Server 2003. 
  
> [!NOTE]
> L'utilizzo dell'algoritmo di firma RSASSA-PSS non è supportato e può comportare errori relativi ai problemi di accesso e di inoltro di chiamata, tra gli altri. 

> [!NOTE]
> Skype for Business Server 2015 non supporta i certificati CNG.
  
- Sono supportate le lunghezze delle chiavi di crittografia pari a 1024, 2048 e 4096. È consigliabile utilizzare la lunghezza della chiave di 2048 e una maggiore.
    
- L'algoritmo digest o hash predefinito è RSA. Sono supportati anche gli algoritmi ECDH_P256, ECDH_P384 e ECDH_P521.
    
In questo modo, è molto da considerare e sicuramente esistono diversi livelli di comfort che richiedono certificati da un'autorità di certificazione. Di seguito vengono fornite ulteriori indicazioni per rendere la pianificazione il più indolore possibile.
  
### <a name="certificates-for-your-internal-servers"></a>Certificati per i server interni

È necessario disporre di certificati per la maggior parte dei server interni e, molto probabilmente, è possibile ottenerli da un'autorità di certificazione interna (che si trova nel dominio). Se si desidera, è possibile richiedere questi certificati da un'autorità di certificazione esterna (una che si trova su Internet). Se si sta chiedendo quale autorità di certificazione pubblica dovrebbe andare, è possibile consultare l'elenco dei partner di certificato per le [comunicazioni unificate](/SkypeForBusiness/certification/services-ssl) .
  
Sono inoltre necessari certificati quando Skype for Business Server 2015 comunica con altre applicazioni e server, ad esempio Microsoft Exchange Server. Questo, ovviamente, dovrà essere un certificato che può essere utilizzato da altre applicazioni e server in modo supportato. Skype for Business Server 2015 e altri prodotti Microsoft supportano il protocollo di autorizzazione aperta (OAuth) per l'autenticazione e l'autorizzazione da server a server. Se si è interessati a questo argomento, è presente un ulteriore articolo sulla pianificazione per OAuth e Skype for Business Server 2015.
  
Skype for Business Server 2015 include anche il supporto per i certificati (senza richiedere) firmati utilizzando la funzione hash di crittografia SHA-256. Per supportare l'accesso esterno tramite SHA-256, è necessario che il certificato esterno venga emesso da un'autorità di certificazione pubblica utilizzando SHA-256.
  
Per cercare di mantenere le cose semplici, sono stati inseriti i requisiti dei certificati per i server Standard Edition, i pool Front end e altri ruoli, nelle tabelle seguenti, con l'contoso.com fittizio utilizzato per gli esempi (probabilmente si utilizzerà qualcos'altro per l'ambiente). Si tratta di tutti i certificati del server Web standard, con chiavi private non esportabili. Alcuni elementi aggiuntivi da prendere nota:
  
- L'utilizzo della chiave avanzata del server viene configurato automaticamente quando si utilizza la configurazione guidata certificati per richiedere i certificati.
    
- Ogni nome descrittivo del certificato deve essere univoco nell'archivio del computer.
    
- Come per i nomi di esempio riportati di seguito, se è stato configurato sipinternal.contoso.com o sipexternal.contoso.com nel DNS, è necessario aggiungerlo al nome alternativo del soggetto del certificato (SAN).
    
Certificati per i server Standard Edition:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |FQDN del pool  <br/> |FQDN del pool e FQDN del server  <br/> Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |SN = SE01. contoso. com; SAN = SE01. contoso. com  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |Nel caso del server Standard Edition, l'FQDN del server corrisponde all'FQDN del pool.  <br/> La procedura guidata consente di rilevare eventuali domini SIP specificati durante l'installazione e di aggiungerli automaticamente come nomi alternativi del soggetto.  <br/> È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.  <br/> |
|Interno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che corrisponde al nome di dominio completo del server)  <br/> E  <br/> • Soddisfa gli URL semplici  <br/> • URL semplice con accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = \* . contoso.com  <br/> |Non è possibile eseguire l'override del nome FQDN Web interno in Generatore di topologie.  <br/> Se si dispone di più URL semplici, è necessario includerli tutti come SANs.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
|Esterno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • URL semplice con accesso esterno  <br/> • Soddisfa gli URL semplici per dominio SIP  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = \* . contoso.com  <br/> |Se sono presenti più URL semplici, è necessario includerli tutti come nomi alternativi del soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
   
Certificati per front end server in un pool Enterprise Edition front end:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |FQDN del pool  <br/> |FQDN del pool e FQDN del server  <br/> Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.  <br/> È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.  <br/> |
|Interno Web  <br/> |FQDN del pool  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che non corrisponde al nome di dominio completo del server)  <br/> • FQDN del server  <br/> • FQDN del pool di Skype for business  <br/> E  <br/> • Soddisfa gli URL semplici  <br/> • URL semplice con accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \* . contoso.com  <br/> |Se sono presenti più URL semplici, è necessario includerli tutti come nomi alternativi del soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
|Esterno Web  <br/> |FQDN del pool  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • URL semplice con accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \* . contoso.com  <br/> |Se sono presenti più URL semplici, è necessario includerli tutti come nomi alternativi del soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
   
Certificati per il server Director:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |Pool Director  <br/> |FQDN del server Director, FQDN del pool di server Director.  <br/> Se il pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria nei criteri di gruppo, saranno inoltre necessarie voci per SIP. SipDomain (per ogni dominio SIP di cui si dispone).  <br/> |pool.contoso.com; SAN = dir01. contoso. com  <br/> Se il pool di server Director rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Interno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che corrisponde al nome di dominio completo del server)  <br/> • FQDN del server  <br/> • FQDN del pool di Skype for business  <br/> E  <br/> • Soddisfa gli URL semplici  <br/> • URL semplice con accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \* . contoso.com  <br/> |
|Esterno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • Soddisfa gli URL semplici per dominio SIP  <br/> • URL semplice con accesso esterno  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |Il nome FQDN Web esterno del Director deve essere diverso dal pool Front end o dal front end server.  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \* . contoso.com  <br/> |
   
Certificati per Mediation Server autonomo:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |FQDN del pool  <br/> |FQDN del pool  <br/> FQDN del server dei membri del pool  <br/> |SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. NET  <br/> |
   
Certificati per Survivable Branch Appliance:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |FQDN del dispositivo  <br/> |SIP.\<sipdomain\> (è necessaria una sola voce per dominio SIP)  <br/> |SN = sba01. contoso. NET; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificati per il server Chat persistente

Quando si installa il server Chat persistente, è necessario un certificato emesso dalla stessa CA come quello utilizzato dai server interni di Skype for Business Server 2015. È necessario eseguire questa operazione per ogni server che esegue i servizi Web di chat persistente per il caricamento o il download di file. È consigliabile disporre dei certificati necessari prima di avviare l'installazione di Persistent Chat e, se l'autorità di certificazione è esterna, anche di più (queste operazioni possono richiedere un po' di tempo per essere emesse).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificati per l'accesso degli utenti esterni (Edge)

Skype for Business Server 2015 supporta l'utilizzo di un **singolo certificato pubblico** per le interfacce esterne di Access e Web Conferencing Edge, oltre al servizio di autenticazione a/V, che è tutto fornito tramite i server perimetrali. L'interfaccia interna del server perimetrale utilizzerà in genere un certificato privato emesso dall'autorità di certificazione interna, ma se si preferisce, è possibile utilizzare un certificato pubblico anche per questo, se si tratta di una CA attendibile.
  
Il proxy inverso (RP) intende anche utilizzare un certificato pubblico e crittografa la comunicazione dal RP ai client e il RP ai server interni utilizzando HTTP (o più precisamente, TLS su HTTP).
  
### <a name="certificates-for-mobility"></a>Certificati per i dispositivi mobili

Se si sta distribuendo mobilità e si sta supportando l'individuazione automatica per i client mobili, è necessario includere alcune voci aggiuntive del nome alternativo soggetto nei certificati per supportare le connessioni sicure dai client mobili.
  
Quali certificazioni? Per l'individuazione automatica dei certificati, è necessario utilizzare i nomi di SAN:
  
- Pool Director
    
- Pool Front End
    
- Proxy inverso
    
Verranno elencate le specifiche di ogni tabella riportata di seguito.
  
A questo punto, si tratta di un po' di tempo di prepianificazione, ma a volte è stato distribuito Skype for Business Server 2015 senza intendere distribuire la mobilità e la linea viene visualizzata quando si dispone già di certificati nell'ambiente in uso. La loro riemissione tramite una CA interna è in genere piuttosto semplice, ma con certificati pubblici provenienti da un'autorità di certificazione pubblica, che può essere un po' più costosa.
  
Se è ciò che si sta esaminando e se si dispone di un numero elevato di domini SIP (che renderanno l'aggiunta di SANS più onerose), è possibile configurare il proxy inverso per l'utilizzo di HTTP per la richiesta iniziale del servizio di individuazione automatica, anziché utilizzare HTTPS (che è la configurazione predefinita). L'argomento Planning for Mobility contiene altre informazioni.
  
Requisiti dei certificati per pool di server Director e front end:
  
|**Descrizione**|**Voce SAN**|
|:-----|:-----|
|URL del servizio di individuazione automatica interno  <br/> |SAN = LyncdiscoverInternal.\<sipdomain\>  <br/> |
|URL del servizio di individuazione automatica esterno  <br/> |SAN = lyncdiscover.\<sipdomain\>  <br/> |
   
In alternativa, è possibile utilizzare SAN = \* .\<sipdomain\>
  
Requisiti dei certificati per il proxy inverso (public CA):
  
|**Descrizione**|**Voce SAN**|
|:-----|:-----|
|URL del servizio di individuazione automatica esterno  <br/> |SAN = lyncdiscover.\<sipdomain\>  <br/> |
   
Questa SAN deve essere assegnata al certificato assegnato al listener SSL nel proxy inverso.
  
> [!NOTE]
> Il listener del proxy inverso avrà SANs per gli URL dei servizi Web esterni. Alcuni esempi sono SAN = skypewebextpool01. contoso. com e dirwebexternal.contoso.com, se è stato distribuito il server Director (facoltativo). 
  
## <a name="file-share"></a>Condivisione file
<a name="Fileshare"> </a>

Skype for Business Server 2015 è in grado di utilizzare la stessa condivisione file per tutti i file di archiviazione. È necessario tenere presente quanto segue:
  
- Una condivisione file deve trovarsi su una rete di archiviazione diretta (DAS, Direct Attached Storage) o su un'area di archiviazione (SAN) e include il file System distribuito (DFS) e un array di dischi indipendenti (RAID) per gli archivi di file. Per ulteriori informazioni su DFS per Windows Server 2012, vedere [Questa pagina DFS](https://technet.microsoft.com/library/jj127250.aspx).
    
- È consigliabile disporre di un cluster condiviso per la condivisione file. Se si sta utilizzando uno, è consigliabile eseguire il cluster di Windows Server 2012 o Windows Server 2012 R2. Anche Windows Server 2008 R2 è accettabile. Perché le finestre più recenti? Le versioni precedenti potrebbero non disporre delle autorizzazioni appropriate per abilitare tutte le funzionalità. È possibile utilizzare l'amministratore di cluster per creare le condivisioni di file e in questo [modo viene illustrato come creare condivisioni di file in un](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) articolo di cluster.
    
> [!CAUTION] 
> È necessario sapere che l'utilizzo di Network Attached Storage (NAS) come condivisione file non è supportato, quindi utilizzare una delle opzioni sopra elencate. 
  
