---
title: Distribuire e configurare la mobilità per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Questo articolo illustra i passaggi per configurare un'installazione di Skype for Business Server esistente per l'uso del servizio di mobilità, consentendo ai dispositivi mobili di sfruttare le caratteristiche di mobilità di Skype for Business Server.
ms.openlocfilehash: 35b9ca6a69dc5add9331aa5399a59a572bdf6906
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195486"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Distribuire e configurare la mobilità per Skype for Business Server  
 
Questo articolo illustra i passaggi per configurare un'installazione di Skype for Business Server esistente per l'uso del servizio di mobilità, consentendo ai dispositivi mobili di sfruttare le caratteristiche di mobilità di Skype for Business Server.
  
Dopo aver esaminato l'articolo [relativo al piano per la mobilità per Skype for Business Server](../plan-your-deployment/mobility.md) , è necessario essere pronti per procedere con la procedura descritta di seguito per distribuire la mobilità nell'ambiente di Skype for Business Server. I passaggi sono i seguenti (e nella tabella è incluso un elenco di autorizzazioni):
  
|**Fase**|**Autorizzazioni**|
|:-----|:-----|
|[Creare record DNS](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Amministratori di dominio  <br/> DNSAdmins  <br/> |
|[Modificare i certificati](deploy-and-configure-mobility.md#ModCerts) <br/> |Amministratore locale  <br/> |
|[Configurare il proxy inverso](deploy-and-configure-mobility.md#ConfigRP) <br/> |Amministratore locale  <br/> |
|[Configurare l'individuazione automatica per la mobilità con distribuzioni ibride](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Amministratori di dominio  <br/> |
|[Testare la distribuzione della mobilità](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Configurare le notifiche push](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Configurare i criteri di mobilità](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Tutte le sezioni seguenti contengono passaggi che presuppongono che l'argomento di pianificazione sia stato letto. Se ti confonde qualcosa, sentiti libero di verificare le informazioni.

> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="create-dns-records"></a>Creare record DNS
<a name="CreateDNSRec"> </a>

Potresti averne già una parte nell'ambiente di Skype for Business Server, ma devi creare i record seguenti per il lavoro di individuazione automatica:
  
- Un record DNS interno che supporta gli utenti di dispositivi mobili che si connettono dall'interno della rete dell'organizzazione.
    
- Un record DNS esterno (o pubblico) per supportare gli utenti di dispositivi mobili che si connettono dall'esterno della rete dell'organizzazione.
    
Questi record possono essere nomi (host) o CNAME (non è necessario eseguire entrambe le operazioni, sono inclusi solo i passaggi per tutti gli elementi).
  
### <a name="create-an-internal-dns-cname-record"></a>Creare un record CNAME DNS interno

1. Accedere a un server DNS della rete che sia un membro del gruppo **Domain Admins** o del gruppo **DnsAdmins** .
    
2. Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione** (potrebbe essere necessario **cercarlo** se non si tratta di un'opzione dal menu Start), quindi fare clic su **DNS** per aprire lo snap-in amministrativo DNS.
    
3. Nel riquadro sinistro della finestra della console è necessario passare al dominio che ospita i server front-end di Skype for Business Server ed espandere le **aree di ricerca in avanti** .
    
4. Prendere un momento per vedere quale delle seguenti:
    
   - Tutti i record host A o AAAA per il server front-end (standard o Enterprise) o i pool di front-end.
    
   - Tutti i record host A o AAAA per un pool di Director o Director (una configurazione facoltativa che si può avere nella distribuzione).
    
5. Dopo aver notato questo, fai clic con il pulsante destro del mouse sul nome di dominio SIP e quindi scegli **nuovo alias (CNAME)** dal menu.
    
6. Nella casella di testo **nome alias** Digitare lyncdiscoverinternal per il nome host, per l'URL del servizio di individuazione automatica interno.
    
7. Nel **nome di dominio completo (FQDN per l'host di destinazione**è necessario digitare o individuare l'FQDN dei servizi Web interni per il pool Front-End (o un singolo server front-end o un pool di Director o un amministratore), identificato nel passaggio 4. Fare clic su OK quando viene immesso.
    
8. È necessario creare un nuovo record CNAME di individuazione automatica nella zona di ricerca diretta per ogni dominio SIP supportato nell'ambiente di Skype for Business Server.
    
### <a name="create-an-external-dns-cname-record"></a>Creare un record CNAME DNS esterno

1. Questi passaggi sono generici, perché non è possibile indicare il provider DNS pubblico che si sta usando, ma si vuole comunque aiutarti. Accedere al provider DNS pubblico con un account che consentirà di creare nuovi record DNS.
    
2. A questo punto, un dominio SIP dovrebbe già esistere per Skype for Business Server. Espandere l' **area di ricerca in avanti** per il dominio SIP oppure aprirla.
    
3. Prendere un momento per vedere quale delle seguenti:
    
   - Tutti i record host A o AAAA per il server front-end (standard o Enterprise) o i pool di front-end.
    
   - Tutti i record host A o AAAA per un pool di Director o Director (una configurazione facoltativa che si può avere nella distribuzione).
    
4. Una volta che hai queste informazioni, dovresti essere in grado di selezionare un'opzione per la creazione di un **nuovo alias (CNAME)**.
    
5. Ora dovresti essere in grado di immettere un **nome alias**, devi immettere Lyncdiscover qui per l'URL del servizio di individuazione automatica esterna.
    
6. A questo punto deve essere presente un'area da immettere in un **nome di dominio completo per l'host di destinazione**, che dovrà essere il nome di dominio completo per il pool Front-End (o un singolo server front-end o un pool di Director o un amministratore) identificato nel passaggio 3.
    
7. Potrebbe essere necessario salvare qui o se è necessario creare altri record CNAME nell'area di ricerca diretta di ogni dominio SIP nell'ambiente di Skype for Business Server, ma una volta pronti, salvare il lavoro.
    
### <a name="create-an-internal-dns-a-record"></a>Creare un record DNS interno

1. Accedere a un server DNS della rete che sia un membro del gruppo **Domain Admins** o del gruppo **DnsAdmins** .
    
2. Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione** (potrebbe essere necessario **cercarlo** se non si tratta di un'opzione dal menu Start), quindi fare clic su **DNS** per aprire lo snap-in amministrativo DNS.
    
3. Nel riquadro sinistro della finestra della console è necessario passare al dominio che ospita i server front-end di Skype for Business Server ed espandere le **aree di ricerca in avanti** .
    
4. Prendere un momento per vedere quale delle seguenti:
    
   - Tutti i record host A o AAAA per il server front-end (standard o Enterprise) o i pool di front-end.
    
   - Tutti i record host A o AAAA per un pool di Director o Director (una configurazione facoltativa che si può avere nella distribuzione).
    
5. Dopo aver notato questo, fare clic con il pulsante destro del mouse sul nome di dominio SIP e quindi scegliere **nuovo host (A o AAAA)** dal menu.
    
6. Nella casella di testo **nome** Digitare lyncdiscoverinternal per il nome host, per l'URL del servizio di individuazione automatica interno.
    
7. Nella casella di testo **indirizzo IP** Digitare l'indirizzo IP dei servizi Web interni per il pool Front-End (o un singolo server front-end o un pool o un Director di Director) identificato nel passaggio 4.
    
8. Al termine, fare clic su **Aggiungi host**e quindi fare clic su **OK**.
    
9. È necessario creare un nuovo record di individuazione automatica a o AAAA nella zona di ricerca inoltra per ogni dominio SIP supportato nell'ambiente di Skype for Business Server. A tale scopo, ripetere i passaggi 6-8 tutte le volte necessarie.
    
10. Al termine, fare clic su **fine**.
    
### <a name="create-an-external-dns-a-record"></a>Creare un record DNS esterno

1. Questi passaggi sono generici, perché non è possibile indicare il provider DNS pubblico che si sta usando, ma si vuole comunque aiutarti. Accedere al provider DNS pubblico con un account che consentirà di creare nuovi record DNS.
    
2. A questo punto, un dominio SIP dovrebbe già esistere per Skype for Business Server. Espandere l' **area di ricerca in avanti** per il dominio SIP oppure aprirla.
    
3. Prendere un momento per vedere quale delle seguenti:
    
   - Tutti i record host A o AAAA per il server front-end (standard o Enterprise) o i pool di front-end.
    
   - Tutti i record host A o AAAA per un pool di Director o Director (una configurazione facoltativa che si può avere nella distribuzione).
    
4. Una volta che hai queste informazioni, dovresti essere in grado di selezionare un'opzione per la creazione di un **nuovo host a o AAAA**.
    
5. Ora dovrebbe essere possibile immettere un **nome**, è necessario immettere Lyncdiscover qui per l'URL del servizio di individuazione automatica esterna.
    
6. A questo punto dovrebbe essere presente un'area da immettere in un **indirizzo IP**, che dovrà essere l'IP per il pool Front-End (o un singolo server front-end o un pool di Director o un direttore), identificato nel passaggio 3.
    
7. Potrebbe essere necessario salvare qui o se è necessario creare altri record a o AAAA nella zona di ricerca diretta di ogni dominio SIP per l'ambiente di Skype for Business Server, ma una volta pronti, salvare il lavoro.
    
## <a name="modify-certificates"></a>Modificare i certificati
<a name="ModCerts"> </a>

In caso di domande sulla pianificazione dei certificati, è stato documentato l'articolo [relativo al piano per la mobilità per Skype for Business Server](../plan-your-deployment/mobility.md) . Dopo aver esaminato questo argomento, verranno illustrati i passaggi seguenti:
  
- Sono necessari nuovi certificati?
    
- Richiedere nuovi certificati dall'autorità di certificazione (CA).
    
- Aggiornare i certificati sul posto con le sostituzioni che usano PowerShell.
    
- Controllo dei certificati tramite lo snap-in certificati in Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>Sono necessari nuovi certificati?

1. Prima di tutto, potrebbe essere necessario controllare e verificare quali certificati sono sul posto e se hanno o meno le voci necessarie. Per eseguire questa operazione, devi accedere al server Skype for business con un account che è un amministratore locale. Questo account può anche essere necessario avere diritti per l'autorità di certificazione (CA) emittente, per alcuni di questi passaggi.
    
2. Aprire Skype for Business Server Management Shell (è possibile usare la funzione di ricerca per trovarlo se non è stato aggiunto al menu Start o alla barra delle applicazioni).
    
3. Sarà essenziale sapere quali certificati sono stati assegnati prima di provare ad aggiungere un certificato aggiornato. Quindi, al comando digitare:
    
   ```
   Get-CsCertificate
   ```

4. Le informazioni del passaggio 3 saranno univoche per l'utente. È necessario esaminarlo per determinare se si dispone di un singolo certificato assegnato per più elementi o se è stato assegnato un certificato diverso per i diversi componenti che ne hanno bisogno. Il parametro **use** indica il modo in cui viene usato un certificato e il parametro **identificazione personale** indica se si tratta dello stesso certificato o di più certificati.
    
5. Se sono state consigliate le voci SAN nella sezione pianificazione, è consigliabile. In caso contrario, è necessario richiedere un nuovo certificato oppure più certificati (a seconda della configurazione) dell'autorità di certificazione.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Richiedere un nuovo certificato o certificati dall'autorità di certificazione (CA)

1. Dopo aver controllato per vedere quali sono le voci di SAN che si hanno, si è certi di avere un **singolo certificato** (dopo il controllo tramite la procedura descritta sopra) e si è appreso che non si hanno tutte le voci necessarie. È necessario apportare una nuova richiesta di certificato alla CA. Aprire la finestra di PowerShell per Skype for Business Server:
    
   - Per un SAN servizio di individuazione automatica mancante (sostituendo il parametro-CA con il percorso dell'autorità di certificazione):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ora, se si hanno più domini SIP, non è possibile usare il parametro AllSipDomain come illustrato nell'esempio precedente. Devi invece usare il parametro DomainName. Quando si usa il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover. Un esempio potrebbe essere (sostituendo il parametro-CA con il proprio percorso dell'autorità di certificazione):
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. In alternativa, dopo aver controllato per vedere quali sono le voci di SAN, è stato rilevato che sono presenti **più certificati** che non dispongono di tutte le voci necessarie. È necessario apportare una nuova richiesta di certificato alla CA. Aprire la finestra di PowerShell per Skype for Business Server:
    
   - Per un SAN servizio di individuazione automatica mancante (sostituendo il parametro-CA con il percorso dell'autorità di certificazione):
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ora, se si hanno più domini SIP, non è possibile usare il parametro AllSipDomain come illustrato nell'esempio precedente. Devi invece usare il parametro DomainName. Quando si usa il parametro DomainName, è necessario definire il nome di dominio completo per i record LyncdiscoverInternal e lyncdiscover. Gli esempi potrebbero essere (sostituendo il parametro-CA con il percorso dell'autorità di certificazione):
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Una volta generati i nuovi certificati dalla CA, sarà necessario assegnarli.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Assegnare certificati con Skype for Business Server Management Shell

- A seconda di cosa è stato trovato nella sezione non sono necessarie nuove certificazioni, è necessario eseguire **una** delle operazioni seguenti.
    
  - Se si dispone di un singolo certificato per tutto (le identificazioni personali sono identiche), è necessario eseguire questa operazione:
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Se si hanno certificati diversi per gli elementi (le identificazioni personali sono tutte diverse), eseguire questa operazione:
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Visualizzazione di certificati in Microsoft Management Console (MMC)

1. È possibile esaminare i certificati usando lo snap-in certificati per MMC. È sufficiente digitare MMC nella ricerca e dovrebbe essere visualizzata come opzione per l'applicazione.
    
2. Per aggiungere lo snap-in certificati, è necessario fare clic su **file**e quindi su **Aggiungi/Rimuovi snap-in...** (o anche tasti di scelta rapida **CTRL + M** funzionerebbe). I **certificati** saranno un'opzione nel riquadro sinistro, selezionarla e quindi l'account del **computer** nella finestra popup, quindi fare clic su **Avanti**.
    
3. Sempre nella finestra popup, con ogni probabilità si sta eseguendo questa operazione nel computer che ospita i certificati che è necessario esaminare, quindi lascia la selezione nel **computer locale** , se è così. Se si sta lavorando a un computer remoto, cambiare il pulsante di opzione in **un altro PC** e quindi immettere il nome di dominio completo del computer o usare il pulsante **Sfoglia** per cercare il computer tramite Active Directory. Dopo aver selezionato il computer, è necessario fare clic su **fine** quando è pronto e quindi su **OK** per aggiungere lo snap-in alla console MMC.
    
4. Espandere la sezione **certificati** nel riquadro sinistro di MMC. Espandere anche la cartella **personale** e quindi selezionare **certificati**. In questo modo è possibile visualizzare i certificati in questo archivio.
    
5. È necessario individuare il certificato che si vuole visualizzare, fare clic con il pulsante destro del mouse su di esso e scegliere **Apri**.
    
    > [!NOTE]
    > Come si può verificare quale certificato si tratta? Dovrebbe essere il singolo certificato assegnato a tutto il contenuto della farm oppure avere più certificati per elementi diversi, ad esempio i servizi Web interni e così via, in questo caso potrebbe essere necessario esaminare più certificati. Più certificati avranno la stessa identificazione personale. 
  
6. Dopo aver ottenuto la visualizzazione **certificato** , scegliere **Dettagli**. In questo modo viene visualizzato il nome del soggetto del certificato quando si seleziona **oggetto**e viene visualizzato il nome del soggetto assegnato e le proprietà associate.
    
7. Dovrai anche controllare le voci del **nome alternativo oggetto** . È possibile trovare una o più delle operazioni seguenti:
    
   - Il nome del pool per il pool o il nome del server singolo se non si tratta di un pool.
    
   - Il nome del server a cui è assegnato il certificato.
    
   - Record URL semplici, in genere soddisfano e effettuano la chiamata.
    
   - Servizi Web Internal e Web Services External names (ad esempio, webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologia e alle selezioni di servizi Web sovrascritte.
    
   - Se è già stata assegnata, Lyncdiscover. \<SipDomain\> e lyncdiscoverinternal. \<record\> di SipDomain.
    
     È necessario controllare più certificati se sono stati assegnati più di uno (selezionare la nota precedente).
    
8. Quindi, se trovi lyncdiscover. \<SipDomain\> e lyncdiscoverinternal. \<SipDomain\> Records, questa configurazione è già stata configurata. È possibile chiudere la console MMC.
    
9. Se non sono assegnati, è necessario effettuare una nuova richiesta di certificato (sopra sopra) oppure è necessario installarla dopo la richiesta (è consigliabile eseguire la seguente procedura di PowerShell).
    
## <a name="configure-the-reverse-proxy"></a>Configurare il proxy inverso
<a name="ConfigRP"> </a>

La procedura seguente non è destinata a essere seguita esattamente. Il motivo è che nelle versioni precedenti del prodotto, ad esempio, è stata configurata la configurazione di Threat Management Gateway (TMG) e, se non è stato usato, è necessario elaborare una versione personalizzata.
  
TMG non viene più offerto da Microsoft come prodotto e, se è comunque necessario configurarlo, è possibile esaminare i [passaggi di 2013 di Lync Server](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx). Ma le informazioni seguenti sono destinate a essere più in generale utili, anche se non c'è modo in cui possiamo eseguire procedure dettagliate specifiche per ogni proxy inverso.
  
Ci sono due aspetti principali da considerare:
  
- Si sta andando a eseguire la richiesta di individuazione automatica iniziale tramite HTTPS (che è consigliabile)?
    
  - Se si ha una regola di pubblicazione Web, è necessario modificarla.
    
  - Se non si ha ancora una regola di pubblicazione Web, è necessario crearla.
    
- Se si sta eseguendo la richiesta di individuazione automatica tramite HTTP, è necessario creare o modificare anche la regola.
    
> [!NOTE]
> **Importante** Un valore di timeout proxy è un numero che può variare dalla distribuzione alla distribuzione. È consigliabile monitorare la distribuzione e modificare il valore per l'esperienza ottimale per i client. Potresti essere in grado di impostare il valore in basso come 200. Se si supportano client mobili Lync nell'ambiente, è necessario impostare il valore su 960 per consentire i timeout delle notifiche push da Office 365, che hanno un valore di timeout di 900. È molto probabile che sia necessario aumentare il valore di timeout per evitare la disconnessione del client quando il valore è troppo basso o ridurre il numero se le connessioni tramite il proxy non si disconnettono, ma si cancellano molto tempo dopo la disconnessione del client. Il monitoraggio e la previsione delle operazioni usuali per l'ambiente sono l'unico modo esatto per determinare l'impostazione appropriata per questo valore.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modificare la regola di pubblicazione Web esistente per la SAN e l'URL di individuazione automatica esterna

1. Aprire l'interfaccia proxy inverso.
    
2. È necessario individuare la regola di pubblicazione Web e scegliere l'opzione di modifica (può essere presente in un menu o in una scheda, a seconda della configurazione del proxy inverso).
    
3. Dovrebbe essere presente un'area in cui viene applicata la regola di pubblicazione Web. È necessario modificare questa regola per i siti in arrivo o le richieste per i siti. Si sta per **aggiungere** una nuova voce.
    
4. Digitare il nome del sito di individuazione automatica (l'esempio che useremo è lyncdiscover.contoso.com) e fare clic su **OK** o su **Salva**, a seconda del formato del proxy inverso.
    
5. Potrebbe essere presente un nuovo certificato con la voce SAN individuazione automatica. Che deve essere installato anche e configurato per l'uso in base alle impostazioni del proxy inverso. Assicurarsi di salvare tutto quando la configurazione viene completata.
    
6. Se il proxy inverso ha una funzionalità di **test** , fare in modo che venga usato per verificare che tutto funzioni correttamente.
    
7. A questo punto, potrebbe essere necessario ripetere questa procedura se si ha un pool di Director o Director nell'ambiente in cui è presente una seconda regola.
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Creare una regola di pubblicazione Web per l'URL di individuazione automatica esterna

1. Aprire l'interfaccia proxy inverso.
    
2. È necessario individuare la posizione dell'interfaccia in cui creare le regole di pubblicazione Web e scegliere l'opzione **nuovo** o **Crea** (può essere presente in un menu o una scheda, a seconda della configurazione del proxy inverso). Si sta cercando l'opzione per creare una nuova regola di pubblicazione Web.
    
3. In genere, dovrai immettere le informazioni seguenti:
    
   - **Nome**: nome della regola
    
   - **Azione regola**: in questo caso si tratta di una regola **Allow** che consente di passare al proxy inverso.
    
   - La regola o l'opzione di **pubblicazione** che si sta scegliendo sarebbe un **singolo sito Web o**un punto di bilanciamento del carico.
    
   - Questo deve essere **SSL** per l'accesso esterno, scegliere questa opzione.
    
   - Dovrai pubblicare un percorso per la **pubblicazione interna**e immettere il nome di dominio completo per i servizi Web esterni sul servizio di bilanciamento del carico del pool di front end (o il nome di dominio completo del dispositivo di bilanciamento del carico del pool di Director se ne hai uno), un esempio sarebbe sfb_ pool01. contoso. local.
    
   - È consigliabile digitare ** / *** come percorso da pubblicare, ma è anche necessario **inoltrare l'intestazione host originale**.
    
   - Sarà disponibile un'opzione per i dettagli o le informazioni sul **nome pubblico o esterno** . Questa è la posizione in cui è possibile immettere:
    
   - **Accettare le richieste**, ma deve essere per il nome di dominio.
    
   - Per il **nome**, devi immettere **lyncdiscover.** <sipdomain>(questo è l'URL del servizio di individuazione automatica esterna). Ora, se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front-End, è necessario digitare il nome di dominio completo per i servizi Web esterni nel pool Front-End, ad esempio lyncwebextpool01.contoso.com.
    
   - Verrà visualizzata un'opzione **percorso** e sarà necessario immettere ** / *** qui.
    
   - È necessario selezionare un **listener SSL** con il certificato pubblico aggiornato.
    
   - La **delega per l'autenticazione** deve essere impostata su **Nessuna delega**, ma **deve** essere consentita l'autenticazione client diretta.
    
   - La regola deve essere impostata su **tutti gli utenti**.
    
   - Dovrebbero essere tutte le informazioni necessarie per creare questa regola e consentire di procedere.
    
4. Dovrai assicurarti che l' **intestazione host originale** sia inoltrata.
    
5. Sarà necessario impostare anche le porte del **server Web** , è necessario eseguire le operazioni seguenti:
    
   - **Reindirizza le richieste alla porta http** e il numero di porta deve essere **8080**.
    
   - **Reindirizza le richieste alla porta SSL** e il numero di porta deve essere **4443**.
    
6. Quando tutto è configurato, è necessario salvarlo o applicarlo, quindi si vuole testare la regola.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Creare una regola di pubblicazione Web per la porta 80 (facoltativa)

1. Aprire l'interfaccia proxy inverso.
    
2. È necessario individuare la posizione dell'interfaccia in cui creare le regole di pubblicazione Web e scegliere l'opzione **nuovo** o **Crea** (può essere presente in un menu o una scheda, a seconda della configurazione del proxy inverso). Si sta cercando l'opzione per creare una nuova regola di pubblicazione Web.
    
3. In genere, dovrai immettere le informazioni seguenti:
    
   - **Nome**: nome della regola
    
   - **Azione regola**: in questo caso si tratta di una regola **Allow** che consente di passare al proxy inverso.
    
   - La regola o l'opzione di **pubblicazione** che si sta scegliendo sarebbe un **singolo sito Web o**un punto di bilanciamento del carico.
    
   - Questa operazione deve essere una **connessione non protetta per la connessione al server Web o alla farm pubblicata**.
    
   - È necessario pubblicare un percorso per la **pubblicazione interna**e immettere il nome di dominio completo per l' **indirizzo VIP** del dispositivo di bilanciamento del carico del pool Front End, un esempio sarebbe sfb_pool01. contoso. local.
    
   - È consigliabile digitare ** / *** come percorso da pubblicare, ma è anche necessario **inoltrare l'intestazione host originale**.
    
   - Sarà disponibile un'opzione per i dettagli o le informazioni sul **nome pubblico o esterno** . Questa è la posizione in cui è possibile immettere:
    
   - **Accettare le richieste**, ma deve essere per il nome di dominio.
    
   - Per il **nome**, devi immettere **lyncdiscover.** <sipdomain>(questo è l'URL del servizio di individuazione automatica esterna).
    
   - Verrà visualizzata un'opzione **percorso** e sarà necessario immettere ** / *** qui.
    
   - È necessario selezionare un listener Web o consentire al proxy inverso di crearne uno per l'utente.
    
   - La **delega per l'autenticazione** deve essere impostata su **Nessuna delega**, ma l'autenticazione client diretta **non deve** essere consentita.
    
   - La regola deve essere impostata su **tutti gli utenti**.
    
   - Dovrebbero essere tutte le informazioni necessarie per creare questa regola e consentire di procedere.
    
4. Sarà necessario impostare le porte del **server Web** , è necessario eseguire le operazioni seguenti:
    
   - **Reindirizza le richieste alla porta http** e il numero di porta deve essere **8080**.
    
   - **Reindirizza le richieste alla porta SSL** e il numero di porta deve essere **4443**.
    
5. Quando tutto è configurato, è necessario salvarlo o applicarlo, quindi si vuole testare la regola.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurare l'individuazione automatica per la mobilità con distribuzioni ibride
<a name="ConfigAutoD"> </a>

Gli ambienti ibridi in Skype for Business Server sono ambienti che combinano un ambiente locale e Office 365. Quando si utilizza Skype for Business Server in un ambiente ibrido, il servizio di individuazione automatica deve essere in grado di individuare un utente da uno di questi ambienti.
  
Per consentire ai client mobili di individuare la posizione di un utente, è necessario configurare il servizio di individuazione automatica con un nuovo URL (Uniform Resource Locator). I passaggi sono i seguenti:
  
1. Aprire Skype for Business Server Management Shell.
    
2. Eseguire la procedura seguente per ottenere il valore dell'attributo **ProxyFqdn** per l'ambiente di Skype for Business Server:
    
   ```
   Get-CsHostingProvider
   ```

3. Quindi, sempre nella finestra della shell, Esegui:
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Dove [Identity] viene sostituito con il nome di dominio dello spazio di indirizzi SIP condiviso.
    
## <a name="test-your-mobility-deployment"></a>Testare la distribuzione della mobilità
<a name="TestMobility"> </a>

Dopo aver distribuito il servizio di mobilità di Skype for Business Server e il servizio di individuazione automatica di Skype for Business Server, è consigliabile eseguire una transazione di test per verificare che la distribuzione funzioni correttamente. È possibile eseguire **test-CsUcwaConference** per testare la capacità di due utenti di creare, partecipare e comunicare in una conferenza. Per eseguire questo test, sono necessari due utenti (reali o test) e le loro credenziali complete. Questo comando funzionerà sia per i client Skype for business che per i client Lync Server 2013.
  
Per i client di Lync Server 2010 in Skype for Business Server 2015, è necessario eseguire **Test-CsMcxP2PIM** per testare. Gli utenti di Lync Server 2010 dovranno comunque essere utenti effettivi o utenti di test predefiniti e saranno necessarie le credenziali per la password.

> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Testare i servizi di conferenza per Skype for business e i client per dispositivi mobili Lync 2013

1. Accedere come membro del ruolo **CsAdministrator** in qualsiasi computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare **Skype for Business Server Management Shell** (è possibile digitare il nome in ricerca o accedere a **tutti i programmi** e sceglierlo).
    
3. Nella riga di comando immettere:
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   È anche possibile impostare le credenziali in uno script e passarle al cmdlet di test. Di seguito è riportato un esempio.
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Testare i servizi di conferenza per i client mobili di Lync 2010

> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.

1. Accedere come membro del ruolo **CsAdministrator** in qualsiasi computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare **Skype for Business Server Management Shell** (è possibile digitare il nome in ricerca o accedere a **tutti i programmi** e sceglierlo).
    
3. Nella riga di comando immettere:
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   È anche possibile impostare le credenziali in uno script e passarle al cmdlet di test. Di seguito è riportato un esempio.
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Per esaminare ulteriormente le procedure di comando, è possibile estrarre [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) e [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Configurare le notifiche push
<a name="ConfigPush"> </a>

Le notifiche push, in forma di badge, icone o avvisi, possono essere inviate a un dispositivo mobile anche quando l'app Skype o Lync è inattiva. Ma cosa sono le notifiche push? Si tratta di avvisi per eventi, ad esempio un invito a un messaggio ISTANTANEo nuovo o mancato o per la segreteria telefonica ricevuta. Il servizio di mobilità di Skype for Business Server invia queste notifiche al servizio di notifica push di Skype for Business Server basato su cloud, che invia quindi le notifiche al servizio di notifica push Microsoft (MSNS) per gli utenti di Windows Phone.
  
Questa funzionalità è invariata rispetto a Lync Server 2013, ma se si ha un server Skype for business, è necessario eseguire le operazioni seguenti:
  
- Per un server Edge Skype for Business Server, aggiungere un nuovo provider di hosting, Microsoft Skype for business online e quindi configurare la Federazione del provider di hosting tra l'organizzazione e Skype for business online.
    
- Abilitare le notifiche push eseguendo il cmdlet **Set-CsPushNotificationConfiguration** . Per impostazione predefinita, le notifiche push sono disattivate.
    
- Verificare la configurazione della Federazione e le notifiche push.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurare Skype for Business Edge Server per le notifiche push

1. Accedere, con un account che fa parte del ruolo **CsAdministrator** , in un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare **Skype for Business Server Management Shell**.
    
3. Aggiungere un provider di hosting di Skype for Business Server online.
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Ad esempio:
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Non è possibile avere più relazioni tra le federazioni con un singolo provider di hosting. Quindi, se hai già configurato un provider di hosting che ha una relazione di federazione con sipfed.online.lync.com, non aggiungere un altro provider di hosting, anche se l'identità del provider di hosting è diversa da SkypeOnline. 
  
4. Configurare la Federazione del provider di hosting tra l'organizzazione e il servizio di notifica push su Skype for business online. Alla riga di comando è necessario digitare:
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Abilitare le notifiche push

1. Accedere, con un account che fa parte del ruolo **CsAdministrator** , in un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare **Skype for Business Server Management Shell**.
    
3. Abilitare le notifiche push:
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Abilita federazione:
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Federazioni di test e notifiche push

1. Accedere, con un account che fa parte del ruolo **CsAdministrator** , in un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare **Skype for Business Server Management Shell**.
    
3. Verificare la configurazione della Federazione:
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Ad esempio:
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Verificare le notifiche push:
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Ad esempio:
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Configurare i criteri di mobilità
<a name="ConfigMob"> </a>

Puoi usare Skype for Business Server per determinare chi può utilizzare il servizio di mobilità, chiamare tramite lavoro, Voice over IP (VoIP) o video, oltre a stabilire se il WiFi sarà necessario per il VoIP o il video. Chiamata tramite lavoro consente a un utente di dispositivi mobili di usare il numero di telefono dell'ufficio, invece del numero di cellulare, quando si effettuano le chiamate. La persona all'altra estremità della riga non vedrà il numero di cellulare dell'utente mobile e consentirà all'utente di evitare oneri per le chiamate in uscita. Quando sono configurati VoIP e video, gli utenti possono eseguire chiamate VoIP e video. Le impostazioni per l'utilizzo di WiFi determinano se un dispositivo mobile dell'utente sarà necessario per usare una rete WiFi tramite una rete dati cellulare.
  
La mobilità, la chiamata tramite lavoro e le funzionalità VoIP e video sono tutte abilitate per impostazione predefinita. L'impostazione per richiedere il WiFi per VoIP e video è disabilitata. Un amministratore ha la possibilità di modificare questa funzionalità, sia a livello globale, per sito, sia per utente.
  
Per poter usare le caratteristiche di mobilità e chiamare tramite lavoro, gli utenti devono essere:
  
- Abilitato per Skype for Business Server
    
- Abilitato per VoIP aziendale.
    
- Assegnato un criterio di mobilità con l'opzione **EnableMobility** impostata su **true**.
    
Per consentire agli utenti di usare la chiamata tramite il lavoro, sarà anche necessario:
  
- Assegnato un criterio vocale con l'opzione **Abilita squillo simultaneo dei telefoni** selezionata.
    
- Assegnato un criterio di mobilità con **EnableOutsideVoice** impostato su **true**.
    
> [!NOTE]
> Gli utenti non abilitati per Enterprise Voice possono usare i loro dispositivi mobili per effettuare chiamate Skype to Skype VoIP o possono partecipare a conferenze usando il collegamento Fai clic per partecipare ai loro dispositivi mobili, se sono impostate le opzioni appropriate per il criterio vocale a cui sono associate. con. Nell'argomento pianificazione sono disponibili altri dettagli. 
  
### <a name="modify-global-mobility-policy"></a>Modificare i criteri di mobilità globale

1. Accedere, con un account che fa parte del ruolo **CsAdministrator** , in un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare **Skype for Business Server Management Shell**.
    
3. Disattivare l'accesso alla mobilità e chiamare tramite il lavoro a livello globale digitando:
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > È possibile disattivare la chiamata tramite lavoro senza disattivare l'accesso alla mobilità. Ma non è possibile disattivare la mobilità senza disattivare la chiamata anche tramite lavoro. 
  
    Per altre info, Vedi [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Modificare i criteri di mobilità per sito

1. Accedere, con un account che fa parte del ruolo **CsAdministrator** , in un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare **Skype for Business Server Management Shell**.
    
3. È possibile creare criteri a livello di sito, disattivare VoIP e video, abilitare Richiedi WiFi per l'audio IP e richiedere il WiFi per i video IP per sito. Tipo
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Altre informazioni su [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Modificare i criteri di mobilità per utente

1. Accedere, con un account che fa parte del ruolo **CsAdministrator** , in un computer in cui sono installati **Skype for Business Server Management Shell** e **OCSCore** .
    
2. Avviare **Skype for Business Server Management Shell**.
    
3. Creare criteri di mobilità a livello di utente e disattivare la mobilità e la chiamata tramite il lavoro da parte dell'utente. Tipo
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Un esempio ulteriore con i dati di esempio:
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > È possibile disattivare la chiamata tramite lavoro senza disattivare l'accesso alla mobilità. Ma non è possibile disattivare la mobilità senza disattivare la chiamata anche tramite lavoro. 
  

