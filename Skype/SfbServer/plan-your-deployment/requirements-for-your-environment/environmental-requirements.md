---
title: Requisiti ambientali di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Riepilogo: configurare i requisiti non server per Skype for Business Server 2015. Prima di eseguire la distribuzione è possibile configurare una varietà di elementi, inclusi Active Directory, DNS, certs e fileshares.'
ms.openlocfilehash: 59f7bed17c217eda46314d2a133c0d5671682824
ms.sourcegitcommit: ab259764dc50bdd52efed3abb1d065ee19486946
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "36393428"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisiti ambientali di Skype for Business Server 2015
 
**Riepilogo:** Configurare i requisiti non server per Skype for Business Server 2015. Prima di eseguire la distribuzione è possibile configurare una varietà di elementi, inclusi Active Directory, DNS, certs e fileshares.
  
Che cos'è un requisito ambientale per Skype for Business Server 2015? Beh, abbiamo inserito tutto ciò che non è direttamente correlato al server in questo argomento, quindi non devi fare molto clic in giro. Se si cercano prerequisiti per i server, è possibile controllare i [requisiti del server per Skype for Business server 2015](server-requirements.md) doc. anche la[pianificazione della rete](../../plan-your-deployment/network-requirements/network-requirements.md) è documentata separatamente. In caso contrario, si tratta di questo articolo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Domain Name System (DNS)](environmental-requirements.md#DNS)
  
- [Certificati](environmental-requirements.md#Certs)
  
- [Condivisione file](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Mentre molti dati di configurazione per server e servizi sono archiviati in Central Management store di Skype for Business Server 2015, alcuni elementi sono ancora archiviati in Active Directory:
  
|**Oggetti Active Directory**|**Tipi di oggetti**|
|:-----|:-----|
|Estensioni dello schema  <br/> |Estensioni degli oggetti utente  <br/> |
||Estensioni per Lync Server 2013 e Lync Server 2010 per mantenere la compatibilità con le versioni precedenti supportate.  <br/> |
|Dati  <br/> |URI SIP utente e altre impostazioni utente  <br/> |
||Oggetti contatto per le applicazioni, ad esempio l'applicazione Response Group e l'applicazione per i servizi di conferenza.  <br/> |
||Dati pubblicati per la compatibilità con le versioni precedenti.  <br/> |
||Un punto di controllo del servizio (SCP) per l'Central Management store.  <br/> |
||Account di autenticazione Kerberos (un oggetto computer facoltativo).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operativo per i controller di dominio

Qual è il sistema operativo del controller di dominio che può essere usato? È presente l'elenco seguente:

- Windows Server 2019 (è necessario avere Skype for Business Server 2015 aggiornamento cumulativo 5 o versioni successive)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
A questo punto, il livello di funzionalità del dominio di qualsiasi dominio in cui si distribuisce Skype for Business Server 2015 e il livello di funzionalità della foresta di qualsiasi foresta in cui si distribuisce Skype for Business Server 2015, devono essere uno dei seguenti:

- Windows Server 2019 (è necessario avere Skype for Business Server 2015 aggiornamento cumulativo 5 o versioni successive)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
In questi ambienti è possibile avere controller di dominio di sola lettura? Certo, purché sia disponibile anche il controller di dominio scrivibile.
  
Ora è importante sapere che Skype for Business Server 2015 non supporta i domini con etichetta singola. Cosa sono? Se si ha un dominio radice con l'etichetta contoso. local, andra ' tutto bene. Se si ha un dominio radice appena denominato local, non funzionerà e non sarà supportato come risultato. Un po' di più su questo articolo è stato scritto [in questa Knowledge base](https://support.microsoft.com/kb/300684/en-us).
  
Anche Skype for Business Server 2015 non supporta la ridenominazione dei domini. Se si ha veramente a che fare, è necessario disinstallare Skype for Business Server 2015, eseguire la ridenominazione del dominio e quindi reinstallare Skype for Business Server 2015.
  
Infine, potresti avere a che fare con un dominio con un ambiente AD DS bloccato e questo è tutto a posto. Sono presenti ulteriori informazioni su come distribuire Skype for Business Server 2015 in questo tipo di ambiente nei documenti di distribuzione.
  
### <a name="ad-topologies"></a>Topologie AD

Le topologie supportate di Skype for Business Server 2015 sono:
  
- Singola foresta con un singolo dominio
    
- Singola foresta con un solo albero e più domini
    
- Foresta singola con più alberi e spazi dei nomi disgiunti
    
- Più foreste in una topologia di foresta centrale
    
- Più foreste in una topologia di foresta di risorse
    
- Più foreste in una topologia della foresta di risorse di Skype for business con Exchange Online
    
- Più foreste in una topologia di foresta di risorse con Skype for business online ed Azure Active Directory Connect
    
Sono presenti diagrammi e descrizioni che consentono di determinare la topologia che si ha nell'ambiente o le operazioni che è necessario configurare prima di installare Skype for Business Server 2015. Per semplificare l'attività, è inclusa anche una chiave:
  
![È una chiave per le icone usate per i diagrammi di topologia di Skype for business](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Singola foresta con un singolo dominio

![Diagramma della foresta singola di Active Directory con un singolo dominio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Non è più facile, ma è una singola foresta di domini, una topologia comune.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Singola foresta con un solo albero e più domini

![Diagramma di un singolo insieme di strutture, ad albero singolo e a domini mutiple](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Questo diagramma mostra di nuovo una singola foresta, ma include anche uno o più domini figlio (ne sono presenti tre in questo esempio specifico). In questo modo il dominio in cui vengono creati gli utenti potrebbe essere diverso dal dominio in cui è distribuito Skype for Business Server 2015. Perché preoccuparsi di questo problema? È importante ricordare che quando si distribuisce un pool Front-End di Skype for Business Server, tutti i server del pool devono essere in un unico dominio. Puoi avere l'amministrazione tra domini tramite il supporto di Skype for Business Server per i gruppi di amministratori universali di Windows.
  
Tornando al diagramma precedente, è possibile vedere che gli utenti di un dominio possono accedere ai pool di Skype for Business Server dallo stesso dominio o da domini diversi, anche se questi utenti si trovano in un dominio figlio.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Foresta singola con più alberi e spazi dei nomi disgiunti

![Diagramma di una singola foresta, più alberi e spazi dei nomi disgiunti](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Può essere che si disponga di una topologia simile a questo diagramma, in cui è presente una sola foresta, ma all'interno di tale foresta sono presenti più domini, con spazi dei nomi degli annunci distinti. In questo caso, questo diagramma è una buona illustrazione, dato che abbiamo utenti in tre diversi domini che accedono a Skype for Business Server 2015. Le linee solide indicano che stanno accedendo a un pool di Skype for Business Server nel proprio dominio, mentre una linea tratteggiata indica che andranno a un pool in un albero diverso.
  
Come si può vedere, gli utenti dello stesso dominio, lo stesso albero o anche un albero diverso riescono ad accedere ai pool con successo.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Più foreste in una topologia di foresta centrale

![Più foreste in un diagramma della topologia di foresta centrale](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 supporta più foreste configurate in una topologia di foresta centrale. Se non si è certi che si ha, la foresta centrale della topologia usa oggetti in esso per rappresentare gli utenti nelle altre foreste e ospita gli account utente per tutti gli utenti della foresta.
  
Come funziona? Un prodotto di sincronizzazione della directory, ad esempio Forefront Identity Manager o FIM, gestisce gli account utente dell'organizzazione in tutta la sua esistenza. Quando si crea o si elimina un account da una foresta, la modifica viene sincronizzata con il contatto corrispondente nella foresta centrale.
  
Chiaramente, se l'infrastruttura degli annunci è sul posto per passare a questa topologia, potrebbe non essere facile, ma se si è già lì o si sta ancora pianificando l'infrastruttura della foresta, è possibile che sia una buona scelta. Puoi centralizzare la distribuzione di Skype for Business Server 2015 in una singola foresta, mentre gli utenti possono cercare, comunicare e visualizzare la presenza di altri utenti in qualsiasi foresta. Tutti gli aggiornamenti dei contatti utente vengono gestiti automaticamente con il software di sincronizzazione.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Più foreste in una topologia della foresta di risorse di Skype for business
<a name="BKMK_multipleforestopology"> </a>

![Più foreste in un diagramma della topologia della foresta di risorse](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
È supportata anche una topologia di foresta di risorse. è la posizione in cui è dedicata una foresta all'uso delle applicazioni server, come Microsoft Exchange Server e Skype for Business Server 2015. Questa foresta di risorse ospita anche una rappresentazione sincronizzata di oggetti utente attivi, ma nessun account utente abilitato per l'accesso. La foresta delle risorse è quindi un ambiente di servizi condivisi per altri insiemi di strutture in cui risiedono gli oggetti utente e hanno una relazione di trust a livello di foresta con la foresta di risorse.
  
Si noti che Exchange Server può essere distribuito nella stessa foresta di risorse di Skype for Business Server o in un'altra foresta.
  
Per distribuire Skype for Business Server 2015 in questo tipo di topologia, devi creare un oggetto utente disabilitato nella foresta di risorse per ogni account utente nelle foreste degli utenti (se Microsoft Exchange Server è già presente nell'ambiente, questo potrebbe essere fatto per te). Sarà quindi necessario uno strumento di sincronizzazione della directory, ad esempio Forefront Identity Manager o FIM, per gestire gli account utente tramite il loro ciclo di vita.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Più foreste in una topologia della foresta di risorse di Skype for business con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Questa topologia è simile alla topologia descritta in [più foreste in una topologia della foresta di risorse di Skype for business](environmental-requirements.md#BKMK_multipleforestopology).
  
In questa topologia sono presenti una o più foreste degli utenti e Skype for Business Server è distribuito in una foresta di risorse dedicata. Exchange Server può essere distribuito in locale nella stessa foresta di risorse o in un'altra foresta e configurato per l'ibrido con Exchange Online oppure i servizi di posta elettronica possono essere forniti esclusivamente da Exchange Online per gli account locali. Per questa topologia non è disponibile un diagramma.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Più foreste in una topologia di foresta di risorse con Skype for business online ed Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Mostra due foreste di annunci, una foresta utente e una foresta di risorse. Le due foreste hanno una relazione di trust. Vengono sincronizzati con Office 365 usando Azure AD Connect. Tutti gli utenti sono abilitati per Skype for business tramite Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Con questo scenario, sono presenti più foreste locali con una topologia di foresta di risorse. Esiste una relazione di trust completa tra le foreste di Active Directory. Lo strumento Azure Active Directory Connect viene usato per sincronizzare gli account tra le foreste degli utenti locali e Office 365.
  
 L'organizzazione ha anche Office 365 e USA [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) per sincronizzare gli account locali con Office 365. Gli utenti abilitati per Skype for business sono abilitati tramite Office 365 e Skype for business online. Skype for Business Server non è distribuito in locale.
  
L'autenticazione Single Sign-on viene fornita da una farm di Active Directory Federation Services situata nella foresta degli utenti.
  
In questo scenario, è supportata la distribuzione di Exchange locale, Exchange Online, una soluzione di Exchange ibrida o non è stato possibile distribuire Exchange. Il diagramma mostra solo Exchange locale, ma anche le altre soluzioni di Exchange sono completamente supportate.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Più foreste in una topologia di foresta di risorse con Skype for business ibrido
<a name="BKMK_multipleforestopology"> </a>

In questo scenario sono presenti una o più foreste di utenti locali e Skype for business è distribuito in una foresta di risorse dedicata ed è configurato per la modalità ibrida con Skype for business online. Exchange Server può essere distribuito localmente nella stessa foresta di risorse o in un'altra foresta e può essere configurato per l'ibrido con Exchange Online. In alternativa, i servizi di posta elettronica possono essere forniti esclusivamente da Exchange Online per gli account locali.
  
Per altre informazioni, vedere [configurare un ambiente con più insiemi di strutture per Skype for business ibrido](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Skype for Business Server 2015 richiede il DNS, per i motivi seguenti:
  
- DNS consente a Skype for Business Server 2015 di individuare i server o i pool interni, consentendo le comunicazioni da server a server.
    
- DNS consente ai computer client di individuare il pool Front-end o il server Standard Edition in uso per le transazioni SIP.
    
- Associa URL semplici per le conferenze con i server che ospitano tali conferenze.
    
- DNS consente agli utenti esterni e ai computer client di connettersi agli Edge Server o al proxy inverso HTTP per la messaggistica istantanea o i servizi di conferenza.
    
- Consente ai dispositivi Unified Communications (UC) che non sono connessi alla scoperta del pool Front-end o del server Standard Edition in cui è in uso il servizio Web Update del dispositivo per ottenere aggiornamenti e inviare log.
    
- L'uso di DNS consente ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni del dispositivo.
    
- Ed è usato in bilanciamento del carico DNS.
    
È importante notare che Skype for Business Server 2015 non supporta i nomi di dominio internazionalizzati (IDN).
  
Ed è estremamente importante tenere presente che qualsiasi nome in DNS è identico al nome del computer configurato in qualsiasi server usato da Skype for Business Server 2015. In particolare, non possiamo avere nomi brevi nell'ambiente e dobbiamo avere FQDN per generatore di topologie.
  
Questo aspetto sarebbe logico per qualsiasi computer già associato a un dominio, ma se si dispone di un server perimetrale non collegato al dominio, potrebbe essere impostato su un nome breve, senza suffisso di dominio. Verificare che non sia il caso, in DNS o nell'Edge Server o in qualsiasi server o pool di Skype for Business Server 2015.
  
E sicuramente non usare caratteri Unicode o carattere di sottolineatura. I caratteri standard (che sono A-Z, a-z, 0-9 e segni meno) sono quelli che verranno supportati da DNS esterni e autorità di certificazione pubbliche (è necessario assegnare FQDN al SN nel certificato, non dimenticarlo), in modo da risparmiare molto dolore se è possibile assegnare un nome in considerazione.
  
Per ulteriori informazioni sui requisiti DNS per la rete, vedere la sezione [Networking](../../plan-your-deployment/network-requirements/network-requirements.md) della documentazione relativa alla pianificazione.
  
## <a name="certificates"></a>Certificati
<a name="Certs"> </a>

Una delle operazioni più importanti che è possibile eseguire prima della distribuzione è assicurarsi di avere i certificati in ordine. Skype for Business Server 2015 richiede un'infrastruttura a chiave pubblica (PKI) per le connessioni TLS (Transport Layer Security) e MTLS (Mutual Transport Layer Security). In sostanza, per comunicare in modo sicuro in maniera standardizzata, Skype for Business Server usa i certificati emessi da autorità di certificazione (CAs).
  
Queste sono alcune delle operazioni che Skype for Business Server 2015 USA i certificati per:
  
- Connessioni TLS tra client e server
    
- Connessioni MTLS tra server
    
- Individuazione automatica DNS usin dei partner
    
- Accesso remoto agli utenti per la messaggistica istantanea (IM)
    
- Accesso degli utenti esterni a sessioni audio/video (AV), condivisione applicazioni e conferenze
    
- Comunicare con le applicazioni Web e Outlook Web App (OWA)
    
Quindi la pianificazione del certificato è un must. Esaminiamo ora un elenco di alcune delle operazioni che è necessario tenere presenti quando si richiedono certificati:
  
- Tutti i certificati server devono supportare l'autorizzazione del server (server EKU).
    
- Tutti i certificati server devono contenere un punto di distribuzione CRL (CDP).
    
- Tutti i certificati devono essere firmati usando un algoritmo di firma supportato dal sistema operativo. Skype for Business Server 2015 supporta la famiglia di dimensioni digest SHA-1 e SHA-2 (224, 256, 384 e 512 bit) e soddisfa o supera i requisiti del sistema operativo.
    
- La registrazione automatica è supportata per i server interni con Skype for Business Server 2015.
    
- La registrazione automatica non è supportata per i server Edge di Skype for Business Server 2015.
    
- Quando si invia una richiesta di certificato basata sul Web a una CA di Windows Server 2003, è necessario inviarla da un computer che utilizza Windows Server 2003 con SP2 o Windows XP.
    
> [!NOTE]
> Anche se KB922706 offre il supporto per la risoluzione dei problemi di registrazione di certificati Web in base a una registrazione Web di Servizi certificati di Windows Server 2003, non consente di usare Windows Server 2008, Windows Vista o Windows 7 per richiedere un certificato da una CA di Windows Server 2003. 
  
> [!NOTE]
> L'uso dell'algoritmo di firma RSASSA-PSS non è supportato e può comportare errori per i problemi di accesso e inoltro di chiamata, tra gli altri. 
  
- Sono supportate le lunghezze della chiave di crittografia di 1024, 2048 e 4096. Sono consigliate le lunghezze delle chiavi di 2048 e superiori.
    
- L'algoritmo digest predefinito o la firma hash è RSA. Sono supportati anche gli algoritmi ECDH_P256, ECDH_P384 e ECDH_P521.
    
Questo è un modo molto a cui pensare, e sicuramente c'è una varietà di livelli di comfort che richiedono certificati da una CA. Per rendere la pianificazione il più indolore possibile, verranno fornite ulteriori indicazioni.
  
### <a name="certificates-for-your-internal-servers"></a>Certificati per i server interni

Avrai bisogno di certificati per la maggior parte dei server interni e probabilmente li otterrai da una CA interna (quella che si trova nel dominio). Se si vuole, è possibile richiedere questi certificati da una CA esterna (uno disponibile su Internet). Se si sta chiedendo quale autorità pubblica dovrebbe andare, è possibile consultare l'elenco [partner certificati comunicazioni unificate](/SkypeForBusiness/certification/services-ssl) .
  
Ti serviranno anche i certificati quando Skype for Business Server 2015 comunica con altre applicazioni e server, come Microsoft Exchange Server. Questo, ovviamente, dovrà essere un certificato che queste altre app e server possono usare in modo supportato. Skype for Business Server 2015 e altri prodotti Microsoft supportano il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server. Se si è interessati a questo problema, è presente un altro articolo sulla pianificazione per OAuth e Skype for Business Server 2015.
  
Skype for Business Server 2015 include anche il supporto per (senza richiedere) i certificati firmati con la funzione hash crittografico SHA-256. Per supportare l'accesso esterno tramite SHA-256, il certificato esterno deve essere emesso da una CA pubblica tramite SHA-256.
  
Per cercare di semplificare le cose, abbiamo inserito i requisiti di certificato per i server Standard Edition, i pool Front-end e altri ruoli nelle tabelle seguenti, con il contoso.com fittizio usato per gli esempi (probabilmente userai qualcosa else per l'ambiente). Si tratta di tutti i certificati server Web standard, con chiavi private non esportabili. Altre informazioni da tenere presenti:
  
- L'utilizzo di chiave avanzata server (EKU) viene configurato automaticamente quando si usa la procedura guidata certificati per richiedere certificati.
    
- Ogni nome descrittivo del certificato deve essere univoco nell'archivio di computer.
    
- Come per i nomi di esempio seguenti, se è stato configurato sipinternal.contoso.com o sipexternal.contoso.com nel DNS, è necessario aggiungerlo al nome alternativo soggetto del certificato (SAN).
    
Certificati per server Standard Edition:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|**Commenti**|
|:-----|:-----|:-----|:-----|:-----|
|Predefinita  <br/> |Nome di dominio completo del pool  <br/> |Nome di dominio completo del pool e nome di dominio completo del server  <br/> Se si hanno più domini SIP ed è stata abilitata la configurazione automatica del client, la procedura guidata certificati rileva e aggiunge ogni FQDN del dominio SIP supportato.  <br/> Se questo pool è il server di accesso automatico per i client e la corrispondenza Strict Domain Name System (DNS) è necessaria in criteri di gruppo, sono necessarie anche le voci per SIP. SipDomain (per ogni dominio SIP).  <br/> |SN = SE01. contoso. com; SAN = SE01. contoso. com  <br/> Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, è necessario anche SAN = SIP. contoso. com; SAN = SIP. fabrikam. com  <br/> |Nel server standard di server Standard Edition il nome di dominio completo del server è uguale al nome di dominio completo del pool.  <br/> La procedura guidata rileva tutti i domini SIP specificati durante l'installazione e li aggiunge automaticamente al nome alternativo oggetto.  <br/> Puoi anche usare questo certificato per l'autenticazione da server a server.  <br/> |
|Interno Web  <br/> |Nome di dominio completo del server  <br/> |Ognuna delle opzioni seguenti:  <br/> • FQDN Web interno (che corrisponde al nome di dominio completo del server)  <br/> E  <br/> • Incontra URL semplici  <br/> • URL semplice con accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com  <br/> Uso di un certificato con caratteri jolly:  <br/> SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN =\*. contoso.com  <br/> |Non è possibile eseguire l'override del FQDN Web interno in Generatore di topologie.  <br/> Se si hanno più URL semplici di riunione, è necessario includerli tutti come SANs.  <br/> Le voci con caratteri jolly sono supportate per le voci URL semplici.  <br/> |
|Web esterno  <br/> |Nome di dominio completo del server  <br/> |Ognuna delle opzioni seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • URL semplice con accesso esterno  <br/> • Soddisfa gli URL semplici per ogni dominio SIP  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com  <br/> Uso di un certificato con caratteri jolly:  <br/> SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN =\*. contoso.com  <br/> |Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci URL semplici.  <br/> |
   
Certificati per i server front-end in un pool Front-end:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|**Commenti**|
|:-----|:-----|:-----|:-----|:-----|
|Predefinita  <br/> |Nome di dominio completo del pool  <br/> |Nome di dominio completo del pool e nome di dominio completo del server  <br/> Se si hanno più domini SIP ed è stata abilitata la configurazione automatica del client, la procedura guidata certificati rileva e aggiunge ogni FQDN del dominio SIP supportato.  <br/> Se questo pool è il server di accesso automatico per i client e la corrispondenza Strict Domain Name System (DNS) è necessaria in criteri di gruppo, sono necessarie anche le voci per SIP. SipDomain (per ogni dominio SIP).  <br/> |SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com  <br/> Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, è necessario anche SAN = SIP. contoso. com; SAN = SIP. fabrikam. com  <br/> |La procedura guidata rileva tutti i domini SIP specificati durante l'installazione e li aggiunge automaticamente al nome alternativo oggetto.  <br/> Puoi anche usare questo certificato per l'autenticazione da server a server.  <br/> |
|Interno Web  <br/> |Nome di dominio completo del pool  <br/> |Ognuna delle opzioni seguenti:  <br/> • FQDN Web interno (che non corrisponde al nome di dominio completo del server)  <br/> • FQDN server  <br/> • FQDN del pool di Skype for business  <br/> E  <br/> • Incontra URL semplici  <br/> • URL semplice con accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com  <br/> Uso di un certificato con caratteri jolly:  <br/> SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN =\*. contoso.com  <br/> |Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci URL semplici.  <br/> |
|Web esterno  <br/> |Nome di dominio completo del pool  <br/> |Ognuna delle opzioni seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • URL semplice con accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com  <br/> Uso di un certificato con caratteri jolly:  <br/> SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN =\*. contoso.com  <br/> |Se si hanno più URL semplici di riunione, è necessario includerli tutti come nomi alternativi oggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci URL semplici.  <br/> |
   
Certificati per il direttore:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefinita  <br/> |Pool di Director  <br/> |Nome di dominio completo del Director, FQDN del pool di Director.  <br/> Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, saranno necessarie anche le voci per SIP. SipDomain (per ogni dominio SIP disponibile).  <br/> |pool.contoso.com; SAN = dir01. contoso. com  <br/> Se questo pool di Director è il server di accesso automatico per i client e la corrispondenza DNS rigorosa è necessaria in criteri di gruppo, è necessario anche SAN = SIP. contoso. com; SAN = SIP. fabrikam. com  <br/> |
|Interno Web  <br/> |Nome di dominio completo del server  <br/> |Ognuna delle opzioni seguenti:  <br/> • FQDN Web interno (che corrisponde al nome di dominio completo del server)  <br/> • FQDN server  <br/> • FQDN del pool di Skype for business  <br/> E  <br/> • Incontra URL semplici  <br/> • URL semplice con accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com; SAN = admin. contoso. com  <br/> Uso di un certificato con caratteri jolly:  <br/> SN = dir01. contoso. com; SAN = dir01. contoso. com SAN =\*. contoso.com  <br/> |
|Web esterno  <br/> |Nome di dominio completo del server  <br/> |Ognuna delle opzioni seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • Soddisfa gli URL semplici per ogni dominio SIP  <br/> • URL semplice con accesso esterno  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |Il nome FQDN Web esterno del Director deve essere diverso dal pool Front-end o dal server front-end.  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = meet. contoso. com; SAN = meet. fabrikam. com; SAN = dialin. contoso. com  <br/> Uso di un certificato con caratteri jolly:  <br/> SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN =\*. contoso.com  <br/> |
   
Certificati per Mediation Server autonomo:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefinita  <br/> |Nome di dominio completo del pool  <br/> |Nome di dominio completo del pool  <br/> Nome di dominio completo del server dei membri del pool  <br/> |SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. NET  <br/> |
   
Certificati per Survivable Branch Appliance:
  
|**Certificato**|**Nome soggetto/nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefinita  <br/> |Nome di dominio completo dell'accessorio  <br/> |SIP. \<SipDomain\> (è necessaria una sola voce per ogni dominio SIP)  <br/> |SN = sba01. contoso. NET; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificati per il server di chat persistente

Quando si installa il server di chat persistente, sarà necessario un certificato emesso dalla stessa CA di quello usato dai server interni di Skype for Business Server 2015. Questa operazione deve essere eseguita per ogni server che gestisce i servizi Web di chat persistenti per l'upload/download di file. Ti consigliamo vivamente di avere i certificati necessari prima di iniziare l'installazione della chat persistente e se la tua CA è esterna, ancora di più (questi elementi possono richiedere un po' di tempo per essere emessi).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificati per l'accesso degli utenti esterni (Edge)

Skype for Business Server 2015 supporta l'uso di un **unico certificato pubblico** per le interfacce esterne di Access e Web Conferencing Edge, oltre al servizio di autenticazione a/V, che viene fornito tramite gli Edge Server. L'interfaccia interna di Edge utilizzerà in genere un certificato privato emesso dalla CA interna, ma se si preferisce, è possibile usare anche un certificato pubblico, se si tratta di una CA attendibile.
  
Anche il proxy inverso (RP) utilizzerà un certificato pubblico e crittografa la comunicazione dal RP ai client e il RP ai server interni tramite HTTP (o più precisamente, TLS su HTTP).
  
### <a name="certificates-for-mobility"></a>Certificati per la mobilità

Se si sta distribuendo la mobilità e si supporta l'individuazione automatica per i client mobili, sarà necessario includere alcune voci aggiuntive per i nomi alternativi nei certificati per supportare le connessioni sicure dai client mobili.
  
Quali certs? Sono necessari i nomi di SAN per l'individuazione automatica dei certificati:
  
- Pool di Director
    
- Pool Front End
    
- Proxy inverso
    
Elenchiamo le specifiche in ogni tabella seguente.
  
Questo è il punto in cui una piccola pianificazione preliminare è buona, ma a volte è stata distribuita una versione di Skype for Business Server 2015 senza l'intenzione di distribuire la mobilità e la linea si presenta quando si hanno già certificati nell'ambiente. La riemissione tramite una CA interna è in genere abbastanza semplice, ma con i certificati pubblici di una CA pubblica, che può essere un po' più caro.
  
Se questo è quello che si sta guardando e se si hanno molti domini SIP (che renderebbe più costoso l'aggiunta di SANS), è possibile configurare il proxy inverso per l'uso di HTTP per la richiesta di servizio di individuazione automatica iniziale, invece di usare HTTPS (che è l'impostazione predefinita configurazione). L'argomento Pianificazione per la mobilità contiene altre informazioni.
  
Requisiti del pool di Director e dei certificati del pool Front end:
  
|**Descrizione**|**Voce SAN**|
|:-----|:-----|
|URL del servizio di individuazione automatica interno  <br/> |SAN = LyncdiscoverInternal. \<SipDomain\>  <br/> |
|URL del servizio di individuazione automatica esterna  <br/> |SAN = lyncdiscover. \<SipDomain\>  <br/> |
   
In alternativa, è possibile usare SAN\*=. \<SipDomain\>
  
Requisiti del certificato di proxy inverso (public CA):
  
|**Descrizione**|**Voce SAN**|
|:-----|:-----|
|URL del servizio di individuazione automatica esterna  <br/> |SAN = lyncdiscover. \<SipDomain\>  <br/> |
   
Questa SAN deve essere assegnata al certificato assegnato al listener SSL nel proxy inverso.
  
> [!NOTE]
> Il listener del proxy inverso avrà SANs per gli URL dei servizi Web esterni. Alcuni esempi sarebbero SAN = skypewebextpool01. contoso. com e dirwebexternal.contoso.com, se è stato distribuito il Director (facoltativo). 
  
## <a name="file-share"></a>Condivisione file
<a name="Fileshare"> </a>

Skype for Business Server 2015 è in grado di usare la stessa condivisione di file per tutti gli archivi di file. È necessario tener presente quanto segue:
  
- Una condivisione file deve essere inserita nell'archiviazione (DAS) Direct Attached Storage Network (SAN), che include il file System distribuito (DFS), nonché una matrice ridondante di dischi indipendenti (RAID) per gli archivi di file. Per altre informazioni su DFS per Windows Server 2012, vedere [Questa pagina DFS](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- È consigliabile un cluster condiviso per la condivisione file. Se si usa uno, è consigliabile eseguire il cluster Windows Server 2012 o Windows Server 2012 R2. Anche Windows Server 2008 R2 è accettabile. Perché le finestre più recenti? Le versioni precedenti potrebbero non avere le autorizzazioni appropriate per abilitare tutte le funzionalità. Puoi usare l'amministratore del cluster per creare le condivisioni di file e questo [come creare condivisioni di file in un](https://support.microsoft.com/en-us/help/224967/how-to-create-file-shares-on-a-cluster) articolo di cluster ti aiuterà in questi dettagli.
    
> [!CAUTION] 
> Dovresti sapere che l'uso di Network Attached Storage (NAS) come condivisione file non è supportato, quindi usa una delle opzioni elencate sopra. 
  

