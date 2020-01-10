---
title: Distribuire la connettività Skype in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Riepilogo: informazioni su come connettere Skype for Business Server con Skype consumer. Nota anche come connettività Skype.'
ms.openlocfilehash: 41a183912604c5880dfa46529f9034bc0673288d
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003076"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Distribuire la connettività Skype in Skype for Business Server

**Riepilogo:** Informazioni su come connettere Skype for Business Server con Skype consumer. Nota anche come connettività Skype.
  
Questo articolo illustra la distribuzione per la connettività Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Panoramica della connettività Skype per professionisti IT

La connettività Skype offre agli utenti di Skype for business la possibilità di cercare e aggiungere utenti Skype. La connettività Skype è una funzionalità di Skype for business che consente di abilitare la ricerca della Federazione e della directory con gli utenti Skype. Dopo aver abilitato la connettività Skype gli utenti di Skype for business saranno in grado di cercare e aggiungere utenti Skype.
  
## <a name="skype-directory-search"></a>Ricerca nell'elenco Skype

La funzionalità di ricerca della directory Skype offre agli utenti di Skype for business la possibilità di cercare i contatti Skype. La funzionalità di ricerca consente agli utenti di eseguire ricerche usando le operazioni seguenti:
  
- **Eseguire una ricerca in base al nome visualizzato, ad esempio "John Doe"** -questo potrebbe restituire molti risultati, quindi non è possibile trovare ciò che si sta cercando.
    
- **Ricerca in base al nome visualizzato più posizione, ad esempio "John Doe in Barcelona"-in** questo modo si restringeranno sensibilmente i risultati della ricerca.
    
- **Eseguire una ricerca tramite posta elettronica, ad esempio "johndoe@outlook.com"** -questo dovrebbe restituire un risultato nella maggior parte dei casi; quello che corrisponde esattamente al messaggio di posta elettronica specificato. Ma se lo stesso messaggio di posta elettronica è associato a più account, potrebbero essere restituiti più risultati.
    
- **Eseguire una ricerca in base al numero di telefono, ad esempio "123-123-1234"** -questo dovrebbe restituire un risultato nella maggior parte dei casi; quello che corrisponde esattamente al telefono specificato. Il numero di telefono deve includere il codice paese (ad esempio 1-xxx-yyy-zzzz). Se lo stesso numero di telefono è associato a più di un account, potrebbero essere restituiti più risultati.
    
- **Eseguire una ricerca in base al nome Skype, ad esempio "JohnDoe1456"** -se viene trovata la corrispondenza esatta, verrà restituito come primo risultato. Possono essere restituite altre possibili corrispondenze "nome".
    
    > [!NOTE]
    > La ricerca nella directory Skype deve essere in grado di comunicare con gli indirizzi IP seguenti sulla porta 443:104.40.75.246, 23.101.135.34 e 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matrice di distribuzione supportata per la ricerca nell'elenco Skype

La tabella seguente illustra il supporto per la ricerca nella directory Skype.
  

||**Front-end di Skype for Business Server**|**Lync Server 2013 (o versioni precedenti) front-end**|**Commenti**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge  <br/> |Supportati  <br/> |Non supportato  <br/> |Skype for Business Server e Edge sono prerequisiti per la ricerca nella directory Skype  <br/> |
|Skype for Business Server Edge + Lync Server 2013 Edge distribuito affiancato  <br/> |Supportati  <br/> |Non supportato  <br/> |Il traffico di ricerca della directory Skype passa attraverso Skype for Business Server Edge Server. Il traffico federativo passa attraverso Edge configurato dall'amministratore. Ad esempio, l'amministratore può scegliere di continuare a inviare il traffico federativo tramite Lync Server 2013 Edge Server che non supportano la ricerca nella directory Skype.  <br/> |
|Edge di Lync Server 2013 (o precedente)  <br/> |Non supportato  <br/> |Non supportato  <br/> ||
   
> [!NOTE]
> Il servizio AddressBook in uso su Skype for Business Server front-end trova il bordo per l'esistenza della porta di ricerca Skype 4443 nel server perimetrale. 
  
> [!NOTE]
> Nel caso in cui un cliente disponga di più siti nella distribuzione locale e se ha distribuito un solo server Edge/pool di Skype for Business Server, il traffico di ricerca da tutti i siti passa attraverso il singolo Edge Server disponibile. L'amministratore deve assicurarsi che i pool di tutti i siti possano accedere al pool o al server Edge di Skype for Business Server distribuito. 
  
> [!NOTE]
> Il servizio Skype graph consente di limitare le richieste di ricerca da qualsiasi cliente locale o Office 365 se il tasso di richiesta supera 15 richieste al secondo. 
  
> [!NOTE]
> Per i clienti di grandi dimensioni aziendali locali, i domini dovranno essere whitelist con il servizio di ricerca Skype per consentire tariffe più elevate. 
  
> [!NOTE]
> Skype for Business Server strozza le richieste in arrivo, se sono presenti troppe richieste in sospeso nella coda. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Distribuzione di connettività Skype per Skype for business online in Office 365

La connettività Skype è anche una funzionalità di Skype for business online, che fa parte di Office 365. È possibile abilitare la funzionalità di connettività Skype dall'area di amministrazione di Skype for business all'interno del portale di Office 365.
  
Per Office 365 medie imprese, Office 365 Enterprise, Office 365 Education e Office 365 per enti pubblici: accedere al portale di Office 365 e passare all'area di amministrazione di Skype for business. Accedere a comunicazioni esterne. In provider di servizi di messaggistica istantanea pubblici fare clic su Abilita. Se si vuole controllare l'accesso individuale degli utenti alla connettività Skype, è possibile modificarne le impostazioni di comunicazione esterna per singoli utenti.
  
Per Office 365 Small Business Premium: accedere a Office 365 e accedere alle impostazioni \> \> di messaggistica istantanea, riunioni e conferenze del servizio di amministrazione. Attivare le comunicazioni esterne. L'interruttore comunicazioni esterne attiva sia la connettività Skype che le comunicazioni con altre organizzazioni che usano Skype for business.
  
Per altre informazioni sull'amministrazione di Skype for business online, vedere:
  
- [Permettere agli utenti di contattare utenti Skype for Business esterni](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Cosa fare se non è possibile usare i contatti esterni di Skype for business o Skype](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Aggiungere un contatto in Skype for business](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Amministratori: Configurare le impostazioni di Skype for Business online per singoli utenti](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Distribuzione di connettività Skype per Skype for Business Server

Skype for Business Server usa l'architettura di accesso federativo per supportare la connettività con Skype. Questa connettività consente agli utenti di Skype for Business Server di aggiungere Skype. I client Skype possono anche aggiungere utenti Skype for business all'elenco contatti. In base ai criteri impostati amministrativamente in Skype for Business Server gli utenti potranno comunicare usando la messaggistica istantanea, vedere la presenza dell'altro e avviare chiamate audio e video. La connettività Skype è anche una funzionalità di Skype for business online e può essere abilitata per i clienti Skype for business online dall'Administration Center di Skype for business nel portale di Office 365.
  
> [!NOTE]
> Se Skype for Business Server è già configurato per la connessione con Windows Messenger tramite la connettività di messaggistica istantanea pubblica (PIC), la distribuzione è già configurata per la connettività Skype. L'unica modifica che potrebbe essere necessaria è la ridenominazione della voce PIC di Messenger esistente in Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Il sito di provisioning della connettività di messaggistica istantanea pubblica di Skype for Business Server non è più disponibile

Il sito usato in precedenza per la distribuzione manuale della Federazione tra le distribuzioni locali di Skype for business e Skype non è più necessario e verrà arrestato in 8/15/2019. La Federazione con Skype usa ora l'individuazione dei partner federati, che è lo stesso meccanismo necessario per la Federazione con Skype for business online.

La comunicazione tra qualsiasi distribuzione locale di Skype for business e gli utenti Skype tramite l'infrastruttura di messaggistica istantanea pubblica esistente richiede ora la configurazione del server perimetrale locale per essere compatibile con Skype for business online.

> [!NOTE]
> La maggior parte dei clienti non deve eseguire alcuna azione, incluse tutte le distribuzioni che si federano con Skype for business online.
  
Le distribuzioni locali sono necessarie per pubblicare un record SRV DNS federativo per ogni dominio che ospitano. Le linee guida sono disponibili nella [pianificazione DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning). Ogni dominio deve risolvere la query DNS SRV in un nome di dominio completo del server perimetrale che soddisfa una corrispondenza di suffisso di primo livello del dominio. Consideriamo ad esempio il dominio "contoso.com":

|**Nomi di dominio completi validi**|**Commento**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |In ogni caso, l'FQDN esatto deve essere presente in SN o SAN del certificato esterno installato nel server perimetrale.   |
|access.contoso.com   ||
|**Nomi di dominio completi non validi**|**Motivo**|
|sip.contoso-edge.com   |Non corrisponde a un suffisso.  |
|sip.it.contoso.com   |Non corrisponde a un suffisso di primo livello.   |

Ulteriori indicazioni per i certificati esterni sono disponibili nella [pianificazione dei certificati](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>FAQ

**Perché il sito Web di provisioning viene arrestato?**
Il meccanismo di provisioning dei messaggi istantanei pubblici (pic.lync.com) distribuito in 2006 non è più utilizzabile e verrà arrestato in 8/15/2019. La Federazione di messaggistica istantanea pubblica assumerà invece lo stesso modello federativo usato da Skype for business online, noto come "partner Discovery", in cui una distribuzione locale è pubblicamente individuabile dai record SRV DNS federativi.

**Questa modifica significa che la Federazione di messaggistica istantanea pubblica è deprecata?**
Non. La Federazione di messaggistica istantanea pubblica continuerà a essere supportata per molti anni, probabilmente finché il prodotto locale Skype for business non raggiungerà la fine del ciclo di vita.

**La nostra azienda ha una relazione ibrida (spazio di indirizzi condiviso) con Skype for business online, siamo interessati?**
No, dato che sei già in Federazione con Skype for business online, questa modifica non influirà su di te.
 
**Questa modifica significa che la società deve abilitare la Federazione con Skype for business online?**
Non. Se le impostazioni proxy di Edge Server non abilitano la Federazione con il provider di hosting di Skype for business online (sipfed.online.lync.com), questa modifica non influirà. Tuttavia, gli stessi requisiti di DNS e certificati applicati alla Federazione con Skype for business online ora si applicano anche alla Federazione con gli utenti Skype.
 
**La nostra società è di grandi dimensioni e non può modificare la configurazione dei bordi a causa di normative/conformità/etc... Cosa possiamo fare?**
Qualsiasi organizzazione locale che non può modificare la configurazione del server perimetrale come specificato dovrebbe raggiungere il supporto tecnico al più presto possibile.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Abilitazione della Federazione e della connettività per messaggistica istantanea pubblica (PIC)

Ora attiva l'ambiente di Skype for Business Server e le attività amministrative necessarie per configurare la connettività Skype. In questa sezione presupponiamo che l'amministratore abbia implementato Skype for Business Server e l'accesso esterno configurato, noto anche come Edge Server. 
  
Per abilitare la Federazione e PIC sono necessari tre passaggi principali. Questi sono:
  
1. Configurare la Federazione e PIC
    
2. Configurare almeno un criterio per supportare l'accesso degli utenti federati
    
3. Configurare l'impostazione del provider di Skype PIC
    
#### <a name="1-configure-federation-and-pic"></a>1. configurare la Federazione e PIC

Per consentire agli utenti Skype di comunicare con gli utenti di Skype for business nell'organizzazione, è necessaria la Federazione. La connettività di messaggistica istantanea pubblica (PIC) è una classe di Federazione e deve essere configurata per consentire agli utenti di Skype for business di comunicare con gli utenti Skype. La Federazione e il PIC sono configurati tramite il pannello di controllo di Skype for Business Server.
  
> [!NOTE]
> La Federazione PIC non è più supportata dalle versioni di prodotto precedenti a Lync Server 2010 (Live Communication Server, Office Communications Server). Le piattaforme supportate per la Federazione PIC includono Skype for Business Server, Lync Server 2013 e Lync Server 2010. 
  
Per consentire agli utenti Skype di comunicare con gli utenti di Skype for business nell'organizzazione, è necessaria la Federazione. La connettività di messaggistica istantanea pubblica (PIC) è una classe di Federazione e deve essere configurata per consentire agli utenti di Skype for Business Server di comunicare con utenti Skype. La Federazione e il PIC sono configurati usando la finestra di dialogo configurazione Edge del pannello di controllo di Skype for Business Server, come illustrato nella figura.
  
![Definire un nuovo pool di bordi](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Gli attributi EnableSkypeIdRouting e EnableSkypeDirectorySearch devono essere impostati su true nelle impostazioni del provider pubblico (vedere le istruzioni successive) per la ricerca per il lavoro. 
  
In questo articolo vengono completate le attività amministrative che devono essere eseguite nel server. Ora sei configurato per la connettività Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. configurare almeno un criterio per supportare l'accesso degli utenti federati

Usando il pannello di controllo di Skype for Business Server, un amministratore deve configurare uno o più criteri di accesso degli utenti esterni per controllare se gli utenti Skype possono collaborare con gli utenti di Skype for Business Server interni.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. configurare l'impostazione del provider di Skype PIC

Usando Skype for Business Server Management Shell, un amministratore deve configurare il criterio client Skype for business per visualizzare Skype come provider di PIC aggiuntivo. 
  
> [!NOTE]
> Gli utenti dei provider di servizi di messaggistica istantanea pubblica (PIC) non possono partecipare alla messaggistica istantanea o alle conferenze dell'organizzazione finché non si configura almeno un criterio (passaggio 2, in precedenza in questa procedura) per supportare la connettività di messaggistica istantanea pubblica. 
  
Per le nuove installazioni è possibile configurare la connettività Skype abilitando un provider pubblico Skype tramite il pannello di controllo di Skype for Business Server, come illustrato nella figura.
  
![Provider federati SIP](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Per configurare la connettività Skype quando si esegue l'aggiornamento a Skype for Business Server, è necessario rimuovere e aggiungere di nuovo il provider pubblico Skype esistente. 
  
La configurazione della connettività Skype può essere eseguita anche usando solo PowerShell. Per configurare la connettività Skype tramite PowerShell:
  
1. Da un server front-end Skype for Business Server aprire Skype for Business Server Management Shell.
    
2. Eseguire i due comandi seguenti:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Se non si dispone già di un provider PIC nell'ambiente e si crea un nuovo provider PIC, non è necessario eseguire il cmdlet Remove-CsPublicProvider. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Quali sono i parametri meno ovvi?
    
   - ProxyFqdn: posizione di Skype Federation Edge (di proprietà/gestito da Microsoft)
    
   - IconURL: icona usata dal client &amp; Lync Skype for business per identificare visivamente i contatti Skype
    
   - NameDecorationRoutingDomain e NameDecorationExcludedDomainList: l'impostazione di questi consente agli utenti di immettere i MSAs degli utenti Skype senza che sia necessario sapere "decorare" i domini non Microsoft con "msn.com". In questo articolo viene eliminata la necessità di digitare "User (contoso. com) @msn. com" per tutti i domini non presenti in ExcludedDomainList. Il client SfB formatterà automaticamente la MSA se il dominio non è presente nell'elenco escluso. Sono stati aggiunti i domini di account Microsoft più comuni all'elenco escluso.
    
     > [!NOTE]
     > Il provider pubblico deve essere rimosso e aggiunto nuovo se vengono apportate modifiche. Non sono consentite modifiche sul posto. 
  
     > [!NOTE]
     > Aggiunta in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, NameDecorationRoutingDomain e NameDecorationExcludedDomainList migliorano la situazione in cui gli utenti di Lync aggiungono contatti Skype necessari per "decorare" i domini non Microsoft per identificarli e instradarli a Skype (il formato di: User (contoso. com) @msn. com). Queste nuove impostazioni consentiranno la formattazione automatica dell'invio dell'utente dell'indirizzo nella finestra di dialogo "Aggiungi contatto Skype" con NameDecorationRoutingDomain (che deve essere impostato su msn.com) se non contiene i domini nel NameDecorationExcludedDomainList ( Attualmente possiamo supportare msn.com, live.com, Hotmail.com, outlook.com). 
  
3. Da un client Skype for business gli utenti possono ora cercare e aggiungere un utente Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Matrice di interoperabilità e client

La tabella seguente descrive lo stato di interoperabilità tra l'ultima versione di Skype consumer e l'ultima versione di Skype for business.
  

|**Client Skype**|**Aggiungere contatti, messaggistica istantanea, presenza, audio e videochiamate**|**Commento**|
|:-----|:-----|:-----|
|Desktop di Windows Skype  <br/> |7,6 o versioni successive, Windows XP e versioni successive  <br/> |**Nuovo**: supporto aggiunto per il client Windows Skype in esecuzione in Windows XP e Windows Vista **(richiede l'ultima versione del client 7,26 o successiva)** <br/> |
|Skype mobile-telefono e Tablet Android  <br/> |6,19 o versione successiva, con sistema operativo Android 4.0.3 o versioni successive  <br/> |I dispositivi low spec potrebbero non supportare le videochiamate  <br/> |
|Skype mobile-iOS  <br/> |6,11 o versione successiva, in IOS 7 o versioni successive  <br/> |Non sono supportati iPhone 4 e versioni precedenti, iPod 4a generazione e versioni precedenti, iPad di 1a generazione  <br/> |
|Skype Mac  <br/> |7,19 o versioni successive, in Mac OS X 10,9 (Mavericks) o versioni successive  <br/> |Richiede Mac OSX 10,9 o versione successiva  <br/> |
|App Skype Universal Windows (Windows 10) desktop e dispositivi mobili  <br/> |Windows 10 (Redstone 1 aggiornamento o versioni successive)  <br/> |L'app universale Windows riceverà l'aggiornamento in autunno 2016 aggiungendo il supporto per l'interoperabilità  <br/> |
   
La tabella seguente descrive lo stato di interoperabilità tra l'ultima versione di Skype for business e la versione più recente di Skype consumer. 
  
|**Client**|**Ricerca e aggiunta di contatti nella directory Skype**|**Skype A/V, interoperabilità di messaggistica istantanea**|
|:-----|:-----|:-----|
|Skype for business  <br/> |Sì  <br/> |Sì  <br/> |
| Skype for Business su Mac  <br/> |Può aggiungere (nessuna ricerca)  <br/> |Sì  <br/> |
|Lync desktop 2013  <br/> |Può aggiungere (nessuna ricerca)  <br/> |Sì  <br/> |
|Lync Web App-online e locale  <br/> |N/D  <br/> |N/D  <br/> |
|Lync mobile-Windows Phone  <br/> |Prossimamente  <br/> |Sì  <br/> |
|Lync mobile-Android  <br/> |Prossimamente  <br/> |Sì  <br/> |
|Lync mobile-iOS  <br/> |Prossimamente  <br/> |Sì  <br/> |
|Sistema di sala Lync  <br/> |Prossimamente  <br/> |Sì  <br/> |
|App Lync Modern (Win 8,1)  <br/> |Sì  <br/> |Sì  <br/> |
|Lync Mac 2011  <br/> |Può aggiungere (nessuna ricerca)  <br/> |Sì  <br/> |
|Lync desktop 2010  <br/> |Può aggiungere (nessuna ricerca)  <br/> |Sì  <br/> |
|Lync Phone Edition  <br/> |N/D  <br/> |N/D  <br/> |
|Assistente di Lync  <br/> |N/D  <br/> |N/D  <br/> |
   

