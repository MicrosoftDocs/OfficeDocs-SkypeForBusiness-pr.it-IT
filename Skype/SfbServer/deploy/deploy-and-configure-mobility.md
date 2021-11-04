---
title: Distribuire e configurare dispositivi mobili per Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: In questo articolo vengono descritti i passaggi per configurare un'installazione di Skype for Business Server esistente per l'utilizzo del servizio per dispositivi mobili, consentendo ai dispositivi mobili di sfruttare le funzionalità di Skype for Business Server Mobility.
ms.openlocfilehash: 598a6b1879f08bb27a0ef5cb44a5033bc3e0339e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741502"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Distribuire e configurare dispositivi mobili per Skype for Business Server  
 
In questo articolo vengono descritti i passaggi per configurare un'installazione di Skype for Business Server esistente per l'utilizzo del servizio per dispositivi mobili, consentendo ai dispositivi mobili di sfruttare le funzionalità di Skype for Business Server Mobility.
  
Dopo aver esaminato l'articolo Plan [for Mobility for Skype for Business Server,](../plan-your-deployment/mobility.md) è consigliabile procedere con i passaggi seguenti per distribuire Mobility nell'ambiente Skype for Business Server aziendale. I passaggi sono i seguenti (e in questa tabella è incluso un elenco di autorizzazioni):
  
|**Fase**|**Autorizzazioni**|
|:-----|:-----|
|[Creare record DNS](deploy-and-configure-mobility.md#CreateDNSRec). <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[Modificare i certificati](deploy-and-configure-mobility.md#ModCerts) <br/> |Amministratore locale  <br/> |
|[Configurare il proxy inverso](deploy-and-configure-mobility.md#ConfigRP) <br/> |Amministratore locale  <br/> |
|[Configurare l'individuazione automatica per dispositivi mobili con distribuzioni ibride](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[Testare la distribuzione per dispositivi mobili](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Configurare il sistema per le notifiche push](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Configurare i criteri per dispositivi mobili](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Tutte le sezioni seguenti contengono passaggi che presuppongono che sia stato letto l'argomento Pianificazione. Se qualcosa ti confonde, non esita a consultare le informazioni.

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
## <a name="create-dns-records"></a>Creare record DNS
<a name="CreateDNSRec"> </a>

Potrebbero essere già presenti nell'ambiente di Skype for Business Server, ma è necessario creare i record seguenti per il funzionamento dell'individuazione automatica:
  
- Record DNS interno per supportare gli utenti mobili che si connettono dalla rete dell'organizzazione.
    
- Record DNS esterno (o pubblico) per supportare gli utenti mobili che si connettono dall'esterno della rete dell'organizzazione.
    
Questi record possono essere nomi A (host) o record CNAME (non è necessario effettuare entrambi, stiamo solo includendo i passaggi per tutto qui).
  
### <a name="create-an-internal-dns-cname-record"></a>Creare un record CNAME DNS interno

1. Accedere a un server DNS nella rete membro del gruppo **Domain Admins** o **DnsAdmins.**
    
2. Fare clic sul pulsante **Start,**  scegliere Strumenti di amministrazione **(potrebbe** essere necessario cercarlo se non è un'opzione del menu Start) e quindi fare clic su **DNS** per aprire lo snap-in di amministrazione DNS.
    
3. Nel riquadro sinistro della finestra della console, è necessario passare al dominio che ospita i Front End Server del  Skype for Business Server ed espandere le zone di ricerca diretta.
    
4. Prenditi un momento per vedere quale dei seguenti elementi hai:
    
   - Qualsiasi record A o AAAA host per il Front End Server (Standard o Enterprise) o i pool Front End.
    
   - Qualsiasi record A o AAAA host per un director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).
    
5. Dopo aver preso questa notifica, fare clic con il pulsante destro del mouse sul nome di dominio SIP e quindi scegliere **Nuovo alias (CNAME)** dal menu.
    
6. Nella casella **di testo Nome** alias digitare lyncdiscoverinternal per il nome host, per l'URL del servizio di individuazione automatica interno.
    
7. Nel nome di dominio completo (FQDN per **l'host** di destinazione), è necessario digitare o passare all'FQDN dei servizi Web interni per il pool Front End (o un singolo Front End Server o pool di server Director o Director), identificato nel passaggio 4 precedente. Al momento dell'immissione, fare clic su OK.
    
8. Sarà necessario creare un nuovo record CNAME di individuazione automatica nella zona di ricerca diretta per ogni dominio SIP supportato nell'Skype for Business Server locale.
    
### <a name="create-an-external-dns-cname-record"></a>Creare un record CNAME DNS esterno

1. Questi passaggi sono generici, perché non è possibile indicare quale provider DNS pubblico potrebbe essere in uso, ma vogliamo comunque aiutarti. Accedere al provider DNS pubblico con un account che sarà in grado di creare nuovi record DNS.
    
2. A questo punto, deve esistere già un dominio SIP per Skype for Business Server. Espandere la **zona di ricerca diretta** per il dominio SIP o aprirla in altro modo.
    
3. Prenditi un momento per vedere quale dei seguenti elementi hai:
    
   - Qualsiasi record A o AAAA host per il Front End Server (Standard o Enterprise) o i pool Front End.
    
   - Qualsiasi record A o AAAA host per un director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).
    
4. Una volta che hai queste informazioni, dovresti essere in grado di selezionare un'opzione per la creazione di un **nuovo alias (CNAME).**
    
5. A questo punto dovrebbe essere possibile immettere un **nome alias**, è necessario immettere lyncdiscover qui per l'URL del servizio di individuazione automatica esterno.
    
6. Successivamente dovrebbe essere presente un'area da immettere in un nome di dominio completo per **l'host** di destinazione, che dovrà essere il nome di dominio completo per il pool Front End (o un singolo Front End Server o pool di server Director o Director), identificato nel passaggio 3 precedente.
    
7. Potrebbe essere necessario salvare qui o se è necessario creare ulteriori record CNAME nella zona di ricerca diretta di ogni dominio SIP nell'ambiente Skype for Business Server, ma una volta pronti, salvare il lavoro.
    
### <a name="create-an-internal-dns-a-record"></a>Creare un record A DNS interno

1. Accedere a un server DNS nella rete membro del gruppo **Domain Admins** o **DnsAdmins.**
    
2. Fare clic sul pulsante **Start,**  scegliere Strumenti di amministrazione **(potrebbe** essere necessario cercarlo se non è un'opzione del menu Start) e quindi fare clic su **DNS** per aprire lo snap-in di amministrazione DNS.
    
3. Nel riquadro sinistro della finestra della console, è necessario passare al dominio che ospita i Front End Server del  Skype for Business Server ed espandere le zone di ricerca diretta.
    
4. Prenditi un momento per vedere quale dei seguenti elementi hai:
    
   - Qualsiasi record A o AAAA host per il Front End Server (Standard o Enterprise) o i pool Front End.
    
   - Qualsiasi record A o AAAA host per un director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).
    
5. Dopo aver preso questa notifica, fare clic con il pulsante destro del mouse sul nome di dominio SIP e quindi scegliere **Nuovo host (A o AAAA)** dal menu.
    
6. Nella casella **di testo** Nome digitare lyncdiscoverinternal come nome host per l'URL del servizio di individuazione automatica interno.
    
7. Nella casella **di testo Indirizzo IP** digitare l'indirizzo IP dei servizi Web interni per il pool Front End (o un singolo Front End Server o pool di server Director o Director), identificato nel passaggio 4 precedente.
    
8. Al termine, fare clic **su Aggiungi host** e quindi su **OK.**
    
9. Sarà necessario creare un nuovo record A o AAAA di individuazione automatica nella zona di ricerca diretta per ogni dominio SIP supportato nell'Skype for Business Server locale. A tale scopo, ripetere i passaggi da 6 a 8 il numero di volte necessario.
    
10. Al termine, fare clic su **Fine.**
    
### <a name="create-an-external-dns-a-record"></a>Creare un record A DNS esterno

1. Questi passaggi sono generici, perché non è possibile indicare quale provider DNS pubblico potrebbe essere in uso, ma vogliamo comunque aiutarti. Accedere al provider DNS pubblico con un account che sarà in grado di creare nuovi record DNS.
    
2. A questo punto, deve esistere già un dominio SIP per Skype for Business Server. Espandere la **zona di ricerca diretta** per il dominio SIP o aprirla in altro modo.
    
3. Prenditi un momento per vedere quale dei seguenti elementi hai:
    
   - Qualsiasi record A o AAAA host per il Front End Server (Standard o Enterprise) o i pool Front End.
    
   - Qualsiasi record A o AAAA host per un director o un pool di server Director (una configurazione facoltativa che potrebbe essere presente nella distribuzione).
    
4. Una volta che hai queste informazioni, dovresti essere in grado di selezionare un'opzione per la creazione di un **nuovo host A o AAAA.**
    
5. A questo punto dovrebbe essere possibile immettere un **nome**, è necessario immettere lyncdiscover qui per l'URL del servizio di individuazione automatica esterno.
    
6. Successivamente dovrebbe essere presente un'area da immettere in un indirizzo **IP,** che dovrà essere l'IP per il pool Front End (o un singolo Front End Server o pool di server Director o Director), identificato nel passaggio 3 precedente.
    
7. Potrebbe essere necessario salvare qui o se è necessario creare ulteriori record A o AAAA nella zona di ricerca diretta di ogni dominio SIP per l'ambiente Skype for Business Server, ma una volta pronti, salvare il lavoro.
    
## <a name="modify-certificates"></a>Modificare i certificati
<a name="ModCerts"> </a>

Per domande sulla pianificazione dei certificati, è stato documentato [nell'articolo Plan for Mobility for Skype for Business Server.](../plan-your-deployment/mobility.md) Dopo aver esaminato questo articolo, verrà illustrata la procedura seguente:
  
- Sono necessari nuovi certificati?
    
- Richiesta di nuovi certificati all'Autorità di certificazione (CA).
    
- Aggiornamento dei certificati sul posto con le sostituzioni tramite PowerShell.
    
- Verifica dei certificati tramite lo snap-in Certificati in Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>Sono necessari nuovi certificati?

1. In primo luogo, potrebbe essere necessario controllare e vedere quali certificati sono sul posto e se hanno o meno le voci necessarie. A tale scopo, dovrai accedere al tuo Skype for Business Server con un account amministratore locale. Potrebbe inoltre essere necessario disporre dei diritti per l'Autorità di certificazione (CA) emittente per alcuni di questi passaggi.
    
2. Aprire Skype for Business Server Management Shell (è possibile utilizzare La ricerca per trovarla se non è stata aggiunta alla barra menu Start o alle attività).
    
3. Sarà essenziale sapere quali certificati sono stati assegnati prima di provare ad aggiungere un certificato aggiornato. Quindi, al comando, digitare:
    
   ```powershell
   Get-CsCertificate
   ```

4. Le informazioni del passaggio 3 saranno specifiche dell'utente. È necessario cercarlo per determinare se è stato assegnato un singolo certificato per più elementi o se è stato assegnato un certificato diverso per i diversi componenti che ne hanno bisogno. Il **parametro Use** indica come viene utilizzato un certificato e il parametro **Thumbprint** indica se si tratta dello stesso certificato o di più certificati.
    
5. Se le voci SAN sono consigliate nella sezione Pianificazione, è consigliabile. In caso contrario, dovrai richiedere un nuovo certificato o più certificati (a seconda della configurazione) dall'Autorità di certificazione.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Richiedere un nuovo certificato o un nuovo certificato all'Autorità di certificazione (CA)

1. Dopo aver controllato le voci SAN disponibili, si è a sapere di disporre di un singolo certificato **(dopo** aver controllato tramite i passaggi precedenti) e di aver appreso di non disporre di tutte le voci necessarie. È necessario eseguire una nuova richiesta di certificato all'autorità di certificazione. Aprire la Skype for Business Server PowerShell:
    
   - Per una san del servizio di individuazione automatica mancante (sostituendo il parametro -Ca con il percorso dell'autorità di certificazione):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ora, se si dispone di più domini SIP, non è possibile utilizzare il parametro AllSipDomain come nell'esempio precedente. Sarà invece necessario utilizzare il parametro DomainName. Quando si utilizza il parametro DomainName, è necessario definire il nome di dominio completo per i record lyncdiscoverinternal e lyncdiscover. Un esempio potrebbe essere (sostituendo il parametro -Ca con il percorso dell'autorità di certificazione):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. In caso contrario, dopo aver verificato quali voci SAN sono  disponibili, è possibile trovare più certificati che non dispongono di tutte le voci necessarie. È necessario eseguire una nuova richiesta di certificato all'autorità di certificazione. Aprire la Skype for Business Server PowerShell:
    
   - Per una san del servizio di individuazione automatica mancante (sostituendo il parametro -Ca con il percorso dell'autorità di certificazione):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Ora, se si dispone di più domini SIP, non è possibile utilizzare il parametro AllSipDomain come nell'esempio precedente. Sarà invece necessario utilizzare il parametro DomainName. Quando si utilizza il parametro DomainName, è necessario definire il nome di dominio completo per i record lyncdiscoverinternal e lyncdiscover. Alcuni esempi sono (sostituendo il parametro -Ca con il percorso dell'autorità di certificazione):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Dopo aver generato i nuovi certificati dall'autorità di certificazione, dovrai assegnarli.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Assegnare certificati tramite Skype for Business Server Management Shell

- A seconda di ciò che hai trovato nella sezione Do I need new certifications precedente, devi eseguire **una** delle operazioni seguenti.
    
  - Se si dispone di un singolo certificato per tutti gli elementi (le identificazione personale sono identiche), è necessario eseguire questa operazione:
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Se hai certificati diversi per le cose (le identificazioni personali sono tutte diverse), esegui invece questo comando:
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Visualizzazione dei certificati in Microsoft Management Console (MMC)

1. È possibile esaminare i certificati utilizzando lo snap-in Certificati per MMC. È sufficiente digitare MMC nella ricerca e dovrebbe essere visualizzata come opzione dell'applicazione.
    
2. Per aggiungere lo snap-in Certificati, è necessario fare clic su **File** e quindi su **Aggiungi/Rimuovi snap-in...** (o funziona anche il tasto di scelta rapida **CTRL+M).** **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.
    
3. Sempre nella finestra popup, con ogni probabilità si sta eseguendo questa operazione nel computer che ospita i certificati che è necessario esaminare, quindi lasciare la selezione su **Computer** locale, se è così. Se si utilizza un computer remoto, modificare il pulsante di opzione in Altro **computer**  e quindi immettere il nome di dominio completo del computer oppure utilizzare il pulsante Sfoglia per cercare il computer tramite Active Directory. Dopo aver selezionato il computer, sarà necessario fare clic **su** Fine quando è pronto e quindi **su OK** per aggiungere lo snap-in a MMC.
    
4. Espandere la **sezione** Certificati nel riquadro sinistro di MMC. Espandere anche **la** cartella Personale e quindi selezionare **Certificati**. In questo modo è possibile visualizzare i certificati in questo archivio.
    
5. È necessario individuare il certificato che si desidera visualizzare, fare clic con il pulsante destro del mouse su di esso e scegliere **Apri**.
    
    > [!NOTE]
    > Come si fa a sapere quale certificato si tratta? Deve essere il singolo certificato assegnato a tutti gli elementi della farm oppure è possibile disporre di più certificati per elementi diversi, ad esempio Predefinito, Servizi Web interni e così via, nel qual caso potrebbe essere necessario esaminare più certificati. Più certificati avranno la stessa identificazione personale. 
  
6. Dopo aver ottenuto la visualizzazione **Certificato,** scegliere **Dettagli**. In questo modo sarà possibile visualizzare il nome del soggetto del certificato quando si seleziona **Subject** e vengono visualizzati il nome soggetto assegnato e le proprietà associate.
    
7. Sarà inoltre necessario controllare le **voci Nome** soggetto alternativo. Sono disponibili una o più delle opzioni seguenti:
    
   - Il nome del pool per il pool o il nome del singolo server se non si tratta di un pool.
    
   - Nome del server a cui è assegnato il certificato.
    
   - Record DI URL semplici, in genere meet e dialin.
    
   - Nomi esterni dei servizi Web interni e dei servizi Web (ad esempio, webpool01.contoso.net, webpool01.contoso.com), in base alle scelte effettuate in Generatore di topologie e nelle selezioni di servizi Web sovrascissate.
    
   - Se già assegnato, lyncdiscover.\<sipdomain\> e lyncdiscoverinternal.\<sipdomain\> record.
    
     Dovrai controllare più certificati se ne hai assegnati più di uno (controlla la nota precedente).
    
8. Quindi, se si trova lyncdiscover.\<sipdomain\> e lyncdiscoverinternal.\<sipdomain\> record, hai già configurato questo. È possibile chiudere MMC.
    
9. Se non sono assegnati, dovrai effettuare una nuova richiesta di certificato (descritta sopra) o installarli dopo la richiesta (ti consigliamo di seguire powershell sopra per questo).
    
## <a name="configure-the-reverse-proxy"></a>Configurare il proxy inverso
<a name="ConfigRP"> </a>

I passaggi seguenti non devono essere eseguiti esattamente. Ciò è dovuto al fatto che nelle versioni precedenti del prodotto, sarebbe stato illustrato, ad esempio, la configurazione di Threat Management Gateway (TMG) e, se non si usava, sarebbe necessario determinare la propria versione da lì.
  
TMG non viene più offerto da Microsoft come prodotto e, se è ancora necessario configurarlo, è possibile esaminare i passaggi di [Lync Server 2013.](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility) Tuttavia, le informazioni seguenti hanno lo scopo di essere più in generale utili, anche se non è possibile fornire passaggi dettagliati specifici per ogni proxy inverso disponibile.
  
Abbiamo due aspetti principali da considerare:
  
- Eseguire la richiesta di individuazione automatica iniziale su HTTPS (scelta consigliata)?
    
  - Se si dispone di una regola di pubblicazione Web, è necessario modificarla.
    
  - Se non si dispone ancora di una regola di pubblicazione Web, è necessario crearla.
    
- Se si sta eseguendo la richiesta di individuazione automatica iniziale su HTTP, sarà necessario creare o modificare anche la regola.
    
> [!NOTE]
> **Importante** Un valore di timeout proxy è un numero che varia da distribuzione a distribuzione. È consigliabile monitorare la distribuzione e modificare il valore per un'esperienza ottimale per i client. Potresti essere in grado di impostare il valore fino a 200. Se si supportano client mobili Lync nell'ambiente, è consigliabile impostare il valore su 960 per consentire timeout di notifica push da Office 365, con un valore di timeout pari a 900. È molto probabile che sia necessario aumentare il valore di timeout per evitare la disconnessione del client quando il valore è troppo basso o diminuire il numero se le connessioni tramite il proxy non si disconnettino, ma si cancellano molto tempo dopo la disconnessione del client. Il monitoraggio e la base di ciò che è consueto per l'ambiente è l'unico modo accurato per determinare l'impostazione appropriata per questo valore.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modificare la regola di pubblicazione Web esistente per la SAN e l'URL di individuazione automatica esterni

1. Apri l'interfaccia proxy inverso.
    
2. Dovrai individuare la regola di pubblicazione Web e scegliere l'opzione Modifica (potrebbe essere in un menu o in una scheda, a seconda della configurazione del proxy inverso).
    
3. Deve essere presente un'area che indica a cosa viene applicata questa regola di pubblicazione Web. È necessario modificare questa regola per i siti o le richieste in arrivo per i siti. Si aggiungerà **una** nuova voce.
    
4. Digitare il nome del sito di individuazione automatica (l'esempio che verrà utilizzato è lyncdiscover.contoso.com) e fare clic su **OK** o **Salva**, a seconda del formato del proxy inverso.
    
5. È possibile che sia presente un nuovo certificato con la voce SAN autodiscover. Deve essere installato e configurato per l'utilizzo in base alle impostazioni del proxy inverso. Assicurati di salvare tutto al termine della configurazione.
    
6. Se il proxy inverso ha una **funzionalità di test,** usalo per assicurarti che tutto funzioni correttamente.
    
7. A questo punto, potrebbe essere necessario ripetere questi passaggi se si dispone di un server Director o di un pool di server Director nell'ambiente (ciò significa che si dispone di una seconda regola).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Creare una regola di pubblicazione Web per l'URL di individuazione automatica esterno

1. Apri l'interfaccia proxy inverso.
    
2. Dovrai individuare la posizione nell'interfaccia in cui crei le  regole  di pubblicazione Web e scegliere l'opzione Nuovo o Crea (potrebbe essere in un menu o in una scheda, a seconda della configurazione del proxy inverso). Si sta cercando l'opzione per creare una nuova regola di pubblicazione Web.
    
3. In genere, è necessario immettere le informazioni seguenti:
    
   - **Nome**: il nome della regola
    
   - **Azione regola:** in questo caso si tratta di una regola **Allow,** che consente a qualcosa di passare attraverso il proxy inverso.
    
   - La **regola o** l'opzione di pubblicazione che si sta scegliendo è un singolo sito Web o un servizio di **bilanciamento del carico.**
    
   - Deve essere **SSL per** l'accesso esterno, scegliere questa opzione.
    
   - Sarà necessario pubblicare un percorso per La pubblicazione interna e immettere il nome di dominio completo per i servizi Web esterni nel servizio di bilanciamento del carico del pool Front End (o il nome di dominio completo del servizio di bilanciamento del carico del pool di server Director, se esistente), un esempio potrebbe essere sfb_pool01.contoso.local.
    
   - Devi digitare _ come percorso da pubblicare, ma devi anche _*inoltrare l'intestazione **/\\** host originale***.
    
   - Sarà disponibile un'opzione per informazioni o **dettagli sul nome pubblico** o esterno. Questo è il punto in cui potrai immettere:
    
   - **Accetta richieste**, ma deve essere per il nome di dominio.
    
   - Per **nome**, è necessario immettere **lyncdiscover.** <sipdomain> (questo è l'URL del servizio di individuazione automatica esterno). Se si sta creando una regola per l'URL dei servizi Web esterni nel pool Front End, sarà necessario digitare il nome di dominio completo per i servizi Web esterni nel pool Front End, ad esempio lyncwebextpool01.contoso.com.
    
   - Sarà disponibile **un'opzione** Percorso e dovrai immettere **/\\** * qui.
    
   - Dovrai selezionare un **listener SSL** con il certificato pubblico aggiornato.
    
   - **La delega dell'autenticazione** deve essere impostata **su Nessuna delega,** ma l'autenticazione diretta del client **deve** essere consentita.
    
   - La regola deve essere impostata su **Tutti gli utenti**.
    
   - Queste dovrebbero essere tutte le informazioni necessarie per creare questa regola e consentire di procedere.
    
4. Dovrai assicurarti che l'intestazione **host originale** sia inoltrata.
    
5. Sarà necessario impostare anche le porte del server **Web,** quindi eseguire le operazioni seguenti:
    
   - **Reindirizzare le richieste alla porta HTTP** e il numero di porta deve essere **8080**.
    
   - **Reindirizzare le richieste alla porta SSL** e il numero di porta deve essere **4443.**
    
6. Quando tutto è configurato, è necessario salvarli o applicarlo e quindi testare la regola.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Creare una regola di pubblicazione Web per la porta 80 (facoltativo)

1. Apri l'interfaccia proxy inverso.
    
2. Dovrai individuare la posizione nell'interfaccia in cui crei le  regole  di pubblicazione Web e scegliere l'opzione Nuovo o Crea (potrebbe essere in un menu o in una scheda, a seconda della configurazione del proxy inverso). Si sta cercando l'opzione per creare una nuova regola di pubblicazione Web.
    
3. In genere, è necessario immettere le informazioni seguenti:
    
   - **Nome**: il nome della regola
    
   - **Azione regola:** in questo caso si tratta di una regola **Allow,** che consente a qualcosa di passare attraverso il proxy inverso.
    
   - La **regola o** l'opzione di pubblicazione che si sta scegliendo è un singolo sito Web o un servizio di **bilanciamento del carico.**
    
   - Deve essere una connessione non protetta per connettersi al server Web o alla **farm pubblicata.**
    
   - Sarà necessario pubblicare un percorso per Pubblicazione interna e immettere il nome di dominio completo per l'indirizzo **VIP** del servizio di bilanciamento del carico del pool Front End, ad esempio sfb_pool01.contoso.local.
    
   - Devi digitare _ come percorso da pubblicare, ma devi anche _*inoltrare l'intestazione **/\\** host originale***.
    
   - Sarà disponibile un'opzione per informazioni o **dettagli sul nome pubblico** o esterno. Questo è il punto in cui potrai immettere:
    
   - **Accetta richieste**, ma deve essere per il nome di dominio.
    
   - Per **nome**, è necessario immettere **lyncdiscover.** <sipdomain> (questo è l'URL del servizio di individuazione automatica esterno).
    
   - Sarà disponibile **un'opzione** Percorso e dovrai immettere **/\\** * qui.
    
   - Dovrai selezionare un listener Web o consentire al proxy inverso di crearne uno automaticamente.
    
   - **La delega dell'autenticazione** deve essere impostata **su Nessuna delega,** ma l'autenticazione client **diretta non deve** essere consentita.
    
   - La regola deve essere impostata su **Tutti gli utenti**.
    
   - Queste dovrebbero essere tutte le informazioni necessarie per creare questa regola e consentire di procedere.
    
4. Le **porte del server** Web dovranno essere impostate, sarà necessario eseguire le operazioni seguenti:
    
   - **Reindirizzare le richieste alla porta HTTP** e il numero di porta deve essere **8080**.
    
   - **Reindirizzare le richieste alla porta SSL** e il numero di porta deve essere **4443.**
    
5. Quando tutto è configurato, è necessario salvarli o applicarlo e quindi testare la regola.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurare l'individuazione automatica per dispositivi mobili con distribuzioni ibride
<a name="ConfigAutoD"> </a>

Gli ambienti ibridi Skype for Business Server sono ambienti che combinano un ambiente locale e un ambiente O365. Dopo aver Skype for Business Server in un ambiente ibrido, il servizio di individuazione automatica deve essere in grado di individuare un utente da uno di questi ambienti.
  
Per consentire ai client mobili di individuare la posizione di un utente, è necessario configurare il servizio di individuazione automatica con un nuovo URL (Uniform Resource Locator). Ecco come procedere:
  
1. Aprire Skype for Business Server Management Shell.
    
2. Eseguire le operazioni seguenti per ottenere il valore dell'attributo **ProxyFQDN** per l'Skype for Business Server locale:
    
   ```powershell
   Get-CsHostingProvider
   ```

3. Quindi, sempre nella finestra della shell, eseguire:
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Dove [identity] viene sostituito dal nome di dominio dello spazio di indirizzi SIP condiviso.
    
## <a name="test-your-mobility-deployment"></a>Testare la distribuzione per dispositivi mobili
<a name="TestMobility"> </a>

Dopo aver distribuito il servizio per dispositivi mobili Skype for Business Server e il servizio di individuazione automatica di Skype for Business Server, è necessario eseguire una transazione di test per verificare che la distribuzione funzioni correttamente. È possibile eseguire **Test-CsUcwaConference** per testare la capacità di due utenti di creare, partecipare e comunicare in una conferenza. Per eseguire questo test saranno necessari due utenti (reali o di prova) e le relative credenziali complete. Questo comando funzionerà sia per Skype for Business client di Lync Server 2013 che per i client Lync Server 2013.
  
Per i client Lync Server 2010 Skype for Business Server 2015, è necessario eseguire **Test-CsMcxP2PIM** per testare. Gli utenti di Lync Server 2010 dovranno comunque essere utenti effettivi o utenti di test predefiniti e saranno necessarie le credenziali della password.

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Test conferencing for Skype for Business and Lync 2013 mobile clients

1. Accedere come membro del ruolo **CsAdministrator** in qualsiasi computer in cui **Skype for Business Server Management Shell** e **Ocscore** siano installati.
    
2. Avviare la **Skype for Business Server Management Shell** (è possibile digitare il nome nella ricerca o passare a Tutti i **programmi** e sceglierlo).
    
3. Nella riga di comando immettere:
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   È anche possibile impostare le credenziali in uno script e passarle al cmdlet di test. Ecco un esempio di questo esempio.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Test conferencing for Lync 2010 mobile clients

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.

1. Accedere come membro del ruolo **CsAdministrator** in qualsiasi computer in cui **Skype for Business Server Management Shell** e **Ocscore** siano installati.
    
2. Avviare la **Skype for Business Server Management Shell** (è possibile digitare il nome nella ricerca o passare a Tutti i **programmi** e sceglierlo).
    
3. Nella riga di comando immettere:
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   È anche possibile impostare le credenziali in uno script e passarle al cmdlet di test. Ecco un esempio di questo esempio.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Per esaminare ulteriormente le procedure di comando, è possibile consultare [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) e [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Configurare il sistema per le notifiche push
<a name="ConfigPush"> </a>

Le notifiche push, sotto forma di notifiche, icone o avvisi, possono essere inviate a un dispositivo mobile anche quando l'Skype o l'app Lync è inattiva. Ma cosa sono le notifiche push? Si tratta di avvisi di eventi, ad esempio un invito di messaggistica istantanea nuovo o perso, o per una segreteria telefonica ricevuta. Il servizio Skype for Business Server Mobility invia queste notifiche al servizio di notifica Push Skype for Business Server basato su cloud, che quindi invia le notifiche al servizio di notifica Push Microsoft (MSNS) per gli utenti Windows Phone cloud.
  
Questa funzionalità rimane invariata rispetto a Lync Server 2013, ma se si dispone di un Skype for Business Server, è necessario eseguire le operazioni seguenti:
  
- Per un server perimetrale Skype for Business Server, aggiungere un nuovo provider di hosting, Microsoft Skype for Business Online, quindi configurare la federazione del provider di hosting tra l'organizzazione e Skype for Business Online.
    
- Abilitare le notifiche push eseguendo il cmdlet **Set-CsPushNotificationConfiguration.** Per impostazione predefinita, le notifiche push sono disattivate.
    
- Testare la configurazione della federazione e le notifiche push.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurare il server perimetrale Skype for Business per le notifiche push

1. Accedere con un account membro del ruolo **CsAdministrator** a un computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**
    
2. Avviare Skype for Business Server **Management Shell**.
    
3. Aggiungere un Skype for Business Server di hosting online.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Ad esempio:
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Non è possibile avere più di una relazione di federazione con un singolo provider di hosting. Pertanto, se hai già configurato un provider di hosting che ha una relazione di federazione con sipfed.online.lync.com, non aggiungere un altro provider di hosting, anche se l'identità del provider di hosting è diversa da SkypeOnline. 
  
4. Configurare la federazione del provider di hosting tra l'organizzazione e il servizio di notifica Push in Skype for Business Online. Nella riga di comando, è necessario digitare:
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Abilitare le notifiche push

1. Accedere con un account membro del ruolo **CsAdministrator** a un computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**
    
2. Avviare Skype for Business Server **Management Shell**.
    
3. Abilita notifiche push:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Abilita federazione:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Testare la federazione e le notifiche push

1. Accedere con un account membro del ruolo **CsAdministrator** a un computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**
    
2. Avviare Skype for Business Server **Management Shell**.
    
3. Testare la configurazione della federazione:
    
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

Hai la possibilità con Skype for Business Server di determinare chi può usare il servizio Per dispositivi mobili, Chiama tramite lavoro, voice over IP (VoIP) o video, nonché se il WiFi sarà necessario per VoIP o video. Chiama tramite ufficio consente a un utente mobile di usare il proprio numero di telefono dell'ufficio, anziché il numero di cellulare, durante l'esecuzione e la ricezione di chiamate. La persona all'altra estremità della linea non vede il numero di cellulare dell'utente mobile e consente all'utente mobile di evitare i costi delle chiamate in uscita. Quando voIP e video sono impostati, gli utenti possono effettuare chiamate VoIP e video. Le impostazioni per l'utilizzo di WiFi determinano se il dispositivo mobile di un utente sarà necessario per usare una rete WiFi su una rete dati cellulare.
  
Le funzionalità Per dispositivi mobili, Chiamata tramite lavoro e VoIP e video sono tutte abilitate per impostazione predefinita. L'impostazione per richiedere WiFi per VoIP e video è disabilitata. Un amministratore ha la possibilità di modificare questa impostazione, a livello globale, in base al sito o in base all'utente.
  
Per poter usare le funzionalità per dispositivi mobili e Chiamare tramite il lavoro, gli utenti devono essere:
  
- Abilitato per Skype for Business Server
    
- Abilitato per VoIP aziendale.
    
- Assegnato un criterio per dispositivi mobili con **l'opzione EnableMobility** impostata su **True.**
    
Per consentire agli utenti di usare Chiama tramite il lavoro, dovranno anche essere:
  
- Assegnato un criterio vocale con **l'opzione Abilita squillo simultaneo dei** telefoni selezionata.
    
- Assegnato un criterio per dispositivi mobili con **EnableOutsideVoice** impostato su **True.**
    
> [!NOTE]
> Gli utenti che non sono abilitati per VoIP aziendale possono usare i propri dispositivi mobili per effettuare Skype Skype chiamate VoIP o partecipare alle conferenze utilizzando il collegamento Fai clic per partecipare nei dispositivi mobili, se sono impostate le opzioni appropriate per il criterio vocale a cui sono associati. Nell'argomento PIANIFICAZIONE sono disponibili ulteriori dettagli. 
  
### <a name="modify-global-mobility-policy"></a>Modificare i criteri globali per dispositivi mobili

1. Accedere con un account membro del ruolo **CsAdministrator** a un computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**
    
2. Avviare Skype for Business Server **Management Shell**.
    
3. Disattiva l'accesso a Mobilità e Chiamata tramite Lavoro a livello globale digitando:
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > È possibile disattivare Chiama tramite Il lavoro senza disattivare l'accesso a Mobility. Tuttavia, non è possibile disattivare La mobilità senza disattivare anche Chiama tramite il lavoro. 
  
    Per altre info, consulta [Set-CsMobilityPolicy.](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)
    
### <a name="modify-mobility-policy-by-site"></a>Modificare i criteri per dispositivi mobili in base al sito

1. Accedere con un account membro del ruolo **CsAdministrator** a un computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**
    
2. Avviare Skype for Business Server **Management Shell**.
    
3. Puoi creare criteri a livello di sito, disattivare VoIP e video, abilitare Richiedi WiFi per ip audio e Richiedi WiFi per IP Video per sito. Digitare:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Per ulteriori informazioni, [vedere New-CsMobilityPolicy.](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)
    
### <a name="modify-mobility-policy-by-user"></a>Modificare i criteri per dispositivi mobili in base all'utente

1. Accedere con un account membro del ruolo **CsAdministrator** a un computer in cui sono installati **Skype for Business Server Management Shell** e **Ocscore.**
    
2. Avviare Skype for Business Server **Management Shell**.
    
3. Creare criteri per dispositivi mobili a livello di utente e disattivare Mobilità e Chiamata tramite lavoro per utente. Digitare:
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Un altro esempio con dati di esempio:
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > È possibile disattivare Chiama tramite Il lavoro senza disattivare l'accesso a Mobility. Tuttavia, non è possibile disattivare La mobilità senza disattivare anche Chiama tramite il lavoro. 
