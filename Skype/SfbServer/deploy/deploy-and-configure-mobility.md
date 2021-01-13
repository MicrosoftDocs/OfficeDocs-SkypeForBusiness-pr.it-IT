---
title: Distribuire e configurare i dispositivi mobili per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: In questo articolo vengono illustrati i passaggi necessari per configurare un'installazione di Skype for Business Server esistente per l'utilizzo del servizio per dispositivi mobili, in modo da poter usufruire delle funzionalità di mobilità di Skype for Business Server.
ms.openlocfilehash: 420d34dcf1406df776e438e01007770e515c0d4a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820896"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Distribuire e configurare i dispositivi mobili per Skype for Business Server  
 
In questo articolo vengono illustrati i passaggi necessari per configurare un'installazione di Skype for Business Server esistente per l'utilizzo del servizio per dispositivi mobili, in modo da poter usufruire delle funzionalità di mobilità di Skype for Business Server.
  
Dopo aver esaminato l'articolo [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) , è necessario essere pronti a procedere con i passaggi riportati di seguito per distribuire la mobilità nell'ambiente di Skype for Business Server. I passaggi sono i seguenti (e in questa tabella è incluso un elenco delle autorizzazioni):
  
|**Fase**|**Autorizzazioni**|
|:-----|:-----|
|[Creare record DNS](deploy-and-configure-mobility.md#CreateDNSRec). <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[Modificare i certificati](deploy-and-configure-mobility.md#ModCerts) <br/> |Amministratore locale  <br/> |
|[Configurare il proxy inverso](deploy-and-configure-mobility.md#ConfigRP) <br/> |Amministratore locale  <br/> |
|[Configurare l'individuazione automatica per i dispositivi mobili con distribuzioni ibride](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[Testare la distribuzione di dispositivi mobili](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Configurare il sistema per le notifiche push](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Configurare i criteri per dispositivi mobili](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Tutte le sezioni seguenti contengono passaggi che presumono di aver letto l'argomento relativo alla pianificazione. Se qualcosa ti confonde, sentiti libero di consultare le informazioni.

> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="create-dns-records"></a>Creare record DNS
<a name="CreateDNSRec"> </a>

Potrebbe essere già presente come parte dell'ambiente di Skype for Business Server, ma è necessario creare i record seguenti per il funzionamento dell'individuazione automatica:
  
- Un record DNS interno per supportare gli utenti mobili che si connettono dall'interno della rete dell'organizzazione.
    
- Un record DNS esterno (o pubblico) per supportare gli utenti mobili che si connettono dall'esterno della rete dell'organizzazione.
    
Questi record possono essere nomi A (host) o record CNAME (non è necessario effettuare entrambe le operazioni, sono inclusi solo i passaggi per tutto ciò che segue).
  
### <a name="create-an-internal-dns-cname-record"></a>Creare un record CNAME DNS interno

1. Accedere a un server DNS della rete che sia un membro del gruppo **Domain Admins** o del gruppo **DnsAdmins** .
    
2. Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione** (potrebbe essere necessario **cercarlo** se non è disponibile nel menu Start) e quindi fare clic su **DNS** per aprire lo snap-in amministrativo DNS.
    
3. Nel riquadro sinistro della finestra della console, è necessario accedere al dominio che ospita i front end server di Skype for business e quindi espandere le **zone di ricerca diretta** .
    
4. Prendere un momento per vedere quali delle seguenti operazioni sono:
    
   - Tutti i record host A o AAAA per il front end server (standard o Enterprise) o i pool Front end.
    
   - Tutti i record host A o AAAA per un server Director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).
    
5. Dopo aver notato questo passaggio, fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **nuovo alias (CNAME)** dal menu.
    
6. Nella casella di testo **nome alias** Digitare lyncdiscoverinternal per il nome host per l'URL del servizio di individuazione automatica interno.
    
7. Nel **nome di dominio completo (FQDN per l'host di destinazione**, è necessario digitare o passare all'FQDN dei servizi Web interni per il pool Front End (o un singolo front end server o un pool di Director o un Director), identificato nel passaggio 4 sopra riportato. Quando viene immesso, fare clic su OK.
    
8. È necessario creare un nuovo record CNAME di individuazione automatica nella zona di ricerca diretta per ogni dominio SIP supportato nell'ambiente di Skype for Business Server.
    
### <a name="create-an-external-dns-cname-record"></a>Creare un record CNAME DNS esterno

1. Questi passaggi sono generici, perché non è possibile stabilire quale provider DNS pubblico è possibile utilizzare, ma è comunque necessario darvi una mano. Accedere al provider DNS pubblico con un account che sarà in grado di creare nuovi record DNS.
    
2. A questo punto, un dominio SIP dovrebbe esistere già per Skype for Business Server. Espandere la **zona di ricerca diretta** per il dominio SIP o altrimenti aprirla.
    
3. Prendere un momento per vedere quali delle seguenti operazioni sono:
    
   - Tutti i record host A o AAAA per il front end server (standard o Enterprise) o i pool Front end.
    
   - Tutti i record host A o AAAA per un server Director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).
    
4. Una volta che si dispone di tali informazioni, è possibile selezionare un'opzione per la creazione di un **nuovo alias (CNAME)**.
    
5. A questo punto, è possibile immettere un **nome alias**, è necessario immettere lyncdiscover per l'URL del servizio di individuazione automatica esterno.
    
6. Successivamente dovrebbe essere presente un'area per immettere un **nome di dominio completo per l'host di destinazione**, il nome di dominio completo del pool Front End (o un singolo front end server o un pool di Director o un Director), identificato nel passaggio 3 sopra riportato.
    
7. Potrebbe essere necessario salvare qui, o se è necessario creare altri record CNAME nella zona di ricerca diretta di ogni dominio SIP nell'ambiente di Skype for Business Server, è consigliabile farlo, ma una volta che si è pronti, salvare il proprio lavoro.
    
### <a name="create-an-internal-dns-a-record"></a>Creare un record A DNS interno

1. Accedere a un server DNS della rete che sia un membro del gruppo **Domain Admins** o del gruppo **DnsAdmins** .
    
2. Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione** (potrebbe essere necessario **cercarlo** se non è disponibile nel menu Start) e quindi fare clic su **DNS** per aprire lo snap-in amministrativo DNS.
    
3. Nel riquadro sinistro della finestra della console, è necessario accedere al dominio che ospita i front end server di Skype for business e quindi espandere le **zone di ricerca diretta** .
    
4. Prendere un momento per vedere quali delle seguenti operazioni sono:
    
   - Tutti i record host A o AAAA per il front end server (standard o Enterprise) o i pool Front end.
    
   - Tutti i record host A o AAAA per un server Director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).
    
5. Dopo aver notato questo passaggio, fare clic con il pulsante destro del mouse sul nome del dominio SIP e quindi scegliere **nuovo host (A o AAAA)** dal menu.
    
6. Nella casella di testo **nome** Digitare lyncdiscoverinternal per il nome host per l'URL del servizio di individuazione automatica interno.
    
7. Nella casella di testo **indirizzo IP** Digitare l'indirizzo IP dei servizi Web interni per il pool Front End (o un singolo server front-end o un pool di Director o un Director), identificato nel passaggio 4 sopra riportato.
    
8. Al termine, fare clic su **Aggiungi host**, quindi fare clic su **OK**.
    
9. È necessario creare un nuovo record a o AAAA di individuazione automatica nella zona di ricerca diretta per ogni dominio SIP supportato nell'ambiente di Skype for Business Server. A tale scopo, ripetere i passaggi 6-8 tutte le volte necessarie.
    
10. Al termine, fare clic su **fine**.
    
### <a name="create-an-external-dns-a-record"></a>Creare un record A DNS esterno

1. Questi passaggi sono generici, perché non è possibile stabilire quale provider DNS pubblico è possibile utilizzare, ma è comunque necessario darvi una mano. Accedere al provider DNS pubblico con un account che sarà in grado di creare nuovi record DNS.
    
2. A questo punto, un dominio SIP dovrebbe esistere già per Skype for Business Server. Espandere la **zona di ricerca diretta** per il dominio SIP o altrimenti aprirla.
    
3. Prendere un momento per vedere quali delle seguenti operazioni sono:
    
   - Tutti i record host A o AAAA per il front end server (standard o Enterprise) o i pool Front end.
    
   - Tutti i record host A o AAAA per un server Director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).
    
4. Una volta che si dispone di tali informazioni, è possibile selezionare un'opzione per la creazione di un **nuovo host a o AAAA**.
    
5. Ora si dovrebbe essere in grado di immettere un **nome**, è necessario immettere Lyncdiscover qui per l'URL del servizio di individuazione automatica esterno.
    
6. Successivamente dovrebbe essere presente un'area da immettere in un **indirizzo IP**, questo dovrà essere l'IP per il pool Front End (o un singolo server front-end o un pool di Director o un Director), individuato nel passaggio 3 precedente.
    
7. Potrebbe essere necessario salvare qui, o se è necessario creare altri record a o AAAA nella zona di ricerca diretta di ogni dominio SIP per l'ambiente di Skype for Business Server, è consigliabile farlo, ma una volta che si è pronti, salvare il proprio lavoro.
    
## <a name="modify-certificates"></a>Modificare i certificati
<a name="ModCerts"> </a>

In caso di domande sulla pianificazione dei certificati, è stato documentato l'articolo [relativo al piano per dispositivi mobili per Skype for Business Server](../plan-your-deployment/mobility.md) . Dopo aver esaminato questo articolo, verrà illustrato quanto segue:
  
- Sono necessarie nuove certificazioni?
    
- Richiedere nuovi certificati dall'autorità di certificazione (CA).
    
- Aggiornamento dei certificati sul posto con le sostituzioni tramite PowerShell.
    
- Verifica dei certificati mediante lo snap-in certificati in Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>Sono necessarie nuove certificazioni?

1. In primo luogo, potrebbe essere necessario controllare e vedere quali certificati sono sul posto e se dispongono o meno delle voci necessarie. A tale scopo, è necessario accedere al server Skype for business con un account che sia un amministratore locale. Questo account potrebbe anche dover disporre dei diritti per l'autorità di certificazione (CA) emittente, per alcuni di questi passaggi.
    
2. Aprire Skype for Business Server Management Shell (è possibile utilizzare la funzione di ricerca per trovarla se non è stata bloccata al menu Start o alla barra delle applicazioni).
    
3. Sarà essenziale sapere quali certificati sono stati assegnati prima di provare ad aggiungere un certificato aggiornato. Quindi, al comando, digitare:
    
   ```powershell
   Get-CsCertificate
   ```

4. Le informazioni del passaggio 3 saranno univoche per l'utente. È necessario esaminarlo per determinare se si dispone di un singolo certificato assegnato per più elementi o se è stato assegnato un certificato diverso per i diversi componenti che ne hanno bisogno. Il parametro **use** indica in che modo viene utilizzato un certificato e il parametro **identificazione personale** indica se si tratta dello stesso certificato o di più certificati.
    
5. Se si dispone delle voci di SAN consigliate nella sezione pianificazione, si è a posto. In caso contrario, è necessario richiedere un nuovo certificato o più certificati (a seconda della configurazione) dall'autorità di certificazione.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Richiedere un nuovo certificato o i certificati dall'autorità di certificazione (CA)

1. Dopo aver verificato la verifica delle voci di SAN, è possibile sapere di disporre di un **singolo certificato** (dopo aver eseguito la procedura descritta in alto) e di aver imparato che non si dispone di tutte le voci necessarie. È necessario apportare una nuova richiesta di certificato all'autorità di certificazione. Aprire la PowerShell di Skype for Business Server:
    
   - Per un servizio SAN di individuazione automatica mancante (sostituendo il parametro-CA con il proprio percorso dell'autorità di certificazione):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Se si dispone di più domini SIP, non è possibile utilizzare il parametro AllSipDomain come nell'esempio precedente. È necessario utilizzare invece il parametro DomainName. Quando si utilizza il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover. Un esempio potrebbe essere (sostituendo il parametro-CA con il proprio percorso dell'autorità di certificazione):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. In alternativa, dopo aver verificato le voci di SAN che sono state trovate, si dispone di **più certificati** che non dispongono di tutte le voci necessarie. È necessario apportare una nuova richiesta di certificato all'autorità di certificazione. Aprire la PowerShell di Skype for Business Server:
    
   - Per un servizio SAN di individuazione automatica mancante (sostituendo il parametro-CA con il proprio percorso dell'autorità di certificazione):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Se si dispone di più domini SIP, non è possibile utilizzare il parametro AllSipDomain come nell'esempio precedente. È necessario utilizzare invece il parametro DomainName. Quando si utilizza il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover. Gli esempi potrebbero essere (sostituendo il parametro-CA con il proprio percorso dell'autorità di certificazione):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Dopo che i nuovi certificati sono stati generati dall'autorità di certificazione, sarà necessario assegnarli.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Assegnare certificati tramite Skype for Business Server Management Shell

- A seconda di cosa si è trovato nella sezione non ho bisogno di nuove certificazioni, è necessario eseguire **una** delle operazioni seguenti.
    
  - Se si dispone di un solo certificato per tutti gli elementi (le identificazioni personali sono identici), è necessario eseguire questa operazione:
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Se sono presenti certificati diversi per gli elementi (le identificazioni personali sono tutte diverse), eseguire questa operazione:
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Visualizzazione di certificati in Microsoft Management Console (MMC)

1. È possibile esaminare i certificati utilizzando lo snap-in certificati per MMC. È sufficiente digitare MMC in Search e dovrebbe apparire come un'opzione di applicazione.
    
2. Per aggiungere lo snap-in certificati, è necessario fare clic su **file** e quindi **aggiungere/rimuovere lo snap-in...** (o la combinazione di tasti di scelta rapida **CTRL + M** funzionerebbe anche). I **certificati** saranno un'opzione nel riquadro sinistro, selezionarlo e quindi **account computer** nella finestra popup, quindi **Avanti**.
    
3. Sempre nella finestra popup, è probabile che si stia eseguendo questa operazione nel computer che ospita i certificati che è necessario esaminare, quindi lasciare la selezione sul **computer locale** , se è così. Se si lavora su un computer remoto, cambiare il pulsante di opzione su un **altro calcolatore** e quindi immettere il nome di dominio completo del computer o utilizzare il pulsante **Sfoglia** per cercare il computer tramite Active Directory. Dopo aver selezionato il computer, è necessario fare clic su **fine** quando pronto e quindi su **OK** per aggiungere lo snap-in alla console MMC.
    
4. Espandere la sezione **certificati** nel riquadro sinistro della console MMC. Espandere anche la cartella **personale** e quindi selezionare **certificati**. In questo modo è possibile visualizzare i certificati in questo archivio.
    
5. È necessario individuare il certificato che si desidera visualizzare, fare clic con il pulsante destro del mouse su di esso e scegliere **Apri**.
    
    > [!NOTE]
    > Come si fa a sapere quale certificato è? Dovrebbe essere il singolo certificato assegnato a tutto per la farm oppure possono essere presenti più certificati per cose diverse, come default, servizi Web interni e così via, in questo caso potrebbe essere necessario esaminare più certificati. Più certificati avranno la stessa identificazione personale. 
  
6. Dopo aver ottenuto la visualizzazione **certificato** , scegliere **Dettagli**. In questo modo viene visualizzato il nome del soggetto del certificato quando si seleziona **soggetto** e viene visualizzato il nome del soggetto assegnato e le proprietà associate.
    
7. È inoltre necessario controllare le voci del **nome alternativo soggetto** . Sono disponibili una o più delle opzioni seguenti:
    
   - Il nome del pool per il pool o il nome del server singolo se non si tratta di un pool.
    
   - Nome del server a cui è assegnato il certificato.
    
   - Simple URL Records, in genere Meet e dialin.
    
   - Servizi Web interni e nomi esterni dei servizi Web (ad esempio, webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologie e le selezioni dei servizi Web in corso.
    
   - Se è già stato assegnato, il lyncdiscover.\<sipdomain\> e lyncdiscoverinternal.\<sipdomain\> record.
    
     Se si dispone di più di un utente, è necessario controllare più certificati (vedere la nota precedente).
    
8. Pertanto, se si trova lyncdiscover.\<sipdomain\> e lyncdiscoverinternal.\<sipdomain\> record, questa configurazione è già stata configurata. È possibile chiudere la console MMC.
    
9. Se non sono assegnati, è necessario effettuare una nuova richiesta di certificato (descritta sopra) oppure è necessario installarla dopo la richiesta (si consiglia di eseguire la seguente procedura di PowerShell in questo caso).
    
## <a name="configure-the-reverse-proxy"></a>Configurare il proxy inverso
<a name="ConfigRP"> </a>

I passaggi riportati di seguito non devono essere seguiti in modo esatto. Ciò è dovuto al fatto che nelle versioni precedenti del prodotto, ad esempio, è stata configurata la configurazione di Threat Management Gateway (TMG) e, se non è stato utilizzato, è necessario elaborare la propria versione.
  
TMG non è più offerto da Microsoft come prodotto e, se è ancora necessario configurarlo, è possibile esaminare i [passaggi di Lync Server 2013](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx). Tuttavia, le seguenti informazioni sono destinate a essere più generalmente utili, anche se non è possibile fornire procedure dettagliate specifiche per ogni proxy inverso là fuori.
  
Sono due le principali considerazioni da prendere in considerazione:
  
- Si intende eseguire la richiesta di individuazione automatica iniziale su HTTPS (cosa consigliata)?
    
  - Se si dispone di una regola di pubblicazione Web, è necessario modificarla.
    
  - Se non si dispone ancora di una regola di pubblicazione Web, è necessario crearla.
    
- Se si sta eseguendo la richiesta di individuazione automatica iniziale su HTTP, sarà necessario creare o modificare anche la regola.
    
> [!NOTE]
> **Importante** Un valore di timeout del proxy è un numero che può variare dalla distribuzione alla distribuzione. È necessario monitorare la distribuzione e modificare il valore per la migliore esperienza per i client. Potrebbe essere possibile impostare il valore come minimo di 200. Se si supportano client mobili Lync nell'ambiente, è necessario impostare il valore su 960 per consentire i timeout di notifica push da Office 365, che hanno un valore di timeout di 900. È molto probabile che sia necessario aumentare il valore di timeout per evitare che il client si disconnetta quando il valore è troppo basso oppure diminuisce il numero se le connessioni tramite il proxy non si disconnettono ma sono chiare dopo la disconnessione del client. Il monitoraggio e la previsione dei requisiti usuali per l'ambiente sono l'unico modo esatto per determinare l'impostazione appropriata per questo valore.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modificare la regola di pubblicazione Web esistente per la SAN e l'URL di individuazione automatica esterni

1. Aprire l'interfaccia proxy inverso.
    
2. È necessario individuare la regola di pubblicazione Web e scegliere l'opzione di modifica, che può essere visualizzata in un menu o in una scheda, a seconda della configurazione del proxy inverso.
    
3. Deve essere presente un'area a cui viene applicata la regola di pubblicazione Web. È necessario modificare questa regola per i siti in ingresso o le richieste per i siti. Si sta per **aggiungere** una nuova voce.
    
4. Digitare il nome del sito di individuazione automatica (l'esempio che verrà utilizzato è lyncdiscover.contoso.com) e fare clic su **OK** o su **Salva**, a seconda del formato del proxy inverso.
    
5. Potrebbe essere presente un nuovo certificato che contiene la voce SAN di individuazione automatica. Che deve essere installato e configurato per l'utilizzo in base alle impostazioni del proxy inverso. Assicurarsi di salvare tutto quando la configurazione è stata completata.
    
6. Se il proxy inverso dispone di una funzionalità di **testing** , utilizzarlo per assicurarsi che tutto funzioni correttamente.
    
7. A questo punto, potrebbe essere necessario ripetere questi passaggi se si dispone di un server Director o di un pool di server Director nell'ambiente in uso, ovvero se si dispone di una seconda regola.
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Creare una regola di pubblicazione Web per l'URL di individuazione automatica esterno

1. Aprire l'interfaccia proxy inverso.
    
2. È necessario individuare la posizione dell'interfaccia per la creazione delle regole di pubblicazione Web e scegliere l'opzione **nuovo** o **Crea** (può essere presente in un menu o in una scheda, a seconda della configurazione del proxy inverso). Si sta cercando l'opzione per creare una nuova regola di pubblicazione Web.
    
3. In genere, è necessario immettere le informazioni seguenti:
    
   - **Nome**: il nome della regola
    
   - **Azione della regola**: in questo caso è una regola **Allow** , si sta lasciando che qualcosa passi attraverso il proxy inverso.
    
   - La regola di **pubblicazione** o l'opzione che si sta scegliendo potrebbe essere un **singolo sito Web o un bilanciamento del carico**.
    
   - Questo deve essere **SSL** per l'accesso esterno, scegliere quell'opzione.
    
   - Sarà necessario pubblicare un percorso per la **pubblicazione interna** e immettere il nome di dominio completo per i servizi Web esterni sul bilanciamento del carico del pool Front End (o il nome di dominio completo del servizio di bilanciamento del carico del pool di server Director se ne esiste uno), un esempio potrebbe essere sfb_pool01. contoso. local.
    
   - È necessario digitare **/\\** _ come percorso da pubblicare, ma è necessario anche _ * inoltrare l'intestazione host originale * *.
    
   - Vi sarà un'opzione per i dettagli del **nome pubblico o esterno** o informazioni. Questo è il luogo in cui sarà possibile immettere:
    
   - **Accetta richieste**, ma dovrebbe essere per il nome di dominio.
    
   - Per il **nome**, è necessario immettere **lyncdiscover.** <sipdomain> (questo è l'URL del servizio di individuazione automatica esterno). A questo punto, se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front End, è necessario digitare il nome di dominio completo per i servizi Web esterni nel pool Front End (ad esempio, lyncwebextpool01.contoso.com).
    
   - Verrà visualizzata un'opzione **percorso** e sarà necessario immettere **/\\** _ qui.
    
   - È necessario selezionare un *listener SSL** con il certificato pubblico aggiornato.
    
   - La **delega di autenticazione** deve essere impostata su **Nessuna delega**, ma **dovrebbe** essere consentita l'autenticazione diretta del client.
    
   - La regola deve essere impostata su **tutti gli utenti**.
    
   - Queste devono essere tutte le informazioni necessarie per creare questa regola e consentire di procedere.
    
4. Sarà necessario verificare che l' **intestazione host originale** sia inoltrata.
    
5. Sarà necessario impostare anche le porte del **server Web** , è necessario eseguire le operazioni seguenti:
    
   - **Reindirizzare le richieste alla porta http** e il numero di porta dovrebbe essere **8080**.
    
   - **Reindirizzare le richieste alla porta SSL** e il numero di porta dovrebbe essere **4443**.
    
6. Quando tutto è configurato, è necessario salvarlo o applicarlo, quindi si desidera testare la regola.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Creare una regola di pubblicazione Web per la porta 80 (facoltativa)

1. Aprire l'interfaccia proxy inverso.
    
2. È necessario individuare la posizione dell'interfaccia per la creazione delle regole di pubblicazione Web e scegliere l'opzione **nuovo** o **Crea** (può essere presente in un menu o in una scheda, a seconda della configurazione del proxy inverso). Si sta cercando l'opzione per creare una nuova regola di pubblicazione Web.
    
3. In genere, è necessario immettere le informazioni seguenti:
    
   - **Nome**: il nome della regola
    
   - **Azione della regola**: in questo caso è una regola **Allow** , si sta lasciando che qualcosa passi attraverso il proxy inverso.
    
   - La regola di **pubblicazione** o l'opzione che si sta scegliendo potrebbe essere un **singolo sito Web o un bilanciamento del carico**.
    
   - Questa operazione deve essere una **connessione non protetta per la connessione al server Web o alla farm pubblicati**.
    
   - Sarà necessario pubblicare un percorso per la **pubblicazione interna** e immettere il nome di dominio completo per l' **indirizzo VIP** del sistema di bilanciamento del carico del pool Front End, un esempio potrebbe essere sfb_pool01. contoso. local.
    
   - È necessario digitare **/\\** _ come percorso da pubblicare, ma è necessario anche _ * inoltrare l'intestazione host originale * *.
    
   - Vi sarà un'opzione per i dettagli del **nome pubblico o esterno** o informazioni. Questo è il luogo in cui sarà possibile immettere:
    
   - **Accetta richieste**, ma dovrebbe essere per il nome di dominio.
    
   - Per il **nome**, è necessario immettere **lyncdiscover.** <sipdomain> (questo è l'URL del servizio di individuazione automatica esterno).
    
   - Verrà visualizzata un'opzione **percorso** e sarà necessario immettere **/\\** _ qui.
    
   - È necessario selezionare un listener Web o consentire al proxy inverso di crearne uno.
    
   - _ La *delega di autenticazione** deve essere impostata su **Nessuna delega**, ma **non deve** essere consentita l'autenticazione diretta del client.
    
   - La regola deve essere impostata su **tutti gli utenti**.
    
   - Queste devono essere tutte le informazioni necessarie per creare questa regola e consentire di procedere.
    
4. Sarà necessario impostare le porte del **server Web** , è necessario eseguire le operazioni seguenti:
    
   - **Reindirizzare le richieste alla porta http** e il numero di porta dovrebbe essere **8080**.
    
   - **Reindirizzare le richieste alla porta SSL** e il numero di porta dovrebbe essere **4443**.
    
5. Quando tutto è configurato, è necessario salvarlo o applicarlo, quindi si desidera testare la regola.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurare l'individuazione automatica per i dispositivi mobili con distribuzioni ibride
<a name="ConfigAutoD"> </a>

Gli ambienti ibridi in Skype for Business Server sono ambienti che combinano un ambiente locale e O365. Quando si utilizza Skype for Business Server in un ambiente ibrido, il servizio di individuazione automatica deve essere in grado di individuare un utente da uno di questi ambienti.
  
Per consentire ai client mobili di individuare il luogo in cui si trova l'utente, il servizio di individuazione automatica deve essere configurato con un nuovo URL (Uniform Resource Locator). Ecco come procedere:
  
1. Aprire Skype for Business Server Management Shell.
    
2. Per ottenere il valore dell'attributo **ProxyFqdn** per l'ambiente di Skype for Business Server, eseguire le operazioni seguenti:
    
   ```powershell
   Get-CsHostingProvider
   ```

3. Quindi, sempre nella finestra di Shell, eseguire:
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Dove [identity] viene sostituito dal nome di dominio dello spazio di indirizzi SIP condiviso.
    
## <a name="test-your-mobility-deployment"></a>Testare la distribuzione di dispositivi mobili
<a name="TestMobility"> </a>

Dopo aver distribuito il servizio per dispositivi mobili di Skype for Business Server e il servizio di individuazione automatica di Skype for Business Server, è necessario eseguire una transazione di test per verificare che la distribuzione funzioni correttamente. È possibile eseguire **test-CsUcwaConference** per verificare la capacità di due utenti di creare, partecipare e comunicare in una conferenza. Per eseguire questo test, sono necessari due utenti (reale o di prova) e le loro credenziali complete. Questo comando funzionerà sia per i client Skype for business che per i client Lync Server 2013.
  
Per i client di Lync Server 2010 su Skype for Business Server 2015, è necessario eseguire **Test-CsMcxP2PIM** per testare. Gli utenti di Lync Server 2010 dovranno comunque essere utenti effettivi, o utenti di test predefiniti, ed è necessario disporre delle credenziali per la password.

> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Servizi di conferenza di prova per Skype for business e Lync 2013 per i client mobili

1. Accedere come membro del ruolo **CsAdministrator** in qualsiasi computer in cui sia installato **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare **Skype for Business Server Management Shell** (è possibile digitare il nome in Search o andare a **tutti i programmi** e sceglierlo).
    
3. Nella riga di comando, immettere:
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   È inoltre possibile impostare le credenziali in uno script e passarle al cmdlet test. Di seguito è riportato un esempio.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Testare le conferenze per i client per dispositivi mobili Lync 2010

> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.

1. Accedere come membro del ruolo **CsAdministrator** in qualsiasi computer in cui sia installato **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare **Skype for Business Server Management Shell** (è possibile digitare il nome in Search o andare a **tutti i programmi** e sceglierlo).
    
3. Nella riga di comando, immettere:
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   È inoltre possibile impostare le credenziali in uno script e passarle al cmdlet test. Di seguito è riportato un esempio.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Per esaminare ulteriormente le procedure dei comandi, è possibile estrarre [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) e [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Configurare il sistema per le notifiche push
<a name="ConfigPush"> </a>

Le notifiche push, sotto forma di badge, icone o avvisi, possono essere inviate a un dispositivo mobile anche quando l'app Skype o Lync non è attiva. Ma cosa sono le notifiche push? Sono avvisi di eventi, come un invito a messaggistica istantanea nuovo o mancante, o per una segreteria telefonica ricevuta. Il servizio per dispositivi mobili di Skype for Business Server invia queste notifiche al servizio di notifica push di Skype for Business Server basato sul cloud, che invia quindi le notifiche al servizio di notifica push di Microsoft (MSNS) per gli utenti di Windows Phone.
  
Questa funzionalità è invariata rispetto a Lync Server 2013, ma se si dispone di un server Skype for business, è necessario eseguire le operazioni seguenti:
  
- Per un server perimetrale di Skype for Business Server, aggiungere un nuovo provider di hosting, Microsoft Skype for business online e quindi configurare la Federazione dei provider di hosting tra l'organizzazione e Skype for business online.
    
- Abilitare le notifiche push eseguendo il cmdlet **Set-CsPushNotificationConfiguration** . Per impostazione predefinita, le notifiche push sono disattivate.
    
- Testare la configurazione della Federazione e le notifiche push.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurare il server perimetrale di Skype for business per le notifiche push

1. Accedere, con un account membro del ruolo **CsAdministrator** , a un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare la **Shell di gestione di Skype for Business Server**.
    
3. Aggiungere un provider di hosting di Skype for Business Server online.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Ad esempio:
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Non è possibile avere più di una relazione di federazione con un singolo provider di hosting. Pertanto, se è già stato configurato un provider di hosting con una relazione di federazione con sipfed.online.lync.com, non aggiungere un altro provider di hosting, anche se l'identità del provider di hosting è diversa da SkypeOnline. 
  
4. Configurare la Federazione dei provider di hosting tra l'organizzazione e il servizio di notifica push in Skype for business online. Nella riga di comando, è necessario digitare quanto segue:
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Abilitare le notifiche push

1. Accedere, con un account membro del ruolo **CsAdministrator** , a un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare la **Shell di gestione di Skype for Business Server**.
    
3. Abilitare le notifiche push:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Abilitare la Federazione:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Verificare la Federazione e le notifiche push

1. Accedere, con un account membro del ruolo **CsAdministrator** , a un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare la **Shell di gestione di Skype for Business Server**.
    
3. Testare la configurazione della Federazione:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Ad esempio:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Testare le notifiche push:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Ad esempio:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Configurare i criteri per dispositivi mobili
<a name="ConfigMob"> </a>

Si ha la possibilità con Skype for Business Server di determinare gli utenti che possono utilizzare il servizio per dispositivi mobili, la chiamata tramite lavoro, la VoIP (Voice over IP) o il video, nonché l'eventuale presenza di WiFi per VoIP o video. Chiamata tramite lavoro consente a un utente mobile di utilizzare il numero di telefono dell'ufficio, invece del numero di cellulare, quando si effettuano chiamate. La persona all'altra estremità della linea non vedrà il numero di cellulare dell'utente mobile e consente all'utente mobile di evitare le spese di chiamata in uscita. Quando vengono configurati VoIP e video, gli utenti possono effettuare chiamate VoIP e video. Le impostazioni per l'utilizzo di Wi-Fi determinano se il dispositivo mobile di un utente dovrà utilizzare una rete Wi-Fi su una rete di dati cellulare.
  
La mobilità, la chiamata tramite lavoro e le funzionalità VoIP e video sono tutte abilitate per impostazione predefinita. L'impostazione per richiedere il WiFi per VoIP e video è disabilitata. Un amministratore può modificare questa impostazione, sia a livello globale, per sito o per utente.
  
Per poter utilizzare le funzionalità di mobilità e chiamare tramite il lavoro, gli utenti devono essere:
  
- Abilitata per Skype for Business Server
    
- Abilitata per VoIP aziendale.
    
- Assegnato un criterio per dispositivi mobili con l'opzione **EnableMobility** impostata su **true**.
    
Affinché gli utenti siano in grado di utilizzare la chiamata tramite il lavoro, dovranno anche essere:
  
- È stato assegnato un criterio vocale con l'opzione **Abilita squillo simultaneo dei telefoni** selezionati.
    
- Assegnato un criterio per dispositivi mobili con **EnableOutsideVoice** impostato su **true**.
    
> [!NOTE]
> Gli utenti che non sono abilitati per VoIP aziendale possono utilizzare i propri dispositivi mobili per effettuare chiamate Skype su Skype o possono partecipare a conferenze usando il collegamento fare clic per partecipare ai propri dispositivi mobili, se sono state impostate le opzioni appropriate per il criterio vocale a cui sono associati. Nell'argomento relativo alla pianificazione sono disponibili ulteriori dettagli. 
  
### <a name="modify-global-mobility-policy"></a>Modificare i criteri di mobilità globale

1. Accedere, con un account membro del ruolo **CsAdministrator** , a un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare la **Shell di gestione di Skype for Business Server**.
    
3. Disattivare l'accesso alla mobilità e chiamare tramite il lavoro a livello globale digitando:
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > È possibile disattivare la chiamata tramite lavoro senza disattivare l'accesso alla mobilità. Tuttavia, non è possibile disattivare la mobilità senza disattivare anche la chiamata tramite lavoro. 
  
    Per altre informazioni, vedere [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Modificare i criteri per dispositivi mobili per sito

1. Accedere, con un account membro del ruolo **CsAdministrator** , a un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare la **Shell di gestione di Skype for Business Server**.
    
3. È possibile creare criteri a livello di sito, disattivare VoIP e video, abilitare Richiedi WiFi per l'audio IP e richiedere il Wi-Fi per IP video per sito. Tipo
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Per ulteriori informazioni, vedere [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Modifica dei criteri per dispositivi mobili in base all'utente

1. Accedere, con un account membro del ruolo **CsAdministrator** , a un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare la **Shell di gestione di Skype for Business Server**.
    
3. Creare criteri di mobilità a livello di utente e disattivare la mobilità e la chiamata tramite lavoro da parte dell'utente. Tipo
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Un ulteriore esempio con i dati di esempio:
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > È possibile disattivare la chiamata tramite lavoro senza disattivare l'accesso alla mobilità. Tuttavia, non è possibile disattivare la mobilità senza disattivare anche la chiamata tramite lavoro. 
  

