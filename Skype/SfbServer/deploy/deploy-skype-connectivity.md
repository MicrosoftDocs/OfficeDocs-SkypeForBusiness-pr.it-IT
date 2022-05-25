---
title: Distribuire la connettività Skype in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Riepilogo: informazioni su come connettersi Skype for Business Server con Skype consumer. Nota anche come connettività Skype.'
ms.openlocfilehash: 6e569a52569e72d2fe67bdde786b752834452069
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671682"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Distribuire la connettività Skype in Skype for Business Server

**Riepilogo:** Informazioni su come connettersi Skype for Business Server con Skype consumer. Nota anche come connettività Skype.
  
Questo articolo illustra la distribuzione per la connettività Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Panoramica della connettività Skype per i professionisti IT

Skype Connettività offre agli utenti Skype for Business la possibilità di cercare e aggiungere utenti Skype. Skype Connettività è una funzionalità di Skype for Business che consente di abilitare la federazione e la ricerca nella directory con gli utenti Skype. Dopo aver abilitato Skype Connettività, gli utenti Skype for Business potranno cercare e aggiungere Skype utenti.
  
## <a name="skype-directory-search"></a>Ricerca directory Skype

Skype funzionalità Di ricerca directory offre agli utenti Skype for Business la possibilità di cercare contatti Skype. La funzionalità di ricerca consente agli utenti di eseguire ricerche usando quanto segue:
  
- **Ricerca in base al nome visualizzato, ad esempio "John Doe"** - Questo potrebbe restituire molti risultati, quindi potrebbe non essere possibile trovare ciò che si sta cercando.
    
- **Ricerca in base al nome visualizzato e alla posizione, ad esempio "John Doe in Barcelona"** - In questo modo i risultati della ricerca verranno limitati notevolmente.
    
- **Ricerca tramite posta elettronica, ad esempio "johndoe@outlook.com"** - Questo dovrebbe restituire un risultato nella maggior parte dei casi; quella che corrisponde esattamente al messaggio di posta elettronica specificato. Tuttavia, se lo stesso messaggio di posta elettronica è associato a più account, è possibile che vengano restituiti più risultati.
    
- **Ricerca per numero di telefono, esempio "123-123-1234"** - Questo dovrebbe restituire un risultato nella maggior parte dei casi; quello che corrisponde esattamente al telefono specificato. Telefono numero deve includere il codice paese (ad esempio 1-xxx-yyy-zzzz). Se lo stesso numero di telefono è associato a più account, è possibile che vengano restituiti più risultati.
    
- **Ricerca in base Skype Nome, ad esempio "JohnDoe1456"** - Se viene trovata una corrispondenza esatta, verrà restituito come primo risultato. È possibile che vengano restituite altre possibili corrispondenze "name".
    
    > [!NOTE]
    > Skype Ricerca directory deve essere in grado di comunicare con gli indirizzi IP seguenti sulla porta 443: 104.40.75.246, 23.101.135.34 e 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matrice di distribuzione supportata per Skype Ricerca directory

Nella tabella seguente viene descritto il supporto per Skype Ricerca directory.
  

|&nbsp;|front-end Skype for Business Server|Front-end lync server 2013 (o versione precedente)|Commenti|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge   |Supportato   |Non supportato   |Skype for Business Server e Edge sono prerequisiti per Skype Ricerca directory   |
|Skype for Business Server Edge + Lync Server 2013 Edge distribuito side-by-side   |Supportato   |Non supportato   |Skype il traffico di Ricerca directory scorre attraverso Skype for Business Server server Perimetrali. Il traffico federativo passa attraverso il server perimetrale configurato dall'amministratore. Ad esempio, l'amministratore potrebbe scegliere di continuare a inviare il traffico federativo attraverso i server Lync Server 2013 Edge che non supporterebbero Skype Ricerca directory.   |
|Lync Server 2013 (o versione precedente) Edge   |Non supportato   |Non supportato   ||
   
> [!NOTE]
> Il servizio Rubrica in esecuzione in Skype for Business Server Front End trova l'edge in base all'esistenza della porta di ricerca Skype 4443 nel server Perimetrale. 
  
> [!NOTE]
> Nel caso in cui un cliente abbia più siti nella distribuzione locale e abbia distribuito solo un Skype for Business Server server/pool Perimetrale, il traffico di ricerca da tutti i siti passerà attraverso il singolo server Perimetrale disponibile. L'amministratore deve assicurarsi che i pool di tutti i siti possano accedere al server/pool perimetrale distribuito Skype for Business Server. 
  
> [!NOTE]
> Skype servizio graph limiterà le richieste di ricerca provenienti da qualsiasi cliente locale o Microsoft 365 o Office 365 se la frequenza delle richieste supera i 15 richieste al secondo. 
  
> [!NOTE]
> Per i clienti locali aziendali di grandi dimensioni, i domini dovranno essere aggiunti a un elenco di utenti consentiti con il servizio di ricerca Skype per consentire tassi di richiesta più elevati.
  
> [!NOTE]
> Skype for Business Server limiterà le richieste in ingresso, se sono presenti troppe richieste in sospeso nella coda. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Distribuzione della connettività Skype per Skype for Business Online

Skype Connettività è anche una funzionalità di Skype for Business Online, che fa parte di Microsoft 365 e Office 365. È possibile abilitare la funzionalità connettività Skype dall'Interfaccia di amministrazione Skype for Business all'interno del interfaccia di amministrazione di Microsoft 365.
  
Per Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education e Office 365 per enti pubblici: accedere al interfaccia di amministrazione di Microsoft 365 e passare all'Interfaccia di amministrazione Skype for Business. Passare a Comunicazioni esterne. In Provider di servizi di messaggistica istantanea pubblica fare clic su Abilita. Se si vuole controllare l'accesso dei singoli utenti alla connettività Skype, è possibile farlo modificando le impostazioni delle comunicazioni esterne dei singoli utenti.
  
Per Office 365 Small Business Premium: accedere a Office 365 e passare a Amministrazione \> Service Impostazioni \> Messaggistica istantanea, riunioni e conferenze. Attivare Comunicazioni esterne. L'opzione Comunicazioni esterne attiva sia la connettività Skype che le comunicazioni con altre organizzazioni che usano Skype for Business.
  
Per altre informazioni sull'amministrazione Skype for Business Online, vedere:
  
- [Permettere agli utenti di contattare utenti Skype for Business esterni](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Cosa provare se non è possibile Skype for Business di messaggistica istantanea o Skype contatti esterni](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Aggiungere un contatto in Skype for Business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Amministratori: configurare le impostazioni di Skype for Business per i singoli utenti](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Distribuzione della connettività Skype per Skype for Business Server

Skype for Business Server usa l'architettura di accesso federativo per supportare la connettività con Skype. Questa connettività consente agli utenti Skype for Business Server di aggiungere Skype. Skype client possono anche aggiungere Skype for Business utenti al proprio elenco di contatti. In base ai criteri impostati a livello amministrativo in Skype for Business Server gli utenti potranno comunicare usando la messaggistica istantanea, visualizzare la presenza reciproca e avviare chiamate audio e videochiamate. Skype connettività è anche una funzionalità di Skype for Business Online e può essere abilitata per i clienti di Skype for Business Online dall'Interfaccia di amministrazione Skype for Business all'interno di interfaccia di amministrazione di Microsoft 365.
  
> [!NOTE]
> Se Skype for Business Server è già configurato per la connessione con Windows Messenger tramite la connettività di messaggistica istantanea pubblica, la distribuzione è già configurata per la connettività Skype. L'unica modifica che potresti voler prendere in considerazione è rinominare la voce PIC di Messenger esistente come Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Il sito di provisioning della connettività di messaggistica istantanea pubblica Skype for Business Server non è più disponibile

Il sito usato in precedenza per effettuare manualmente il provisioning della federazione tra Skype for Business distribuzioni locali e Skype non è più necessario e verrà arrestato il 15/8/2019. La federazione con Skype usa ora l'individuazione di partner federati, che è lo stesso meccanismo necessario per la federazione con Skype for Business Online.

La comunicazione tra qualsiasi distribuzione Skype for Business locale e Skype utenti tramite l'infrastruttura di messaggistica istantanea pubblica esistente richiede ora che la configurazione di Edge Server locale sia compatibile con Skype for Business Online.

> [!NOTE]
> La maggior parte dei clienti non richiede alcuna azione, incluse tutte le distribuzioni federate con Skype for Business Online.
  
Le distribuzioni locali sono necessarie per pubblicare un record SRV DNS federativo per ogni dominio che ospitano. Le indicazioni sono disponibili nella [pianificazione DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning). Ogni dominio deve essere risolto tramite query SRV DNS in un FQDN del server perimetrale che soddisfa una corrispondenza di suffisso di primo livello del dominio. Si consideri ad esempio il dominio "contoso.com":

|**FQDN validi**|**Commento**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |In ogni caso, l'FQDN esatto deve essere presente nel SN o nella SAN del certificato esterno installato nel server perimetrale.   |
|access.contoso.com   ||
|**FQDN non validi**|**Motivo**|
|sip.contoso-edge.com   |Non corrisponde a un suffisso.  |
|sip.it.contoso.com   |Non corrisponde a un suffisso di primo livello.   |

Altre indicazioni relative ai certificati esterni sono disponibili in [Pianificazione dei certificati](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>Domande frequenti

**Perché il sito Web di provisioning viene arrestato?**
Il meccanismo di provisioning di messaggistica istantanea pubblica (PIC) (pic.lync.com) distribuito nel 2006 non è più utilizzabile e verrà arrestato il 15/8/2019. Al contrario, la federazione della messaggistica istantanea pubblica presuppone lo stesso modello federativo usato da Skype for Business Online, noto come "individuazione partner", in base al quale una distribuzione locale è individuabile pubblicamente dai record SRV DNS federativi.

**Questa modifica significa che la federazione della messaggistica istantanea pubblica viene deprecata?**
No. La federazione della messaggistica istantanea pubblica continuerà a essere supportata per molti anni, probabilmente fino a quando la Skype for Business prodotto locale non raggiungerà la fine del ciclo di vita.

**La nostra azienda ha una relazione ibrida (spazio indirizzi condiviso) con Skype for Business Online, siamo interessati?**
No, poiché si sta già eseguendo la federazione con Skype for Business Online, questa modifica non influisce sull'utente.
 
**Questa modifica significa che la nostra azienda deve abilitare la federazione con Skype for Business Online?**
No. Se le impostazioni proxy del server perimetrale non abilitano la federazione con il provider di hosting Skype for Business Online (sipfed.online.lync.com), questa modifica non influisce su questo aspetto. Tuttavia, gli stessi requisiti DNS e certificati che si applicano alla federazione con Skype for Business Online ora si applicano anche alla federazione con gli utenti Skype.
 
**La nostra azienda è di grandi dimensioni e non può modificare la sua configurazione perimetrale a causa di motivi normativi/di conformità/ecc... Cosa possiamo fare?**
Qualsiasi organizzazione locale che non può modificare la configurazione del server perimetrale come specificato dovrebbe contattare il supporto tecnico al più presto.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Abilitazione della federazione e della connettività di messaggistica istantanea pubblica (PIC)

Concentrarsi ora sull'ambiente Skype for Business Server e sulle attività amministrative necessarie per configurare la connettività Skype. In questa sezione si presuppone che l'amministratore abbia distribuito Skype for Business Server e configurato l'accesso esterno, noto anche come server Perimetrali. 
  
Sono necessari tre passaggi principali per abilitare la federazione e il PIC. Si tratta di:
  
1. Configurare federazione e PIC
    
2. Configurare almeno un criterio per supportare l'accesso utente federato
    
3. Configurare l'impostazione del provider PIC Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurare federazione e PIC

La federazione è necessaria per consentire agli utenti Skype di comunicare con Skype for Business utenti dell'organizzazione. Public Instant Messaging Connectivity (PIC) è una classe di federazione e deve essere configurata per consentire agli utenti Skype for Business di comunicare con gli utenti Skype. La federazione e il PIC vengono configurati usando il Skype for Business Server Pannello di controllo.
  
> [!NOTE]
> La federazione PIC non è più supportata dalle versioni del prodotto precedenti a Lync Server 2010 (Live Communication Server, Office Communications Server). Le piattaforme supportate per la federazione PIC includono Skype for Business Server, Lync Server 2013 e Lync Server 2010. 
  
La federazione è necessaria per consentire agli utenti Skype di comunicare con Skype for Business utenti dell'organizzazione. Public Instant Messaging Connectivity (PIC) è una classe di federazione che deve essere configurata per consentire agli utenti Skype for Business Server di comunicare con gli utenti Skype. La federazione e il PIC vengono configurati tramite la finestra di dialogo di configurazione Edge del Skype for Business Server Pannello di controllo, come illustrato nella figura.
  
![Definire il nuovo pool di server perimetrali.](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Gli attributi EnableSkypeIdRouting e EnableSkypeDirectorySearch devono essere impostati su true nelle impostazioni del provider pubblico (vedere istruzioni successive) per il funzionamento della ricerca. 
  
In questo modo vengono completate le attività amministrative che devono essere eseguite nel server. A questo momento si è configurato per la connettività Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Configurare almeno un criterio per supportare l'accesso utente federato

Usando il Skype for Business Server Pannello di controllo, un amministratore deve configurare uno o più criteri di accesso degli utenti esterni per controllare se Skype utenti possono collaborare con gli utenti Skype for Business Server interni.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Configurare l'impostazione del provider PIC Skype

Usando Skype for Business Server Management Shell, un amministratore deve configurare i criteri client Skype for Business per visualizzare Skype come provider PIC aggiuntivo. 
  
> [!NOTE]
> Gli utenti dei provider di servizi PIC (Public Instant Messaging Connectivity) non possono partecipare alla messaggistica istantanea o alle conferenze nell'organizzazione fino a quando non si configurano anche almeno un criterio (passaggio 2, precedente a questa procedura) per supportare la connettività di messaggistica istantanea pubblica. 
  
Per le nuove installazioni è possibile configurare Skype Connettività abilitando un provider pubblico Skype usando il Skype for Business Server Pannello di controllo come illustrato nella figura.
  
![Provider federati SIP.](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Per configurare Skype Connettività durante l'aggiornamento a Skype for Business Server è necessario rimuovere e aggiungere nuovamente il provider pubblico Skype esistente. 
  
La configurazione della connettività Skype può essere eseguita anche usando solo PowerShell. Per configurare la connettività Skype con PowerShell:
  
1. Da un front-end server Skype for Business Server aprire Skype for Business Server Management Shell.
    
2. Eseguire i due comandi seguenti:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Se non si dispone già di un provider PIC nell'ambiente e si sta creando un nuovo provider PIC, non è necessario eseguire il cmdlet Remove-CsPublicProvider. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Cosa fanno i parametri meno ovvi?
    
   - ProxyFqdn: posizione di Skype bordo federativo (di proprietà/gestito da Microsoft)
    
   - IconURL: icona usata da Lync &amp; Skype for Business client per identificare visivamente i contatti Skype
    
   - NameDecorationRoutingDomain e NameDecorationExcludedDomainList: l'impostazione consente agli utenti di immettere gli account del servizio gestito degli utenti Skype senza dover conoscere la "decorazione" di domini non Microsoft con "msn.com". In questo modo viene eliminata la necessità di digitare "user(contoso.com)@msn.com" per tutti i domini NON inclusi in ExcludedDomainList. Il client SfB formatterà automaticamente l'account del servizio gestito se il dominio non è incluso nell'elenco Esclusi. Sono stati aggiunti i domini dell'account Microsoft più comuni all'elenco escluso.
    
     > [!NOTE]
     > Il provider pubblico deve essere rimosso e aggiunto nuovo se vengono apportate modifiche. Non sono consentite modifiche sul posto. 
  
     > [!NOTE]
     > Aggiunto nel client desktop Lync di Lync Server 2013 CU5 &amp; in Office 2013 SP1, NameDecorationRoutingDomain e NameDecorationExcludedDomainList migliorano la situazione in cui gli utenti di Lync aggiungono Skype contatti necessari per "decorare" domini non Microsoft per identificarli e indirizzarli a Skype (il formato: user(contoso.com)@msn.com). Queste nuove impostazioni consentiranno la formattazione automatica dell'immissione dell'indirizzo dell'utente nella finestra di dialogo "Aggiungi contatto Skype" con NameDecorationRoutingDomain (che deve essere impostato su msn.com) se non contiene i domini in NameDecorationExcludedDomainList (attualmente è possibile supportare msn.com, live.com, Hotmail.com, outlook.com). 
  
3. Da un Skype for Business gli utenti client possono ora cercare e aggiungere un utente Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Client e matrice di interoperabilità

Nella tabella seguente viene descritto lo stato di interoperabilità tra la versione più recente del consumer Skype e la versione più recente di Skype for Business.
  

|Client Skype|Aggiungere contatti, messaggistica istantanea, presenza, audio e videochiamate|Comment|
|:-----|:-----|:-----|
|Skype Windows Desktop   |7.6 o superiore, Windows XP e versioni successive   |**NUOVO**: è stato aggiunto il supporto per Windows Skype client in esecuzione in Windows XP e Windows Vista **(richiede la versione client più recente 7.26 o successiva)**  |
|Skype Mobile - Android Telefono e tablet   |6.19 o versione successiva, in esecuzione Android versione 4.0.3 o successiva del sistema operativo   |I dispositivi con specifiche basse potrebbero non supportare le videochiamate   |
|Skype Mobile - iOS   |6.11 o versione successiva, su IOS 7 o versione successiva   |Non sono supportati iPhone 4 e versioni precedenti, iPod di 4a generazione e versioni precedenti, iPad prima generazione   |
|Skype Mac   |7.19 o superiore, su Mac OS X 10.9 (Mavericks) o superiore   |Richiede Mac OSX 10.9 o versione successiva   |
|Skype desktop e dispositivi mobili dell'app Windows universale (Windows 10)   |Windows 10 (aggiornamento di Redstone 1 o versione successiva)   |Windows'app universale riceverà l'aggiornamento nell'autunno 2016 con l'aggiunta del supporto per l'interoperabilità   |
   
Nella tabella seguente viene descritto lo stato di interoperabilità tra la versione più recente di Skype for Business e la versione più recente di Skype consumer. 
  
|Client|Skype Ricerca directory e Aggiungi contatti|Skype A/V, interoperabilità di messaggistica istantanea|
|:-----|:-----|:-----|
|Skype for Business   |Sì   |Sì   |
|Skype for Business nel Mac   |Può aggiungere (nessuna ricerca)   |Sì   |
|Lync Desktop 2013   |Può aggiungere (nessuna ricerca)   |Sì   |
|Lync Web App - online e locale   |N/D   |N/D   |
|Lync Mobile - Windows Phone   |Prossimamente   |Sì   |
|Lync Mobile - Android   |Prossimamente   |Sì   |
|Lync Mobile - iOS   |Prossimamente   |Sì   |
|Sistema chat room Lync   |Prossimamente   |Sì   |
|App lync moderna (Win 8.1)   |Sì   |Sì   |
|Lync Mac 2011   |Può aggiungere (nessuna ricerca)   |Sì   |
|Lync Desktop 2010   |Può aggiungere (nessuna ricerca)   |Sì   |
|Lync Phone Edition   |N/D   |N/D   |
|Lync Attendant   |N/D   |N/D   |
   
