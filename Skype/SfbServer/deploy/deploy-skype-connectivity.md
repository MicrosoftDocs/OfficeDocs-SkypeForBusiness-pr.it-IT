---
title: Distribuire la connettività Skype in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Riepilogo: informazioni su come connettere Skype for Business Server con Skype consumer. Nota anche come connettività Skype.'
ms.openlocfilehash: 2cf124c340218a352f55fa1c09302a0d0f1d972a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780065"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Distribuire la connettività Skype in Skype for Business Server

**Riepilogo:** Informazioni su come connettere Skype for Business Server con Skype consumer. Nota anche come connettività Skype.
  
In questo articolo viene illustrata la distribuzione per la connettività Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Panoramica della connettività Skype per professionisti IT

La connettività Skype fornisce agli utenti di Skype for business la possibilità di cercare e aggiungere utenti Skype. La connettività Skype è una funzionalità di Skype for business che consente di abilitare la Federazione e la ricerca directory con gli utenti Skype. Dopo aver abilitato la connettività Skype gli utenti di Skype for business saranno in grado di cercare e aggiungere utenti Skype.
  
## <a name="skype-directory-search"></a>Ricerca directory Skype

La funzionalità di ricerca della directory Skype fornisce agli utenti di Skype for business la possibilità di cercare contatti Skype. La funzionalità di ricerca consente agli utenti di eseguire ricerche utilizzando le opzioni seguenti:
  
- **Ricerca in base al nome visualizzato, ad esempio "John Doe"** -potrebbe essere restituito un numero elevato di risultati, quindi non è possibile trovare ciò che si sta cercando.
    
- **Ricerca in base al nome visualizzato e alla posizione, ad esempio "John Doe in Barcelona"-in** questo modo i risultati della ricerca saranno limitati considerevolmente.
    
- **Ricerca tramite posta elettronica, ad esempio "johndoe@outlook.com"** -questo dovrebbe restituire un risultato nella maggior parte dei casi; quella che corrisponde esattamente al messaggio di posta elettronica specificato. Se invece lo stesso messaggio di posta elettronica è associato a più di un account, è possibile che vengano restituiti più risultati.
    
- **Cerca per numero di telefono, ad esempio "123-123-1234"** -questo dovrebbe restituire un risultato nella maggior parte dei casi; corrisponde esattamente a quello corrispondente al telefono specificato. Il numero di telefono deve includere il codice paese (ad esempio, 1-xxx-yyy-zzzz). Se lo stesso numero di telefono è associato a più di un account, è possibile che vengano restituiti più risultati.
    
- **Ricerca in base al nome Skype, ad esempio "JohnDoe1456"** -se viene trovata la corrispondenza esatta, verrà restituito come primo risultato. Possono essere restituite altre possibili corrispondenze "nome".
    
    > [!NOTE]
    > La ricerca nella directory Skype deve essere in grado di comunicare con i seguenti indirizzi IP sulla porta 443:104.40.75.246, 23.101.135.34 e 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matrice di distribuzione supportata per la ricerca nella directory di Skype

Nella tabella seguente viene illustrato il supporto per la ricerca di directory Skype.
  

||**Skype for Business Server front-end**|**Lync Server 2013 (o versioni precedenti) front-end**|**Comments**|
|:-----|:-----|:-----|:-----|
|Server Edge di Skype for business  <br/> |Supportato  <br/> |Non supportata  <br/> |Skype for Business Server e Edge sono prerequisiti per la ricerca di directory Skype  <br/> |
|Skype for Business Server Edge + Lync Server 2013 Edge distribuito affiancato  <br/> |Supportato  <br/> |Non supportata  <br/> |Il traffico di ricerca di Skype directory scorre attraverso i server perimetrali di Skype for Business Server. Il traffico federativo passa attraverso Edge configurato dall'amministratore. Ad esempio, l'amministratore può scegliere di continuare a inviare traffico federativo attraverso i server perimetrali di Lync Server 2013 che non supportano la ricerca nella directory Skype.  <br/> |
|Edge di Lync Server 2013 (o versioni precedenti)  <br/> |Non supportato  <br/> |Non supportato  <br/> ||
   
> [!NOTE]
> Il servizio AddressBook in esecuzione su Skype for Business Server front end consente di individuare il server perimetrale in base all'esistenza della porta di ricerca di Skype 4443 nel computer perimetrale. 
  
> [!NOTE]
> Nel caso in cui un cliente disponga di più siti nella distribuzione locale e, se è stato distribuito un solo server perimetrale o un pool di Skype for Business Server, il traffico di ricerca da tutti i siti passerà attraverso il server perimetrale singolo disponibile. L'amministratore deve accertarsi che i pool di tutti i siti possano accedere al server perimetrale/pool di Skype for Business Server distribuito. 
  
> [!NOTE]
> Il servizio Skype graph consente di limitare le richieste di ricerca da qualsiasi cliente locale o Microsoft 365 o Office 365 se la frequenza delle richieste supera le 15 richieste al secondo. 
  
> [!NOTE]
> Per i clienti locali di grandi dimensioni, i domini dovranno essere whitelist con il servizio di ricerca Skype per consentire tariffe più elevate. 
  
> [!NOTE]
> Skype for Business Server strozza le richieste in arrivo, se nella coda sono presenti troppe richieste in sospeso. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Distribuzione della connettività Skype per Skype for business online in Office 365

La connettività Skype è anche una funzionalità di Skype for business online, che fa parte di Office 365. È possibile abilitare la funzionalità di connettività Skype dal centro di amministrazione di Skype for business all'interno dell'interfaccia di amministrazione di Microsoft 365.
  
Per Office 365 medie imprese, Office 365 Enterprise, Office 365 Education e Office 365 for Government: accedere all'interfaccia di amministrazione di Microsoft 365 e passare all'interfaccia di gestione di Skype for business. Passare a comunicazioni esterne. In provider di servizi di messaggistica istantanea fare clic su Abilita. Se si desidera controllare l'accesso di singoli utenti alla connettività Skype, è possibile modificarne le impostazioni di comunicazione esterna.
  
Per Office 365 Small Business Premium: accedere a Office 365 e passare a impostazioni \> \> del servizio di amministrazione per messaggistica istantanea, riunioni e conferenze. Attiva comunicazioni esterne. L'opzione comunicazioni esterne attiva sia la connettività Skype sia le comunicazioni con altre organizzazioni che utilizzano Skype for business.
  
Per ulteriori informazioni su amministrazione di Skype for business online, vedere:
  
- [Permettere agli utenti di contattare utenti Skype for Business esterni](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Cosa provare se non si riesce a contattare Skype for business o contatti esterni Skype](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Aggiungere un contatto in Skype for business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Amministratori: configurare le impostazioni di Skype for business per singoli utenti](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Distribuzione della connettività Skype per Skype for Business Server

Skype for Business Server utilizza l'architettura di accesso federativo per supportare la connettività con Skype. Questa connettività consente agli utenti di Skype for Business Server di aggiungere Skype. I client Skype possono inoltre aggiungere gli utenti di Skype for business all'elenco dei contatti. In base ai criteri impostati amministrativamente in Skype for Business Server gli utenti saranno in grado di comunicare utilizzando la messaggistica istantanea, vedere reciprocamente la presenza e avviare chiamate audio e video. La connettività Skype è anche una funzionalità di Skype for business online e può essere abilitata per i clienti Skype for business online dall'interfaccia di amministrazione di Skype for business all'interno dell'interfaccia utente di Microsoft 365.
  
> [!NOTE]
> Se Skype for Business Server è già configurato per la connessione con Windows Messenger tramite la connettività per la messaggistica istantanea pubblica, la distribuzione è già configurata per la connettività Skype. L'unica modifica che è possibile prendere in considerazione è quella di rinominare la voce del PIC Messenger esistente come Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Il sito di provisioning di connettività per la messaggistica istantanea pubblica di Skype for Business Server non è più disponibile

Il sito utilizzato in precedenza per il provisioning della Federazione manualmente tra le distribuzioni locali di Skype for business e Skype non è più necessario e verrà interrotto il 8/15/2019. La Federazione con Skype ora utilizza l'individuazione dei partner federati, che è lo stesso meccanismo necessario per la Federazione con Skype for business online.

La comunicazione tra qualsiasi distribuzione di Skype for business locale e gli utenti Skype tramite l'infrastruttura di messaggistica istantanea pubblica esistente richiede che la configurazione del server perimetrale locale sia compatibile con Skype for business online.

> [!NOTE]
> Per la maggior parte dei clienti non è necessaria alcuna azione, incluse tutte le distribuzioni che si configurano con Skype for business online.
  
Le distribuzioni locali sono necessarie per pubblicare un record DNS di Federazione SRV per ogni dominio che ospitano. Le linee guida sono disponibili nella [pianificazione DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning). Ogni dominio deve essere risolto dalla query DNS SRV a un FQDN del server perimetrale che soddisfa una corrispondenza di suffisso di primo livello del dominio. Si consideri, ad esempio, il dominio "contoso.com":

|**FQDN validi**|**Commento**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |In ogni caso, il nome di dominio completo esatto deve essere presente in SN o SAN del certificato esterno installato nel server perimetrale.   |
|access.contoso.com   ||
|**FQDN non validi**|**Motivo**|
|sip.contoso-edge.com   |Non corrisponde a un suffisso.  |
|sip.it.contoso.com   |Non corrisponde a un suffisso di primo livello.   |

Ulteriori indicazioni sui certificati esterni sono disponibili nella [pianificazione dei certificati](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>Domande frequenti

**Perché è in corso la chiusura del sito Web di provisioning?**
Il meccanismo di provisioning della messaggistica istantanea pubblica (pic.lync.com) distribuito in 2006 non è più utilizzabile e verrà interrotto su 8/15/2019. La Federazione di messaggistica istantanea pubblica assumerà invece lo stesso modello di Federazione utilizzato da Skype for business online, noto come "partner Discovery", in cui una distribuzione locale è pubblicamente individuabile dai propri record DNS di Federazione SRV.

**Questa modifica significa che la Federazione di messaggistica istantanea pubblica è obsoleta?**
No. La Federazione di messaggistica istantanea pubblica continuerà a essere supportata per molti anni, probabilmente fino a quando il prodotto Skype for business in locale raggiungerà la fine della vita.

**La nostra azienda ha una relazione ibrida (spazio di indirizzi condiviso) con Skype for business online, ne siamo stati coinvolti?**
No, dal momento che si è già in Federazione con Skype for business online, questa modifica non influirà sull'utente.
 
**Questa modifica significa che la nostra azienda deve abilitare la Federazione con Skype for business online?**
No. Se le impostazioni del proxy del server perimetrale non consentono la Federazione con il provider di hosting di Skype for business online (sipfed.online.lync.com), questa modifica non avrà alcun effetto. Tuttavia, gli stessi requisiti di certificato e DNS che si applicano alla Federazione con Skype for business online ora si applicano anche alla Federazione con gli utenti di Skype.
 
**La nostra azienda è di grandi dimensioni e non è in grado di modificare la configurazione del perimetro a causa di normative/conformità/ecc. Cosa possiamo fare?**
Tutte le organizzazioni locali che non possono modificare la configurazione del server perimetrale, come specificato, devono raggiungere il supporto tecnico al più presto possibile.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Abilitazione della Federazione e della connettività per la messaggistica istantanea pubblica (PIC)

Ora concentrati sull'ambiente di Skype for Business Server e sulle attività amministrative necessarie per configurare la connettività Skype. In questa sezione si presuppone che l'amministratore abbia distribuito Skype for Business Server e abbia configurato l'accesso esterno, noto anche come server perimetrali. 
  
Per abilitare la Federazione e PIC, sono necessari tre passaggi principali. Si tratta di:
  
1. Configurazione della Federazione e del PIC
    
2. Configurare almeno un criterio per il supporto dell'accesso utente federato
    
3. Configurare l'impostazione di Skype PIC provider
    
#### <a name="1-configure-federation-and-pic"></a>1. configurare la Federazione e PIC

La Federazione è necessaria per consentire agli utenti di Skype di comunicare con gli utenti di Skype for business nell'organizzazione. La connettività per la messaggistica istantanea pubblica (PIC) è una classe di Federazione e deve essere configurata per consentire agli utenti di Skype for business di comunicare con gli utenti di Skype. La Federazione e il PIC sono configurati utilizzando il pannello di controllo di Skype for Business Server.
  
> [!NOTE]
> La Federazione PIC non è più supportata dalle versioni di prodotto precedenti a Lync Server 2010 (Live Communication Server, Office Communications Server). Le piattaforme supportate per la Federazione PIC includono Skype for Business Server, Lync Server 2013 e Lync Server 2010. 
  
La Federazione è necessaria per consentire agli utenti di Skype di comunicare con gli utenti di Skype for business nell'organizzazione. La connettività per la messaggistica istantanea pubblica (PIC) è una classe di Federazione e deve essere configurata per consentire agli utenti di Skype for Business Server di comunicare con gli utenti di Skype. La Federazione e il PIC sono configurati utilizzando la finestra di dialogo configurazione Edge del pannello di controllo di Skype for Business Server, come mostrato nella figura.
  
![Definire un nuovo pool di server perimetrali](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Gli attributi EnableSkypeIdRouting e EnableSkypeDirectorySearch devono essere impostati su true nelle impostazioni del provider pubblico (vedere le istruzioni successive) per il funzionamento della ricerca. 
  
Vengono completate le attività amministrative che devono essere eseguite sul server. Ora è stato configurato per la connettività Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. configurare almeno un criterio per il supporto dell'accesso utente federato

Usando il pannello di controllo di Skype for Business Server, un amministratore deve configurare uno o più criteri di accesso degli utenti esterni per controllare se gli utenti di Skype possono collaborare con gli utenti interni di Skype for Business Server.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. configurare l'impostazione di Skype PIC provider

Usando Skype for Business Server Management Shell, un amministratore deve configurare il criterio client Skype for business per visualizzare Skype come un ulteriore provider PIC. 
  
> [!NOTE]
> Gli utenti dei provider di servizi di connettività di messaggistica istantanea pubblica non possono partecipare a conferenze o messaggistica istantanea nell'organizzazione fino a quando non si configura anche almeno un criterio (passaggio 2, più indietro in questa procedura) per supportare la connettività per la messaggistica istantanea pubblica. 
  
Per le nuove installazioni è possibile configurare la connettività Skype abilitando un provider pubblico Skype utilizzando il pannello di controllo di Skype for Business Server, come mostrato nella figura.
  
![Provider federati SIP](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Per configurare la connettività Skype quando si effettua l'aggiornamento a Skype for Business Server, è necessario rimuovere e aggiungere di nuovo il provider pubblico Skype esistente. 
  
La configurazione della connettività Skype può essere realizzata anche utilizzando solo PowerShell. Per configurare la connettività Skype tramite PowerShell:
  
1. Da un server front end di Skype for Business Server, aprire la shell di gestione di Skype for Business Server.
    
2. Eseguire i due comandi seguenti:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Se non si dispone già di un provider PIC nel proprio ambiente e si crea un nuovo provider PIC, non è necessario eseguire il cmdlet Remove-CsPublicProvider. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Che cosa fanno i parametri meno evidenti?
    
   - ProxyFqdn: posizione di Skype Federation Edge (di proprietà/gestito da Microsoft)
    
   - IconURL: icona utilizzata dal client &amp; Lync Skype for business per identificare visivamente i contatti Skype
    
   - NameDecorationRoutingDomain e NameDecorationExcludedDomainList: questa impostazione consente agli utenti di immettere MSAs degli utenti di Skype senza dover conoscere i domini "decorazione" non Microsoft con "msn.com". In questo modo viene eliminata la necessità di digitare "User (contoso. com) @msn. com" per tutti i domini che non sono presenti in ExcludedDomainList. Se il dominio non è incluso nell'elenco escluso, il client questo formatterà automaticamente la MSA. Sono stati aggiunti i domini dell'account Microsoft più comuni all'elenco escluso.
    
     > [!NOTE]
     > Il provider pubblico deve essere rimosso e aggiunto nuovo se vengono apportate modifiche. Non sono consentite modifiche sul posto. 
  
     > [!NOTE]
     > Aggiunta in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, NameDecorationRoutingDomain e NameDecorationExcludedDomainList migliorano la situazione in cui gli utenti di Lync aggiungono contatti Skype necessari per "decorare" i domini non Microsoft per identificare e instradarli a Skype (il formato di: User (contoso. com) @msn. com). Queste nuove impostazioni consentiranno la formattazione automatica della finestra di dialogo "Aggiungi contatto Skype" con il NameDecorationRoutingDomain (che dovrebbe essere impostato su msn.com) se non contiene i domini nel NameDecorationExcludedDomainList (attualmente in grado di supportare msn.com, live.com, hotmail.com, outlook.com). 
  
3. Da un client Skype for business, gli utenti possono ora cercare e aggiungere un utente Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Matrice di interoperabilità e client

Nella tabella seguente viene descritto lo stato di interoperabilità tra la versione più recente di Skype consumer e la versione più recente di Skype for business.
  

|**Client Skype**|**Aggiungere la chiamata a contatti, messaggistica istantanea, presenza, audio e video**|**Commento**|
|:-----|:-----|:-----|
|Desktop di Windows Skype  <br/> |7,6 o versioni successive, Windows XP e versioni successive  <br/> |**Nuovo**: supporto aggiunto per il client Skype di Windows in esecuzione su Windows XP e Windows Vista **(richiede la versione client più recente 7,26 o superiore)** <br/> |
|Skype Mobile-telefoni e Tablet Android  <br/> |6,19 o versioni successive, esecuzione di Android OS versione 4.0.3 o superiore  <br/> |I dispositivi low Specs potrebbero non supportare le videochiamate  <br/> |
|Skype mobile-iOS  <br/> |6,11 o versione successiva, su IOS 7 o versione successiva  <br/> |Non supportato sono iPhone 4 e versioni precedenti, iPod 4th Generation e versioni precedenti, iPad 1st Generation  <br/> |
|Skype Mac  <br/> |7,19 o versione successiva, in Mac OS X 10,9 (Mavericks) o superiore  <br/> |Richiede Mac OSX 10,9 o versione successiva  <br/> |
|Skype Universal Windows app (Windows 10) desktop e dispositivi mobili  <br/> |Windows 10 (Redstone 1 Update o versione successiva)  <br/> |Windows Universal app riceverà l'aggiornamento in autunno 2016 aggiunta del supporto per l'interoperabilità  <br/> |
   
Nella tabella seguente viene descritto lo stato di interoperabilità tra la versione più recente di Skype for business e la versione più recente di Skype consumer. 
  
|**Client**|**Ricerca directory Skype e aggiunta contatti**|**Skype A/V, interoperabilità di messaggistica istantanea**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |Sì  <br/> |Sì  <br/> |
|Skype for Business nel Mac  <br/> |Possibile aggiungere (nessuna ricerca)  <br/> |Sì  <br/> |
|Lync desktop 2013  <br/> |Possibile aggiungere (nessuna ricerca)  <br/> |Sì  <br/> |
|Lync Web App-online e in locale  <br/> |N/D  <br/> |N/D  <br/> |
|Lync mobile-Windows Phone  <br/> |Prossimamente  <br/> |Sì  <br/> |
|Lync mobile-Android  <br/> |Prossimamente  <br/> |Sì  <br/> |
|Lync mobile-iOS  <br/> |Prossimamente  <br/> |Sì  <br/> |
|Sistema chat room Lync  <br/> |Prossimamente  <br/> |Sì  <br/> |
|App Lync Modern (Win 8,1)  <br/> |Sì  <br/> |Sì  <br/> |
|Lync Mac 2011  <br/> |Possibile aggiungere (nessuna ricerca)  <br/> |Sì  <br/> |
|Lync desktop 2010  <br/> |Possibile aggiungere (nessuna ricerca)  <br/> |Sì  <br/> |
|Lync Phone Edition  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Attendant  <br/> |N/D  <br/> |N/D  <br/> |
   

