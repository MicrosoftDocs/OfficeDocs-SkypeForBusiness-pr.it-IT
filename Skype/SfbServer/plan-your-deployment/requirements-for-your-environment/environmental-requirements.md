---
title: Requisiti ambientali per Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Riepilogo: configurare i requisiti non server per Skype for Business Server 2015. Prima di eseguire la distribuzione, è necessario configurare diversi elementi, tra cui Active Directory, DNS, certificati e condivisione file.'
ms.openlocfilehash: 83e01cec8bea5a45debadcf8ef9167ddd53b6a46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832136"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisiti ambientali per Skype for Business Server 2015
 
**Riepilogo:** Configurare i requisiti non server per Skype for Business Server 2015. Prima di eseguire la distribuzione, è necessario configurare diversi elementi, tra cui Active Directory, DNS, certificati e condivisione file.
  
Qual è un requisito ambientale per Skype for Business Server 2015? Bene, abbiamo inserito tutto ciò che non è direttamente correlato al server in questo argomento, quindi non è necessario fare tanto clic. If you're looking for Server Prerequisites, you can check out the [Server requirements for Skype for Business Server 2015](server-requirements.md) doc. Networking [Planning](../../plan-your-deployment/network-requirements/network-requirements.md) is also documented separately. In caso contrario, questo è il contenuto di questo articolo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [DNS (Domain Name System)](environmental-requirements.md#DNS)
  
- [Certificati](environmental-requirements.md#Certs)
  
- [Condivisione file](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Anche se molti dati di configurazione per server e servizi sono archiviati nell'archivio di gestione centrale di Skype for Business Server 2015, esistono alcuni elementi ancora archiviati in Active Directory:
  
|**Objets Active Directory**|**Tipi di oggetto**|
|:-----|:-----|
|Estensioni dello schema  <br/> |Estensioni degli oggetti utente  <br/> |
||Estensioni per Lync Server 2013 e Lync Server 2010, per mantenere la compatibilità con le versioni precedenti supportate.  <br/> |
|Dati  <br/> |URI SIP utente e altre impostazioni utente  <br/> |
||Oggetti contatto per le applicazioni ,ad esempio l'applicazione Response Group e l'applicazione Operatore Conferenza.  <br/> |
||Dati pubblicati per compatibilità con le versioni precedenti.  <br/> |
||Un punto di controllo del servizio (SCP) per l'archivio di gestione centrale.  <br/> |
||Account di autenticazione Kerberos (un oggetto computer facoltativo).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operativo per i controller di dominio

Quale sistema operativo del controller di dominio può essere utilizzato? Abbiamo l'elenco seguente:

- Windows Server 2019 (è necessario disporre dell'aggiornamento cumulativo 5 o versione successiva di Skype for Business Server 2015)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Ora, il livello di funzionalità del dominio di qualsiasi dominio in cui si distribuisce Skype for Business Server 2015 e il livello di funzionalità della foresta di qualsiasi foresta in cui si distribuisce Skype for Business Server 2015, devono essere uno dei seguenti:

- Windows Server 2019 (è necessario disporre dell'aggiornamento cumulativo 5 o versione successiva di Skype for Business Server 2015)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
È possibile disporre di controller di dominio di sola lettura in questi ambienti? Certo, purché ci siano anche controller di dominio scrivibili disponibili nello stesso sito di Skype for Business Server.
  
Ora, è importante sapere che Skype for Business Server 2015 non supporta i domini con etichetta singola. Cosa sono? Se si dispone di un dominio radice denominato contoso.local, andrà bene. Se si dispone di un dominio radice denominato solo locale, non funzionerà e di conseguenza non è supportato. Ulteriori informazioni sono state scritte [in questo articolo della Knowledge Base.](https://support.microsoft.com/kb/300684/en-us)
  
Anche Skype for Business Server 2015 non supporta la ridenominazione dei domini. If you've really got to do that, then you'll need to uninstall Skype for Business Server 2015, do the domain rename, and then reinstall Skype for Business Server 2015.
  
Infine, potresti avere a che fare con un dominio con un ambiente di Servizi di dominio Active Directory bloccato e non c'è problema. Abbiamo altre informazioni su come distribuire Skype for Business Server 2015 in questo tipo di ambiente nella documentazione sulla distribuzione.
  
### <a name="ad-topologies"></a>Topologie AD

Le topologie supportate di Skype for Business Server 2015 sono:
  
- Foresta singola con singolo dominio
    
- Foresta singola con albero singolo e più domini
    
- Foresta singola con più alberi e spazi dei nomi disgiunti
    
- Più foreste in una topologia di foreste centralizzate
    
- Più foreste in una topologia di foresta di risorse
    
- Più foreste in una topologia a foresta di risorse di Skype for Business con Exchange Online
    
- Più foreste in una topologia a foresta di risorse con Skype for Business online e Azure Active Directory Connect
    
Sono presenti diagrammi e descrizioni che consentono di determinare quale topologia si dispone nel proprio ambiente o cosa potrebbe essere necessario configurare prima di installare Skype for Business Server 2015. Per semplicità, è inclusa anche una chiave:
  
![La chiave per le icone utilizzate per i diagrammi di topologia di Skype for Business](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Foresta singola con singolo dominio

![Diagramma della foresta singola di Active Directory con un singolo dominio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Non è più facile, si tratta di una foresta a dominio singolo, si tratta di una topologia comune.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Foresta singola con albero singolo e più domini

![Diagramma di una foresta singola, di un singolo albero e di domini a più elementi](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Questo diagramma mostra una singola foresta, anche in questo caso, ma include anche uno o più domini figlio (sono presenti tre in questo esempio specifico). Pertanto, il dominio in cui vengono creati gli utenti potrebbe essere diverso dal dominio in cui è distribuito Skype for Business Server 2015. Perché preoccuparsi di questo? È importante ricordare che quando si distribuisce un pool Front End di Skype for Business Server, tutti i server del pool devono essere in un singolo dominio. È possibile eseguire l'amministrazione tra domini tramite il supporto di Skype for Business Server per i gruppi di amministratori universali di Windows.
  
Tornando al diagramma precedente, è possibile vedere che gli utenti di un dominio sono in grado di accedere ai pool di Skype for Business Server dallo stesso dominio o da domini diversi, anche se si tratta di un dominio figlio.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Foresta singola con più alberi e spazi dei nomi disgiunti

![Diagramma di una foresta singola, più alberi e spazi dei nomi disgiunti](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Potrebbe essere presente una topologia simile a questo diagramma, in cui si dispone di una foresta, ma all'interno di tale foresta sono presenti più domini, con spazi dei nomi AD separati. In questo caso, questo diagramma è una buona illustrazione, perché ci sono utenti in tre domini diversi che accedono a Skype for Business Server 2015. Linee solide indicano che stanno accedendo a un pool di Skype for Business Server nel proprio dominio, mentre una linea tratteggiata indica che stanno per accedere completamente a un pool in un albero diverso.
  
Come è possibile vedere, gli utenti nello stesso dominio, nello stesso albero o persino in un albero diverso sono in grado di accedere correttamente ai pool.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Più foreste in una topologia di foreste centralizzate

![Diagramma di più foreste in una topologia a foresta centrale](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 supporta più foreste configurate in una topologia a foresta centrale. Se non si è certi di disporre di tale funzionalità, la foresta centrale della topologia utilizza gli oggetti in essa contenuti per rappresentare gli utenti nelle altre foreste e ospita gli account utente per qualsiasi utente nella foresta.
  
Funzionamento. Un prodotto di sincronizzazione della directory (ad esempio Forefront Identity Manager o FIM) gestisce gli account utente dell'organizzazione per tutta la durata della loro esistenza. Quando un account viene creato o eliminato da una foresta, tale modifica viene sincronizzata fino al contatto corrispondente nella foresta centrale.
  
Chiaramente, se l'infrastruttura di Active Directory sta passando a questa topologia potrebbe non essere facile, ma se si è già presenti o si sta ancora pianificando l'infrastruttura della foresta, questa può essere una buona scelta. È possibile centralizzare la distribuzione di Skype for Business Server 2015 in una singola foresta, mentre gli utenti possono cercare, comunicare e visualizzare la presenza di altri utenti in qualsiasi foresta. Tutti gli aggiornamenti dei contatti utente vengono gestiti automaticamente con il software di sincronizzazione.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Più foreste in una topologia a foresta di risorse di Skype for Business
<a name="BKMK_multipleforestopology"> </a>

![Diagramma di più foreste in una topologia a foresta di risorse](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
È supportata anche una topologia di foresta di risorse. è qui che una foresta è dedicata all'esecuzione delle applicazioni server, come Microsoft Exchange Server e Skype for Business Server 2015. Questa foresta di risorse ospita anche una rappresentazione sincronizzata degli oggetti utente attivi, ma nessun account utente abilitato all'accesso. Pertanto, la foresta di risorse è un ambiente di servizi condivisi per altre foreste in cui risiedono gli oggetti utente e hanno una relazione di trust a livello di foresta con la foresta di risorse.
  
Tenere presente Exchange Server essere distribuiti nella stessa foresta di risorse di Skype for Business Server o in una foresta diversa.
  
Per distribuire Skype for Business Server 2015 in questo tipo di topologia, è necessario creare un oggetto utente disabilitato nella foresta di risorse per ogni account utente nelle foreste utente (se Microsoft Exchange Server è già presente nell'ambiente, questa operazione potrebbe essere eseguita automaticamente). Sarà quindi necessario uno strumento di sincronizzazione della directory (ad esempio Forefront Identity Manager o FIM) per gestire gli account utente durante il ciclo di vita.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Più foreste in una topologia a foresta di risorse di Skype for Business con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Questa topologia è simile a quella descritta in Più foreste in una topologia a foresta di risorse [skype for Business.](environmental-requirements.md#BKMK_multipleforestopology)
  
In questa topologia sono presenti una o più foreste utente e Skype for Business Server viene distribuito in una foresta di risorse dedicata. Exchange Server possono essere distribuiti in locale nella stessa foresta di risorse o in una foresta diversa e configurati per la distribuzione ibrida con Exchange Online oppure i servizi di posta elettronica possono essere forniti esclusivamente da Exchange Online per gli account locali. Per questa topologia non è disponibile alcun diagramma.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Più foreste in una topologia a foresta di risorse con Skype for Business online e Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Mostra due foreste di Active Directory, una foresta utente e una foresta di risorse. Le due foreste hanno una relazione di trust. Vengono sincronizzati con Microsoft 365 o Office 365 tramite Azure AD Connect. Tutti gli utenti sono abilitati per Skype for Business tramite Microsoft 365 o Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Con questo scenario, sono presenti più foreste in locale, con una topologia di foresta di risorse. Esiste una relazione di trust completo tra le foreste di Active Directory. Lo strumento Azure Active Directory Connect viene usato per sincronizzare gli account tra le foreste utente locali e Microsoft 365 o Office 365.
  
 L'organizzazione ha anche Microsoft 365 o Office 365 e usa [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) per sincronizzare i propri account locali con Microsoft 365 o Office 365. Gli utenti abilitati per Skype for Business sono abilitati tramite Microsoft 365 o Office 365 e Skype for Business online. Skype for Business Server non è distribuito in locale.
  
L'autenticazione Single #A0 viene fornita da una farm di Active Directory Federation Services che si trova nella foresta utenti.
  
In questo scenario, è supportata la distribuzione di Exchange locale, Exchange Online, una soluzione Exchange ibrida o per non distribuire affatto Exchange. Il diagramma mostra solo Exchange locale, ma anche le altre soluzioni Exchange sono completamente supportate.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Più foreste in una topologia a foresta di risorse con Skype for Business ibrido
<a name="BKMK_multipleforestopology"> </a>

In questo scenario, sono presenti una o più foreste utente locali e Skype for Business viene distribuito in una foresta di risorse dedicata ed è configurato per la modalità ibrida con Skype for Business online. Exchange Server possono essere distribuiti in locale nella stessa foresta di risorse o in una foresta diversa e possono essere configurati per la distribuzione ibrida con Exchange Online. In alternativa, i servizi di posta elettronica possono essere forniti esclusivamente da Exchange Online per gli account locali.
  
Per ulteriori informazioni, vedere [Configurare un ambiente a più foreste per Skype for Business ibrido.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)
  
## <a name="domain-name-system-dns"></a>DNS (Domain Name System)
<a name="DNS"> </a>

Skype for Business Server 2015 richiede DNS, per i motivi seguenti:
  
- DNS consente a Skype for Business Server 2015 di individuare server o pool interni, consentendo comunicazioni da server a server.
    
- DNS consente ai computer client di individuare il pool Front End o il server Standard Edition utilizzato per le transazioni SIP.
    
- Associa URL semplici per le conferenze ai server che ospitano tali conferenze.
    
- DNS consente agli utenti esterni e ai computer client di connettersi ai server perimetrali, o al proxy inverso HTTP, per la messaggistica istantanea o le conferenze.
    
- Consente ai dispositivi per comunicazioni unificate che non hanno effettuato l'accesso di individuare il pool Front End o il server Standard Edition che esegue il servizio Web Aggiornamento dispositivi per ottenere aggiornamenti e inviare registri.
    
- L'utilizzo di DNS consente ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni del dispositivo.
    
- E viene usato nel bilanciamento del carico DNS.
    
È importante notare che Skype for Business Server 2015 non supporta i nomi IDN (Internationalized Domain Names).
  
Ed è estremamente importante ricordare che qualsiasi nome in DNS è identico al nome computer configurato su qualsiasi server utilizzato da Skype for Business Server 2015. In particolare, non è possibile avere nomi brevi nell'ambiente e devono disporre di FQDN per Generatore di topologie.
  
Sembra logico per qualsiasi computer già aggiunto a un dominio, ma se si dispone di un server perimetrale che non fa parte del dominio, potrebbe avere un nome breve predefinito, senza suffisso di dominio. Assicurati che non sia così, in DNS o nel server perimetrale o in qualsiasi server o pool di Skype for Business Server 2015.
  
E sicuramente non usare caratteri Unicode o caratteri di sottolineatura. I caratteri standard (che sono A-Z, a-z, 0-9 e trattini) sono quelli che saranno supportati da DNS esterno e da autorità di certificazione pubbliche (sarà necessario assegnare FQDN al nome del servizio nel certificato, non dimenticare), quindi se si assegnano nomi di dominio completo al nome utente nel certificato, è necessario risparmiare molto.
  
Per ulteriori informazioni sui requisiti DNS per la rete, vedere la [sezione Relativa](../../plan-your-deployment/network-requirements/network-requirements.md) alla rete della documentazione relativa alla pianificazione.
  
## <a name="certificates"></a>Certificati
<a name="Certs"> </a>

Una delle operazioni più importanti che è possibile eseguire prima della distribuzione è assicurarsi di disporre dei certificati nell'ordine indicato. Skype for Business Server 2015 necessita di un'infrastruttura a chiave pubblica (PKI) per le connessioni TLS (Transport Layer Security) e MTLS (Mutual Transport Layer Security). Fondamentalmente, per comunicare in modo sicuro in modo standardizzato, Skype for Business Server usa i certificati emessi dalle autorità di certificazione (CA).
  
Ecco alcuni degli elementi che Skype for Business Server 2015 usa i certificati per:
  
- Connessioni TLS tra client e server
    
- Connessioni MTLS tra server
    
- Federazione con individuazione DNS automatica dei partner
    
- Accesso utente remoto per la messaggistica istantanea
    
- Accesso degli utenti esterni alle sessioni audio/video, alla condivisione di applicazioni e alle conferenze
    
- Parlare con applicazioni Web e Outlook Web Access (OWA)
    
Pertanto, la pianificazione dei certificati è un'operazione da eseguire. Esamini ora un elenco di alcuni aspetti da tenere presenti quando richiedi certificati:
  
- Tutti i certificati del server devono supportare l'autorizzazione server (utilizzo chiavi avanzato del server).
    
- Tutti i certificati del server devono contenere un punto di distribuzione CRL (CDP).
    
- Tutti i certificati devono essere firmati utilizzando un algoritmo di firma supportato dal sistema operativo. Skype for Business Server 2015 supporta la famiglia di prodotti SHA-1 e SHA-2 di dimensioni del digest (224, 256, 384 e 512 bit) e soddisfa o supera i requisiti del sistema operativo.
    
- La registrazione automatica è supportata per i server interni che eseguono Skype for Business Server 2015.
    
- La registrazione automatica non è supportata per i server perimetrali di Skype for Business Server 2015.
    
- Quando si invia una richiesta di certificato Web a un'autorità di certificazione (CA) di Windows Server 2003, è necessario inviarla da un computer che esegue Windows Server 2003 con SP2 oppure Windows XP.
    
> [!NOTE]
> Sebbene KB922706 supporti la risoluzione dei problemi relativi alla registrazione dei certificati Web in una registrazione Web di Servizi certificati di Windows Server 2003, non consente di utilizzare Windows Server 2008, Windows Vista o Windows 7 per richiedere un certificato a un'autorità di certificazione di Windows Server 2003. 
  
> [!NOTE]
> L'utilizzo dell'algoritmo di firma RSASSA-PSS non è supportato e può causare errori in caso di problemi di accesso e inoltro di chiamata, tra gli altri problemi. 

> [!NOTE]
> Skype for Business Server 2015 non supporta i certificati CNG.
  
- Sono supportate le lunghezze delle chiavi di crittografia 1024, 2048 e 4096. Sono consigliate lunghezze chiave pari o superiori a 2048.
    
- L'algoritmo predefinito di digest, o firma hash, è RSA. Sono supportati ECDH_P256, ECDH_P384 e ECDH_P521 di sicurezza.
    
Pertanto, è molto da pensare e, sicuramente, esiste una varietà di livelli di comfort con la richiesta di certificati da un'autorità di certificazione. Di seguito verranno fornite ulteriori indicazioni per rendere la pianificazione il più indolore possibile.
  
### <a name="certificates-for-your-internal-servers"></a>Certificati per i server interni

Saranno necessari certificati per la maggior parte dei server interni e molto probabilmente verranno scaricati da un'autorità di certificazione interna (che si trova nel dominio). Se lo si desidera, è possibile richiedere questi certificati a un'autorità di certificazione esterna (una che si trova su Internet). If you're wondering what public CA you should go to, you can check out the [Unified Communications certificate partners](/SkypeForBusiness/certification/services-ssl) list.
  
You're also going to need certificates when Skype for Business Server 2015 communicates with other applications and servers, such as Microsoft Exchange Server. Ovviamente, questo deve essere un certificato che queste altre app e server possono usare in modo supportato. Skype for Business Server 2015 e altri prodotti Microsoft supportano il protocollo Open Authorization (OAuth) per l'autenticazione e l'autorizzazione da server a server. If you're interested in this, we have an additional planning article for OAuth and Skype for Business Server 2015.
  
Skype for Business Server 2015 include anche il supporto per (senza richiedere) certificati firmati utilizzando la funzione hash crittografica SHA-256. Per supportare l'accesso esterno tramite SHA-256, il certificato esterno deve essere emesso da una CA pubblica tramite SHA-256.
  
Per cercare di mantenere le cose semplici, i requisiti dei certificati per i server Standard Edition, i pool Front End e altri ruoli sono stati inseriti nelle tabelle seguenti, con il contoso.com fittizio usato per esempi (probabilmente si sta utilizzando altro per il proprio ambiente). Si tratta di tutti certificati server Web standard, con chiavi private non esportabili. Di seguito sono riportati alcuni aspetti da tenere presente:
  
- L'utilizzo chiavi avanzato del server (EKU) viene configurato automaticamente quando si utilizza la configurazione guidata dei certificati per richiedere i certificati.
    
- Ogni nome descrittivo del certificato deve essere univoco nell'archivio computer.
    
- In base ai nomi di esempio riportati di seguito, se è stato configurato sipinternal.contoso.com o sipexternal.contoso.com nel DNS, questi devono essere aggiunti al nome alternativo del soggetto (SAN) del certificato.
    
Certificati per i server Standard Edition:
  
|**Certificato**|**Nome soggetto/Nome comune**|**Nome alternativo soggetto**|**Esempio**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |FQDN del pool  <br/> |FQDN del pool e FQDN del server  <br/> Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |Nel caso del server Standard Edition, l'FQDN del server corrisponde all'FQDN del pool.  <br/> La procedura guidata rileva eventuali domini SIP specificati durante l'installazione e li aggiunge automaticamente come nomi alternativi del soggetto.  <br/> È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.  <br/> |
|Interno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (uguale all'FQDN del server)  <br/> E  <br/> • Meet simple URLs  <br/> • URL semplice per l'accesso esterno  <br/> • URL semplice dell'amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |Non è possibile sostituire l'FQDN Web interno in Generatore di topologie.  <br/> Se si dispone di più URL semplici meet, è necessario includerli tutti come SAN.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
|Esterno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • URL semplice per l'accesso esterno  <br/> • Soddisfare GLI URL semplici per dominio SIP  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Se si dispone di più URL semplici Meet, è necessario includerli tutti come nomi alternativi del soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
   
Certificati per i Front End Server in un pool Enterprise Edition Front End:
  
|**Certificato**|**Nome soggetto/Nome comune**|**Nome alternativo soggetto**|**Esempio**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |FQDN del pool  <br/> |FQDN del pool e FQDN del server  <br/> Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.  <br/> È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.  <br/> |
|Interno Web  <br/> |FQDN del pool  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che NON corrisponde all'FQDN del server)  <br/> • FQDN server  <br/> • FQDN pool Skype for Business  <br/> E  <br/> • Meet simple URLs  <br/> • URL semplice per l'accesso esterno  <br/> • URL semplice dell'amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Se si dispone di più URL semplici Meet, è necessario includerli tutti come nomi alternativi del soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
|Esterno Web  <br/> |FQDN del pool  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • URL semplice per l'accesso esterno  <br/> • URL semplice dell'amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Se si dispone di più URL semplici Meet, è necessario includerli tutti come nomi alternativi del soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
   
Certificati per il Director:
  
|**Certificato**|**Nome soggetto/Nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |Pool Director  <br/> |FQDN del Director, FQDN del pool di server Director.  <br/> Se questo pool è il server di accesso automatico per i client ed è necessaria una corrispondenza DNS rigida nei criteri di gruppo, saranno necessarie anche voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Se il pool di server Director rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Interno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (uguale all'FQDN del server)  <br/> • FQDN server  <br/> • FQDN pool Skype for Business  <br/> E  <br/> • Meet simple URLs  <br/> • URL semplice per l'accesso esterno  <br/> • URL semplice dell'amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Esterno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • Soddisfare GLI URL semplici per dominio SIP  <br/> • URL semplice per l'accesso esterno  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |L'FQDN web esterno del Director deve essere diverso dal pool Front End o dal Front End Server.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
Certificati per Mediation Server autonomo:
  
|**Certificato**|**Nome soggetto/Nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |FQDN del pool  <br/> |FQDN del pool  <br/> FQDN del server membro del pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificati per Survivable Branch Appliance:
  
|**Certificato**|**Nome soggetto/Nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Predefiniti  <br/> |FQDN del dispositivo  <br/> |SIP.\<sipdomain\> (è necessaria una sola voce per dominio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificati per il server Chat persistente

Quando si installa il server Chat persistente, è necessario un certificato emesso dalla stessa CA utilizzata dai server interni di Skype for Business Server 2015. Questa operazione deve essere eseguita per ogni server che esegue Servizi Web Chat persistente per il caricamento/download di file. È consigliabile disporre dei certificati necessari prima di avviare l'installazione di Persistent Chat e, se l'autorità di certificazione è esterna, ancora di più (l'emissione di queste operazioni può richiedere un po' di tempo).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificati per l'accesso degli utenti esterni (Edge)

Skype for Business Server 2015 supporta  l'uso di un singolo certificato pubblico per le interfacce esterne di Access e Web Conferencing Edge, oltre al servizio di autenticazione A/V, che viene fornito tramite i server perimetrali. L'interfaccia interna perimetrale in genere utilizza un certificato privato emesso dall'autorità di certificazione interna, ma se si preferisce, è possibile utilizzare anche un certificato pubblico, se si tratta di un'autorità di certificazione attendibile.
  
Anche il proxy inverso utilizzerà un certificato pubblico e crittografa la comunicazione tra il componente e i client e il componente ai server interni tramite HTTP (o, più precisamente, TLS su HTTP).
  
### <a name="certificates-for-mobility"></a>Certificati per dispositivi mobili

Se si distribuisce la funzionalità per dispositivi mobili e si supporta l'individuazione automatica per i client mobili, sarà necessario includere nei certificati alcune voci aggiuntive del nome alternativo del soggetto per supportare le connessioni protette dai client mobili.
  
Quali certificati? I nomi SAN sono necessari per l'individuazione automatica dei certificati qui:
  
- Pool Director
    
- Pool Front End
    
- Proxy inverso
    
Le specifiche verranno elencate in ogni tabella seguente.
  
Ora, è qui che un po' di pre-pianificazione è buona, ma a volte è stato distribuito Skype for Business Server 2015 senza l'intenzione di distribuire i dispositivi mobili e ciò risulta in linea quando si dispone già di certificati nell'ambiente. La loro riemissione tramite un'autorità di certificazione interna è in genere piuttosto semplice, ma con i certificati pubblici di una CA pubblica può essere un po' più costosa.
  
Se si sta esaminando questo aspetto e se si dispone di molti domini SIP (il che renderebbe più costosa l'aggiunta di SANS), è possibile configurare il proxy inverso per l'utilizzo di HTTP per la richiesta iniziale del servizio di individuazione automatica, invece di usare HTTPS (che è la configurazione predefinita). L'argomento Pianificazione per dispositivi mobili contiene altre informazioni su questo argomento.
  
Requisiti dei certificati del pool di server Director e del pool Front End:
  
|**Descrizione**|**Voce SAN**|
|:-----|:-----|
|URL del servizio di individuazione automatica interno  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|URL del servizio di individuazione automatica esterno  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
In alternativa, è possibile utilizzare SAN= \* .\<sipdomain\>
  
Requisiti dei certificati del proxy inverso (CA pubblica):
  
|**Descrizione**|**Voce SAN**|
|:-----|:-----|
|URL del servizio di individuazione automatica esterno  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Questa sanità san deve essere assegnata al certificato assegnato al listener SSL nel proxy inverso.
  
> [!NOTE]
> Nel listener del proxy inverso saranno disponibili sans ton per gli URL dei servizi Web esterni. Alcuni esempi sono SAN=skypewebextpool01.contoso.com e dirwebexternal.contoso.com, se è stato distribuito il Director (facoltativo). 
  
## <a name="file-share"></a>Condivisione file
<a name="Fileshare"> </a>

Skype for Business Server 2015 è in grado di usare la stessa condivisione file per l'archiviazione di tutti i file. È necessario tenere presente quanto segue:
  
- Una condivisione file deve essere in uno spazio di archiviazione collegato diretto (DAS) o in una rete di archiviazione (SAN) e questo include DFS (Distributed File System) e un array ridondante di dischi indipendenti (RAID) per gli archivi file. Per altre informazioni su DFS per Windows Server 2012, consultare [questa pagina DFS.](https://technet.microsoft.com/library/jj127250.aspx)
    
- È consigliabile un cluster condiviso per la condivisione file. Se ne stai usando uno, dovresti eseguire il clustering di Windows Server 2012 o Windows Server 2012 R2. Anche Windows Server 2008 R2 è accettabile. Perché la versione più recente di Windows? Le versioni precedenti potrebbero non disporre delle autorizzazioni appropriate per abilitare tutte le funzionalità. È possibile utilizzare Amministrazione cluster per creare le condivisioni file e questo articolo sulla creazione di [condivisioni file](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) in un cluster consente di ottenere informazioni dettagliate.
    
> [!CAUTION] 
> È necessario sapere che l'uso di nas (Network Attached Storage) come condivisione file non è supportato, quindi usa una delle opzioni elencate in precedenza. 
  
