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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: 'Riepilogo: configurare i requisiti non server per Skype for Business Server 2015. Prima di eseguire la distribuzione, è necessario configurare diversi elementi, tra cui Active Directory, DNS, certificati e condivisivi file.'
ms.openlocfilehash: dfaf19ac3c34a13055cd496ad25d02cd4b89c783
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601331"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Requisiti ambientali per Skype for Business Server 2015
 
**Riepilogo:** Configurare i requisiti non server per Skype for Business Server 2015. Prima di eseguire la distribuzione, è necessario configurare diversi elementi, tra cui Active Directory, DNS, certificati e condivisivi file.
  
Qual è un requisito ambientale per Skype for Business Server 2015? Bene, abbiamo inserito tutto ciò che non è direttamente correlato al server in questo argomento, quindi non è necessario fare tanto clic. Se si cercano i prerequisiti del server, è possibile consultare i requisiti del server [](../../plan-your-deployment/network-requirements/network-requirements.md) per Skype for Business Server [2015.](server-requirements.md) La pianificazione delle reti è inoltre documentata separatamente. In caso contrario, questo è il contenuto di questo articolo:
  
- [Active Directory](environmental-requirements.md#AD)
  
- [Domain Name System (DNS)](environmental-requirements.md#DNS)
  
- [Certificati](environmental-requirements.md#Certs)
  
- [Condivisione file](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Sebbene molti dati di configurazione per server e servizi siano archiviati nell'archivio di gestione centrale di Skype for Business Server 2015, esistono alcuni elementi ancora archiviati in Active Directory:
  
|**Objets Active Directory**|**Tipi di oggetto**|
|:-----|:-----|
|Estensioni dello schema  <br/> |Estensioni degli oggetti utente  <br/> |
||Estensioni per Lync Server 2013 e Lync Server 2010, per mantenere la compatibilità con le versioni precedenti supportate.  <br/> |
|Dati  <br/> |URI SIP utente e altre impostazioni utente  <br/> |
||Oggetti contatto per le applicazioni ,ad esempio l'applicazione Response Group e il applicazione Operatore conferenza).  <br/> |
||Dati pubblicati per garantire la compatibilità con le versioni precedenti.  <br/> |
||Un punto di controllo del servizio (SCP) per l'archivio di gestione centrale.  <br/> |
||Account di autenticazione Kerberos (un oggetto computer facoltativo).  <br/> |
   
### <a name="os-for-domain-controllers"></a>Sistema operativo per controller di dominio

Quindi, quale sistema operativo controller di dominio può essere utilizzato? Abbiamo l'elenco seguente:

- Windows Server 2019 (è necessario Skype for Business Server 2015 aggiornamento cumulativo 5 o versione successiva)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
Ora, il livello di funzionalità del dominio di qualsiasi dominio in cui si distribuisce Skype for Business Server 2015 e il livello di funzionalità della foresta di qualsiasi foresta Skype for Business Server cui si distribuisce Skype for Business Server 2015, devono essere uno dei seguenti:

- Windows Server 2019 (è necessario Skype for Business Server 2015 aggiornamento cumulativo 5 o versione successiva)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
È possibile disporre di controller di dominio di sola lettura in questi ambienti? Certo, purché ci siano anche controller di dominio scrivibili disponibili nello stesso sito del Skype for Business Server.
  
A questo punto, è importante sapere che Skype for Business Server 2015 non supporta i domini con etichetta singola. Quali? Se si dispone di un dominio radice denominato contoso.local, andrà bene. Se si dispone di un dominio radice denominato localmente, non funzionerà e di conseguenza non è supportato. Ulteriori informazioni sono state scritte [in questo articolo della Knowledge Base.](https://support.microsoft.com/kb/300684/en-us)
  
Skype for Business Server 2015 non supporta anche la ridenominazione dei domini. Se è necessario eseguire questa operazione, è necessario disinstallare Skype for Business Server 2015, eseguire la ridenominazione del dominio e quindi reinstallare Skype for Business Server 2015.
  
Infine, potresti avere a che fare con un dominio con un ambiente di Servizi di dominio Active Directory bloccato e questo è tutto a posto. Abbiamo altre informazioni su come distribuire Skype for Business Server 2015 in questo tipo di ambiente nella documentazione sulla distribuzione.
  
### <a name="ad-topologies"></a>Topologie AD

Skype for Business Server topologie supportate dalla versione 2015 sono:
  
- Foresta singola con singolo dominio
    
- Foresta singola con albero singolo e più domini
    
- Foresta singola con più alberi e spazi dei nomi disgiunti
    
- Più foreste in una topologia di foreste centralizzate
    
- Più foreste in una topologia di foresta di risorse
    
- Più foreste in una topologia Skype for Business di risorse con Exchange Online
    
- Più foreste in una topologia a foresta di risorse con Skype for Business Online e Azure Active Directory Connessione
    
Sono presenti diagrammi e descrizioni che consentono di determinare quale topologia è presente nell'ambiente o cosa potrebbe essere necessario configurare prima di installare Skype for Business Server 2015. Per mantenere la semplicità, è inclusa anche una chiave:
  
![L'elemento è una chiave per le icone utilizzate Skype for Business diagrammi di topologia](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Foresta singola con singolo dominio

![Diagramma della foresta singola di Active Directory con un singolo dominio](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Non è più facile, si tratta di una foresta a dominio singolo, si tratta di una topologia comune.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Foresta singola con albero singolo e più domini

![Diagramma di una foresta singola, di un singolo albero e di domini mutiple](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Questo diagramma mostra una singola foresta, ma ha anche uno o più domini figlio (sono presenti tre in questo esempio specifico). Pertanto, il dominio in cui vengono creati gli utenti potrebbe essere diverso da quello in cui Skype for Business Server 2015 viene distribuito. Perché preoccuparsi di questo? È importante ricordare che quando si distribuisce un pool Front End Skype for Business Server, tutti i server del pool devono essere in un singolo dominio. È possibile eseguire l'amministrazione tra domini Skype for Business Server il supporto di Windows gruppi di amministratori universali.
  
Tornando al diagramma precedente, è possibile vedere che gli utenti di un dominio sono in grado di accedere Skype for Business Server pool dallo stesso dominio o da domini diversi, anche se tali utenti sono in un dominio figlio.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Foresta singola con più alberi e spazi dei nomi disgiunti

![Diagramma di una singola foresta, più alberi e spazi dei nomi disgiunti](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
È possibile che sia presente una topologia simile a questo diagramma, in cui è presente una foresta, ma all'interno di tale foresta sono presenti più domini, con spazi dei nomi AD separati. In questo caso, questo diagramma è una buona illustrazione, in quanto sono presenti utenti in tre domini diversi che accedono Skype for Business Server 2015. Linee solide indicano che stanno accedendo a un pool di Skype for Business Server nel proprio dominio, mentre una linea tratteggiata indica che stanno andando a un pool in un albero diverso del tutto.
  
Come si può vedere, gli utenti nello stesso dominio, nello stesso albero o anche in un albero diverso sono in grado di accedere correttamente ai pool.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Più foreste in una topologia di foreste centralizzate

![Più foreste in un diagramma della topologia a foresta centrale](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 supporta più foreste configurate in una topologia a foresta centrale. Se non si è certi di avere questo tipo di dati, la foresta centrale della topologia utilizza gli oggetti in essa contenuti per rappresentare gli utenti nelle altre foreste e ospita gli account utente per tutti gli utenti nella foresta.
  
Funzionamento. Un prodotto di sincronizzazione della directory (ad esempio Forefront Identity Manager o FIM) gestisce gli account utente dell'organizzazione per tutta la durata della loro esistenza. Quando un account viene creato o eliminato da una foresta, tale modifica viene sincronizzata fino al contatto corrispondente nella foresta centrale.
  
Chiaramente, se l'infrastruttura ad Active Directory sta passando a questa topologia potrebbe non essere facile, ma se si è già presenti o si sta ancora pianificando l'infrastruttura della foresta, questa può essere una buona scelta. È possibile centralizzare la distribuzione di Skype for Business Server 2015 in una singola foresta, mentre gli utenti possono cercare, comunicare e visualizzare la presenza di altri utenti in qualsiasi foresta. Tutti gli aggiornamenti dei contatti utente vengono gestiti automaticamente con il software di sincronizzazione.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Più foreste in una topologia Skype for Business di risorse locali
<a name="BKMK_multipleforestopology"> </a>

![Più foreste in un diagramma della topologia a foresta di risorse](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
È supportata anche una topologia di foresta di risorse. è qui che una foresta è dedicata all'esecuzione delle applicazioni server, come Microsoft Exchange Server e Skype for Business Server 2015. Questa foresta di risorse ospita anche una rappresentazione sincronizzata degli oggetti utente attivi, ma nessun account utente abilitato all'accesso. La foresta di risorse è quindi un ambiente di servizi condivisi per altre foreste in cui risiedono gli oggetti utente e hanno una relazione di trust a livello di foresta con la foresta di risorse.
  
Tenere presente Exchange Server possono essere distribuiti nella stessa foresta di risorse Skype for Business Server o in una foresta diversa.
  
Per distribuire Skype for Business Server 2015 in questo tipo di topologia, è necessario creare un oggetto utente disabilitato nella foresta di risorse per ogni account utente nelle foreste utente (se Microsoft Exchange Server è già presente nell'ambiente, questa operazione potrebbe essere eseguita automaticamente). Sarà quindi necessario uno strumento di sincronizzazione della directory (ad esempio Forefront Identity Manager o FIM) per gestire gli account utente attraverso il ciclo di vita.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Più foreste in una topologia Skype for Business di risorse con Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Questa topologia è simile a quella descritta in Più foreste in una Skype for Business [di foresta di risorse.](environmental-requirements.md#BKMK_multipleforestopology)
  
In questa topologia sono presenti una o più foreste utente e Skype for Business Server in una foresta di risorse dedicata. Exchange Server possono essere distribuiti in locale nella stessa foresta di risorse o in una foresta diversa e configurati per la distribuzione ibrida con Exchange Online oppure i servizi di posta elettronica possono essere forniti esclusivamente da Exchange Online per gli account locali. Non è disponibile alcun diagramma per questa topologia.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Più foreste in una topologia a foresta di risorse con Skype for Business Online e Azure Active Directory Connessione
<a name="BKMK_multipleforestopology"> </a>

![Mostra due foreste di Active Directory, una foresta utente e una foresta di risorse. Le due foreste hanno una relazione di trust. Vengono sincronizzati con Microsoft 365 o Office 365 usando Azure AD Connessione. Tutti gli utenti sono abilitati per Skype for Business tramite Microsoft 365 o Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Con questo scenario, sono presenti più foreste in locale, con una topologia a foresta di risorse. Esiste una relazione di trust completo tra le foreste di Active Directory. Lo Azure Active Directory Connessione viene utilizzato per sincronizzare gli account tra le foreste utente locali e Microsoft 365 o Office 365.
  
 L'organizzazione ha anche Microsoft 365 o Office 365 e usa [Azure Active Directory Connessione](/previous-versions/azure/azure-services/dn832695(v=azure.100)) per sincronizzare i propri account locali con Microsoft 365 o Office 365. Gli utenti abilitati per Skype for Business sono abilitati tramite Microsoft 365 o Office 365 e Skype for Business Online. Skype for Business Server non viene distribuito in locale.
  
L'autenticazione Single #A0 è fornita da una farm di Active Directory Federation Services che si trova nella foresta utente.
  
In questo scenario, è supportato per distribuire Exchange locale, Exchange Online, una soluzione Exchange ibrida o per non distribuire Exchange affatto. Il diagramma mostra solo Exchange locale, ma anche le altre soluzioni Exchange sono completamente supportate.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Più foreste in una topologia a foresta di risorse con Skype for Business
<a name="BKMK_multipleforestopology"> </a>

In questo scenario, sono presenti una o più foreste utente locali e Skype for Business viene distribuito in una foresta di risorse dedicata ed è configurato per la modalità ibrida con Skype for Business Online. Exchange Server possono essere distribuiti in locale nella stessa foresta di risorse o in una foresta diversa e possono essere configurati per la distribuzione ibrida con Exchange Online. In alternativa, i servizi di posta elettronica possono essere forniti Exchange Online per gli account locali.
  
Per ulteriori informazioni, vedere [Configure a multi-forest environment for hybrid Skype for Business](../../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Skype for Business Server 2015 richiede DNS, per i motivi seguenti:
  
- DNS consente Skype for Business Server 2015 di individuare server o pool interni, consentendo comunicazioni da server a server.
    
- DNS consente ai computer client di individuare il pool Front End o edizione Standard server utilizzato per le transazioni SIP.
    
- Associa URL semplici per conferenze ai server che ospitano tali conferenze.
    
- DNS consente agli utenti esterni e ai computer client di connettersi ai server perimetrali o al proxy inverso HTTP per la messaggistica istantanea o le conferenze.
    
- Consente ai dispositivi per comunicazioni unificate che non hanno effettuato l'accesso di individuare il pool Front End o il server edizione Standard che esegue il servizio Web Aggiornamento dispositivi per ottenere aggiornamenti e inviare log.
    
- L'utilizzo di DNS consente ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni del dispositivo.
    
- E viene usato nel bilanciamento del carico DNS.
    
È importante notare che Skype for Business Server 2015 non supporta i nomi di dominio internazionalizzati (IDN).
  
Ed è estremamente importante ricordare che qualsiasi nome in DNS sia identico al nome del computer configurato su qualsiasi server utilizzato da Skype for Business Server 2015. In particolare, non è possibile avere nomi brevi nell'ambiente e devono disporre di FQDN per Generatore di topologie.
  
Ciò sembra logico per qualsiasi computer già aggiunto a un dominio, ma se si dispone di un server perimetrale che non fa parte del dominio, potrebbe avere un nome breve predefinito senza suffisso di dominio. Assicurarsi che non sia così, in DNS o nel server perimetrale o in qualsiasi server o pool Skype for Business Server 2015, a tale riguardo.
  
E sicuramente non usare caratteri Unicode o caratteri di sottolineatura. I caratteri standard (che sono A-Z, a-z, 0-9 e trattini) sono quelli che saranno supportati da DNS esterno e autorità di certificazione pubbliche (sarà necessario assegnare NOMI FQDN al nome di dominio completo nel certificato, non dimenticare), in modo da risparmiare un sacco di pena se si assegna questo nome in mente.
  
Per ulteriori informazioni sui requisiti DNS per rete, vedere la [sezione Networking](../../plan-your-deployment/network-requirements/network-requirements.md) della documentazione relativa alla pianificazione.
  
## <a name="certificates"></a>Certificati
<a name="Certs"> </a>

Una delle operazioni più importanti che è possibile eseguire prima della distribuzione è assicurarsi di disporre dei certificati in ordine. Skype for Business Server 2015 richiede un'infrastruttura a chiave pubblica (PKI) per le connessioni TLS (Transport Layer Security) e MTLS (Mutual Transport Layer Security). Fondamentalmente, per comunicare in modo sicuro in modo standardizzato, Skype for Business Server i certificati emessi dalle autorità di certificazione (CA).
  
Ecco alcuni degli aspetti che Skype for Business Server 2015 usa i certificati per:
  
- Connessioni TLS tra client e server
    
- Connessioni MTLS tra server
    
- Federazione con individuazione DNS automatica dei partner
    
- Accesso utente remoto per la messaggistica istantanea
    
- Accesso degli utenti esterni alle sessioni audio/video, alla condivisione di applicazioni e alle conferenze
    
- Parlare con applicazioni Web e Outlook Web Access (OWA)
    
Quindi la pianificazione dei certificati è un must. Esamini ora un elenco di alcuni aspetti da tenere presenti quando si richiedono certificati:
  
- Tutti i certificati del server devono supportare l'autorizzazione server (utilizzo chiavi avanzato del server).
    
- Tutti i certificati del server devono contenere un punto di distribuzione CRL (CDP).
    
- Tutti i certificati devono essere firmati utilizzando un algoritmo di firma supportato dal sistema operativo. Skype for Business Server 2015 supporta la famiglia di prodotti SHA-1 e SHA-2 di dimensioni del digest (224, 256, 384 e 512 bit) e soddisfa o supera i requisiti del sistema operativo.
    
- La registrazione automatica è supportata per i server interni che eseguono Skype for Business Server 2015.
    
- La registrazione automatica non è supportata per i server perimetrali Skype for Business Server 2015.
    
- Quando si invia una richiesta di certificato Web a un'autorità di certificazione (CA) di Windows Server 2003, è necessario inviarla da un computer che esegue Windows Server 2003 con SP2 oppure Windows XP.
    
> [!NOTE]
> Sebbene KB922706 supporti la risoluzione dei problemi relativi alla registrazione dei certificati Web in una registrazione Web di Servizi certificati di Windows Server 2003, non consente di utilizzare Windows Server 2008, Windows Vista o Windows 7 per richiedere un certificato a una CA di Windows Server 2003. 
  
> [!NOTE]
> L'utilizzo dell'algoritmo di firma RSASSA-PSS non è supportato e può causare errori in caso di problemi di accesso e inoltro di chiamata, tra gli altri problemi. 

> [!NOTE]
> Skype for Business Server 2015 non supporta i certificati CNG.
  
- Sono supportate le lunghezze delle chiavi di crittografia 1024, 2048 e 4096. Sono consigliate lunghezze di chiave pari o superiori a 2048.
    
- L'algoritmo predefinito del digest, o firma hash, è RSA. Sono supportati ECDH_P256, ECDH_P384 e ECDH_P521 algoritmi.
    
Questo è molto da pensare, e sicuramente, c'è una varietà di livelli di comfort con la richiesta di certificati da un'autorità di certificazione. Di seguito verranno fornite ulteriori indicazioni per rendere la pianificazione il più indolore possibile.
  
### <a name="certificates-for-your-internal-servers"></a>Certificati per i server interni

Saranno necessari certificati per la maggior parte dei server interni e molto probabilmente li si otterrà da un'autorità di certificazione interna (che si trova nel dominio). Se lo si desidera, è possibile richiedere questi certificati a un'autorità di certificazione esterna (una che si trova su Internet). Se ti stai chiedendo a quale autorità di certificazione pubblica dovresti andare, puoi consultare l'elenco dei partner dei certificati [per comunicazioni unificate.](../../../SfbPartnerCertification/certification/services-ssl.md)
  
Saranno inoltre necessari certificati quando Skype for Business Server 2015 comunica con altre applicazioni e server, ad esempio Microsoft Exchange Server. Questo sarà, ovviamente, necessario essere un certificato che queste altre app e server possono usare in modo supportato. Skype for Business Server 2015 e altri prodotti Microsoft supportano il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server. If you're interested in this, we have an additional planning article for OAuth and Skype for Business Server 2015.
  
Skype for Business Server 2015 include anche il supporto per (senza richiedere) certificati firmati utilizzando la funzione hash crittografica SHA-256. Per supportare l'accesso esterno tramite SHA-256, il certificato esterno deve essere emesso da un'autorità di certificazione pubblica utilizzando SHA-256.
  
Per cercare di mantenere le cose semplici, i requisiti dei certificati per i server edizione Standard, i pool Front End e altri ruoli sono stati inseriti nelle tabelle seguenti, con il contoso.com fittizio utilizzato per esempi (probabilmente si sta usando qualcos'altro per l'ambiente). Si tratta di tutti i certificati server Web standard, con chiavi private non esportabili. Alcuni aspetti aggiuntivi da notare:
  
- L'utilizzo chiavi avanzato del server (EKU) viene configurato automaticamente quando si utilizza la procedura guidata per la richiesta di certificati.
    
- Ogni nome descrittivo del certificato deve essere univoco nell'archivio computer.
    
- In base ai nomi di esempio riportati di seguito, se è stato configurato sipinternal.contoso.com o sipexternal.contoso.com nel DNS, questi devono essere aggiunti al nome alternativo soggetto (SAN) del certificato.
    
Certificati per edizione Standard server:
  
|**Certificato**|**Nome soggetto/Nome comune**|**Nome alternativo soggetto**|**Esempio**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Impostazione predefinita  <br/> |FQDN del pool  <br/> |FQDN del pool e FQDN del server  <br/> Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |Nel caso del server Standard Edition, l'FQDN del server corrisponde all'FQDN del pool.  <br/> La procedura guidata rileva eventuali domini SIP specificati durante l'installazione e li aggiunge automaticamente come nomi alternativi soggetto.  <br/> È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.  <br/> |
|Interno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che corrisponde all'FQDN del server)  <br/> E  <br/> • Soddisfare GLI URL semplici  <br/> • URL semplice per l'accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |Non è possibile sostituire l'FQDN Web interno in Generatore di topologie.  <br/> Se si dispone di più URL semplici Meet, è necessario includerli tutti come SAN.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
|Esterno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • URL semplice per l'accesso esterno  <br/> • Soddisfare GLI URL semplici per dominio SIP  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Se si dispone di più URL semplici Meet, è necessario includerli tutti come nomi alternativi soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
   
Certificati per i Front End Server in edizione Enterprise pool Front End:
  
|**Certificato**|**Nome soggetto/Nome comune**|**Nome alternativo soggetto**|**Esempio**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Impostazione predefinita  <br/> |FQDN del pool  <br/> |FQDN del pool e FQDN del server  <br/> Se sono presenti più domini SIP ed è stata abilitata la configurazione automatica dei client, la Configurazione guidata certificati rileva e aggiunge l'FQDN di ogni dominio SIP supportato.  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS (Domain Name System) esatta nei criteri di gruppo, saranno inoltre necessarie voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Se il pool rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |La procedura guidata rileva i domini SIP specificati durante la configurazione e li aggiunge automaticamente al nome alternativo del soggetto.  <br/> È inoltre possibile utilizzare questo certificato per l'autenticazione da server a server.  <br/> |
|Interno Web  <br/> |FQDN del pool  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che NON corrisponde all'FQDN del server)  <br/> • FQDN server  <br/> • FQDN Skype for Business pool  <br/> E  <br/> • Soddisfare GLI URL semplici  <br/> • URL semplice per l'accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Se si dispone di più URL semplici Meet, è necessario includerli tutti come nomi alternativi soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
|Esterno Web  <br/> |FQDN del pool  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • URL semplice per l'accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Se si dispone di più URL semplici Meet, è necessario includerli tutti come nomi alternativi soggetto.  <br/> Le voci con caratteri jolly sono supportate per le voci di URL semplici.  <br/> |
   
Certificati per il Director:
  
|**Certificato**|**Nome soggetto/Nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Impostazione predefinita  <br/> |Pool Director  <br/> |FQDN del Director, FQDN del pool di server Director.  <br/> Se questo pool è il server di accesso automatico per i client e la corrispondenza DNS rigida è necessaria nei Criteri di gruppo, sono necessarie anche voci per sip.sipdomain (per ogni dominio SIP di cui si dispone).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Se il pool di server Director rappresenta il server di accesso automatico per i client ed è richiesta la corrispondenza DNS esatta nei criteri di gruppo, sarà inoltre necessario utilizzare SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
|Interno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web interno (che corrisponde all'FQDN del server)  <br/> • FQDN server  <br/> • FQDN Skype for Business pool  <br/> E  <br/> • Soddisfare GLI URL semplici  <br/> • URL semplice per l'accesso esterno  <br/> • URL semplice amministratore  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Esterno Web  <br/> |FQDN del server  <br/> |Ognuno dei seguenti:  <br/> • FQDN Web esterno  <br/> E  <br/> • Soddisfare GLI URL semplici per dominio SIP  <br/> • URL semplice per l'accesso esterno  <br/> OPPURE  <br/> • Una voce con caratteri jolly per gli URL semplici  <br/> |L'FQDN Web esterno del Director deve essere diverso dal pool Front End o dal Front End Server.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Nel caso di un certificato con caratteri jolly:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
Certificati per Mediation Server autonomo:
  
|**Certificato**|**Nome soggetto/Nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Impostazione predefinita  <br/> |FQDN del pool  <br/> |FQDN del pool  <br/> FQDN del server membro del pool  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Certificati per Survivable Branch Appliance:
  
|**Certificato**|**Nome soggetto/Nome comune**|**Nome alternativo soggetto**|**Esempio**|
|:-----|:-----|:-----|:-----|
|Impostazione predefinita  <br/> |FQDN del dispositivo  <br/> |SIP.\<sipdomain\> (è necessaria una sola voce per ogni dominio SIP)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>Certificati per il server Chat persistente

Quando si installa il server Chat persistente, sarà necessario un certificato emesso dalla stessa AUTORITÀ di certificazione utilizzata dai server interni di Skype for Business Server 2015. Questa operazione deve essere eseguita per ogni server che esegue Servizi Web Chat persistente per file Upload/Download. È consigliabile disporre dei certificati necessari prima di avviare l'installazione di Persistent Chat e, se l'autorità di certificazione è esterna, ancora di più (l'emissione di queste operazioni può richiedere un po' di tempo).
  
### <a name="certificates-for-external-user-access-edge"></a>Certificati per l'accesso degli utenti esterni (Edge)

Skype for Business Server 2015 supporta l'utilizzo di  un singolo certificato pubblico per le interfacce esterne di Access e Web Conferencing Edge, oltre al servizio di autenticazione A/V, fornito tramite i server perimetrali. L'interfaccia interna di Edge in genere userà un certificato privato emesso dall'autorità di certificazione interna, ma se si preferisce, è possibile utilizzare anche un certificato pubblico per questo, se è di un'autorità di certificazione attendibile.
  
Anche il proxy inverso utilizzerà un certificato pubblico e crittograferà la comunicazione tra il componente e i client e il componente ai server interni tramite HTTP (o, più precisamente, TLS su HTTP).
  
### <a name="certificates-for-mobility"></a>Certificati per dispositivi mobili

Se si sta distribuendo dispositivi mobili e si sta supportando l'individuazione automatica per i client mobili, sarà necessario includere nei certificati alcune voci aggiuntive del nome soggetto alternativo per supportare le connessioni protette dai client mobili.
  
Quali certificati? I nomi SAN per l'individuazione automatica dei certificati sono necessari qui:
  
- Pool Director
    
- Pool Front End
    
- Proxy inverso
    
Di seguito verranno elencate le specifiche in ogni tabella.
  
Questo è il punto in cui un po' di pianificazione preliminare è buona, ma a volte è stato distribuito Skype for Business Server 2015 senza l'intenzione di distribuire dispositivi mobili e ciò risulta in linea quando si dispone già di certificati nell'ambiente. La loro riemissione tramite un'autorità di certificazione interna è in genere piuttosto semplice, ma con i certificati pubblici di un'autorità di certificazione pubblica, questo può essere un po' più costoso.
  
Se è quello che si sta esaminando e se si dispone di molti domini SIP (il che renderebbe più costosa l'aggiunta di SANS), è possibile configurare il proxy inverso per l'utilizzo di HTTP per la richiesta iniziale del servizio di individuazione automatica, invece di usare HTTPS (che è la configurazione predefinita). L'argomento Pianificazione per dispositivi mobili contiene altre info su questo argomento.
  
Requisiti del pool di server Director e dei certificati del pool Front End:
  
|**Descrizione**|**Voce SAN**|
|:-----|:-----|
|URL del servizio di individuazione automatica interno  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|URL del servizio di individuazione automatica esterno  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
In alternativa, è possibile utilizzare SAN= \* .\<sipdomain\>
  
Requisiti del certificato proxy inverso (CA pubblica):
  
|**Descrizione**|**Voce SAN**|
|:-----|:-----|
|URL del servizio di individuazione automatica esterno  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Questa san deve essere assegnata al certificato assegnato al listener SSL nel proxy inverso.
  
> [!NOTE]
> Nel listener del proxy inverso saranno disponibili sann per gli URL dei servizi Web esterni. Alcuni esempi sono SAN=skypewebextpool01.contoso.com e dirwebexternal.contoso.com, se è stato distribuito il Director( facoltativo). 
  
## <a name="file-share"></a>Condivisione file
<a name="Fileshare"> </a>

Skype for Business Server 2015 è in grado di usare la stessa condivisione file per tutto l'archiviazione di file. È necessario tenere presente quanto segue:
  
- Una condivisione file deve essere in uno spazio di archiviazione collegato diretto (DAS) o in una rete di archiviazione (SAN) e questo include DFS (Distributed File System) e una matrice ridondante di dischi indipendenti (RAID) per gli archivi file. Per ulteriori informazioni su DFS per Windows Server 2012, vedere [questa pagina DFS.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))
    
- È consigliabile un cluster condiviso per la condivisione file. Se si usa uno, è consigliabile eseguire il cluster Windows Server 2012 o Windows Server 2012 R2. Windows Anche Server 2008 R2 è accettabile. Perché l'ultima Windows? Le versioni precedenti potrebbero non disporre delle autorizzazioni appropriate per abilitare tutte le funzionalità. È possibile utilizzare Amministrazione cluster per creare le condivisioni file e questo articolo Come creare condivisioni file in un [cluster](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) consente di ottenere informazioni dettagliate.
    
> [!CAUTION] 
> È necessario sapere che l'utilizzo di nas (Network Attached Storage) come condivisione file non è supportato, quindi usa una delle opzioni elencate in precedenza. 
