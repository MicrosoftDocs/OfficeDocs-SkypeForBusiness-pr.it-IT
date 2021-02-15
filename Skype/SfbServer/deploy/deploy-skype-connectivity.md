---
title: Distribuire la connettività Skype in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Riepilogo: informazioni su come connettere Skype for Business Server con skype consumer. Noto anche come connettività Skype.'
ms.openlocfilehash: ae3982375c0693c34e204e4512481a1f9f3b6ec3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834106"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Distribuire la connettività Skype in Skype for Business Server

**Riepilogo:** Informazioni su come connettere Skype for Business Server con skype consumer. Noto anche come connettività Skype.
  
In questo articolo viene illustrata la distribuzione della connettività Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Panoramica della connettività Skype per professionisti IT

La connettività Skype offre agli utenti di Skype for Business la possibilità di cercare e aggiungere utenti Skype. Connettività Skype è una funzionalità di Skype for Business che consente di abilitare la federazione e la ricerca nella directory con gli utenti Skype. Dopo aver abilitato la connettività Skype, gli utenti di Skype for Business potranno cercare e aggiungere utenti Skype.
  
## <a name="skype-directory-search"></a>Ricerca directory Skype

La funzionalità Ricerca directory Skype offre agli utenti di Skype for Business la possibilità di cercare contatti Skype. La funzionalità di ricerca consente agli utenti di eseguire ricerche utilizzando quanto segue:
  
- **Ricerca per nome visualizzato, ad esempio "John Doe":** potrebbe restituire molti risultati, quindi potrebbe non essere possibile trovare quello che si sta cercando.
    
- Ricerca in base al nome visualizzato e alla posizione, ad esempio **"John Doe in Catalano":** in questo modo i risultati della ricerca saranno notevolmente ristretti.
    
- **Ricerca per posta elettronica, ad esempio "johndoe@outlook.com"** - Nella maggior parte dei casi dovrebbe essere restituito un risultato. quella che corrisponde esattamente al messaggio di posta elettronica specificato. Tuttavia, se lo stesso messaggio di posta elettronica è associato a più account, possono essere restituiti più risultati.
    
- **Ricerca per numero di telefono, ad esempio "123-123-1234"** - Questo dovrebbe restituire un risultato nella maggior parte dei casi; corrisponde esattamente al telefono specificato. Il numero di telefono deve includere il codice paese (ad esempio 1-xxx-aaa-zzzz). Se lo stesso numero di telefono è associato a più account, possono essere restituiti più risultati.
    
- **Search by Skype Name, example "JohnDoe1456"** - If exact match is found, it will be returned as the first result. Possono essere restituite altre possibili corrispondenze con il nome.
    
    > [!NOTE]
    > Skype Directory Search deve essere in grado di comunicare con i seguenti indirizzi IP sulla porta 443: 104.40.75.246, 23.101.135.34 e 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matrice di distribuzione supportata per La ricerca nella directory Skype

Nella tabella seguente viene descritto il supporto per La ricerca nella directory skype.
  

||**Skype for Business Server Front End**|**Lync Server 2013 (o versione precedente) Front End**|**Comments**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge  <br/> |Supportato  <br/> |Non supportato  <br/> |Skype for Business Server ed Edge sono prerequisiti per la ricerca nella directory di Skype  <br/> |
|Distribuzione affiancata di Skype for Business Server Edge + Lync Server 2013 Edge  <br/> |Supportato  <br/> |Non supportato  <br/> |Il traffico della ricerca nella directory Skype attraversa i server perimetrali di Skype for Business Server. Il traffico federativo passa attraverso il perimetro configurato dall'amministratore. Ad esempio, l'amministratore può scegliere di continuare a inviare il traffico di federazione tramite i server Perimetrali di Lync Server 2013 che non supportano la ricerca nella directory Skype.  <br/> |
|Lync Server 2013 (o versione precedente) Edge  <br/> |Non supportato  <br/> |Non supportato  <br/> ||
   
> [!NOTE]
> Il servizio Addressbook in esecuzione su Skype for Business Server Front End rileva l'edge in base all'esistenza della porta di ricerca Skype 4443 nel server perimetrale. 
  
> [!NOTE]
> Nel caso in cui un cliente abbia più siti nella distribuzione locale e se ha distribuito un solo server/pool di server perimetrali Skype for Business Server, il traffico di ricerca da tutti i siti passa attraverso il singolo server perimetrale disponibile. L'amministratore deve assicurarsi che i pool di tutti i siti possano accedere al server o al pool di server perimetrali di Skype for Business Server distribuito. 
  
> [!NOTE]
> Il servizio Grafico di Skype limiterà le richieste di ricerca da qualsiasi cliente locale o di Microsoft 365 o Office 365 se la frequenza delle richieste supera le 15 richieste al secondo. 
  
> [!NOTE]
> Per i clienti locali di grandi aziende, i domini dovranno essere nell'elenco degli indirizzi consentiti con il servizio di ricerca Skype per consentire una frequenza di richieste più elevata. 
  
> [!NOTE]
> Skype for Business Server rescinterà le richieste in arrivo, se sono presenti troppe richieste in sospeso nella coda. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Distribuzione della connettività Skype per Skype for Business online

La connettività Skype è anche una funzionalità di Skype for Business online, che fa parte di Microsoft 365 e Office 365. È possibile abilitare la funzionalità di connettività Skype dall'interfaccia di amministrazione di Skype for Business all'interno dell'interfaccia di amministrazione di Microsoft 365.
  
Per Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education e Office 365 per enti pubblici: accedere all'interfaccia di amministrazione di Microsoft 365 e passare all'interfaccia di amministrazione di Skype for Business. Passare a Comunicazioni esterne. In Provider di servizi di messaggistica istantanea pubblici fare clic su Abilita. Se si desidera controllare l'accesso dei singoli utenti alla connettività Skype, è possibile modificare le impostazioni di comunicazione esterna dei singoli utenti.
  
For Office 365 Small Business Premium: Sign in to Office 365, and go to Admin \> Service Settings \> Instant messaging, meetings and conferencing. Attivare le comunicazioni esterne. L'opzione Comunicazioni esterne attiva sia la connettività Skype che le comunicazioni con altre organizzazioni che usano Skype for Business.
  
Per ulteriori informazioni sull'amministrazione di Skype for Business online, vedere:
  
- [Permettere agli utenti di contattare utenti Skype for Business esterni](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Cosa provare se non è possibile messaggistica istantanea contatti esterni Skype for Business o Skype](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Aggiungere un contatto in Skype for Business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Amministratori: configurare le impostazioni di Skype for Business per singoli utenti](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Distribuzione della connettività Skype per Skype for Business Server

Skype for Business Server usa l'architettura di accesso federativo per supportare la connettività con Skype. Questa connettività consente agli utenti di Skype for Business Server di aggiungere Skype. I client Skype possono anche aggiungere utenti Skype for Business all'elenco dei contatti. In base ai criteri impostati a livello amministrativo in Skype for Business Server, gli utenti potranno comunicare tramite messaggistica istantanea, vedere la presenza degli altri utenti e avviare chiamate audio e video. La connettività Skype è anche una funzionalità di Skype for Business online e può essere abilitata per i clienti di Skype for Business online dall'interfaccia di amministrazione di Skype for Business all'interno dell'interfaccia di amministrazione di Microsoft 365.
  
> [!NOTE]
> Se Skype for Business Server è già configurato per connettersi a Windows Messenger tramite PIC (Public Instant Messaging Connectivity), la distribuzione è già configurata per la connettività Skype. L'unica modifica da prendere in considerazione è la ridenominazione della voce PIC di Messenger esistente come Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Il sito di provisioning della connettività per la messaggistica istantanea pubblica di Skype for Business Server non è più disponibile

Il sito utilizzato in precedenza per il provisioning manuale della federazione tra le distribuzioni locali di Skype for Business e Skype non è più necessario e verrà arrestato il 15/08/2019. La federazione con Skype ora utilizza l'individuazione di partner federati, che è lo stesso meccanismo necessario per la federazione con Skype for Business online.

La comunicazione tra qualsiasi distribuzione di Skype for Business locale e gli utenti Skype tramite l'infrastruttura di messaggistica istantanea pubblica esistente ora richiede che la configurazione del server perimetrale locale sia compatibile con Skype for Business online.

> [!NOTE]
> La maggior parte dei clienti non ha bisogno di alcuna azione, incluse tutte le distribuzioni federate con Skype for Business online.
  
Le distribuzioni locali sono necessarie per pubblicare un record SRV DNS federativo per ogni dominio che ospitano. Sono disponibili indicazioni per la [pianificazione del DNS.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning) Ogni dominio deve essere risolto dalla query DNS SRV in un FQDN del server perimetrale che soddisfi una corrispondenza di suffisso di primo livello del dominio. Si consideri ad esempio il dominio "contoso.com":

|**FQDN validi**|**Commento**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |In ogni caso, l'FQDN esatto deve essere presente nel nome di dominio completo o nel nome di dominio completo del certificato esterno installato nel server perimetrale.   |
|access.contoso.com   ||
|**FQDN non validi**|**Motivo**|
|sip.contoso-edge.com   |Non corrisponde a un suffisso.  |
|sip.it.contoso.com   |Non corrisponde a un suffisso di primo livello.   |

Ulteriori informazioni sui certificati esterni sono disponibili nella [pianificazione dei certificati.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)

#### <a name="faqs"></a>Domande frequenti

**Perché il sito Web di provisioning viene arrestato?**
Il meccanismo di provisioning di messaggistica istantanea pubblica (PIC) (pic.lync.com) distribuito nel 2006 non è più utilizzabile e verrà arrestato il 15/08/2019. La federazione di messaggistica istantanea pubblica presupporrà invece lo stesso modello di federazione utilizzato da Skype for Business Online, noto come "individuazione partner", in base al quale una distribuzione locale è pubblicamente individuabile dai record DNS SRV della federazione.

**Questa modifica significa che la federazione di messaggistica istantanea pubblica è deprecata?**
No. La federazione di messaggistica istantanea pubblica continuerà a essere supportata per molti anni, probabilmente finché il prodotto locale di Skype for Business non raggiunge la fine del ciclo di vita.

**La nostra azienda ha una relazione ibrida (spazio di indirizzi condiviso) con Skype for Business online, siamo interessati?**
No, poiché si è già federati con Skype for Business online, questa modifica non influirà sull'utente.
 
**Questo cambiamento significa che l'azienda deve abilitare la federazione con Skype for Business online?**
No. Se le impostazioni del proxy del server perimetrale non abilitano la federazione con il provider di hosting di Skype for Business online (sipfed.online.lync.com), questa modifica non influirà su questo. Tuttavia, gli stessi requisiti dns e certificati che si applicano alla federazione con Skype for Business online ora si applicano anche alla federazione con gli utenti Skype.
 
**La nostra azienda è di grandi dimensioni e non può modificare la configurazione perimetrale per motivi normativi/di conformità/ecc... Cosa possiamo fare?**
Tutte le organizzazioni locali che non possono modificare la configurazione del server perimetrale come specificato devono contattare il supporto tecnico del prodotto al più presto.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Abilitazione della federazione e della connettività PIC (Public IM Connectivity)

Ora concentrati sull'ambiente Skype for Business Server e sulle attività amministrative necessarie per configurare la connettività Skype. In questa sezione si presuppone che l'amministratore abbia distribuito Skype for Business Server e configurato l'accesso esterno, noto anche come server perimetrali. 
  
Esistono tre passaggi principali necessari per abilitare la federazione e pic. Si tratta di:
  
1. Configurare la federazione e pic
    
2. Configurare almeno un criterio per supportare l'accesso degli utenti federati
    
3. Configurare l'impostazione del provider PIC di Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurare la federazione e pic

La federazione è necessaria per consentire agli utenti skype di comunicare con gli utenti di Skype for Business nell'organizzazione. Pic (Public Instant Messaging Connectivity) è una classe di federazione e deve essere configurata per consentire agli utenti di Skype for Business di comunicare con gli utenti Skype. La federazione e il PIC vengono configurati utilizzando il Pannello di controllo di Skype for Business Server.
  
> [!NOTE]
> La federazione PIC non è più supportata dalle versioni dei prodotti precedenti a Lync Server 2010 (Live Communication Server, Office Communications Server). Le piattaforme supportate per la federazione PIC includono Skype for Business Server, Lync Server 2013 e Lync Server 2010. 
  
La federazione è necessaria per consentire agli utenti skype di comunicare con gli utenti di Skype for Business nell'organizzazione. Pic (Public Instant Messaging Connectivity) è una classe di federazione e deve essere configurata per consentire agli utenti di Skype for Business Server di comunicare con gli utenti Skype. La federazione e il PIC vengono configurati utilizzando la finestra di dialogo di configurazione edge del Pannello di controllo di Skype for Business Server, come illustrato nella figura.
  
![Definire un nuovo pool di server perimetrali](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Gli attributi EnableSkypeIdRouting e EnableSkypeDirectorySearch devono essere impostati su true nelle impostazioni del provider pubblico (vedere le istruzioni successive) per il funzionamento della ricerca. 
  
In questo modo vengono completate le attività amministrative che devono essere eseguite sul server. A questo punto è stata impostata la connettività Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Configurare almeno un criterio per supportare l'accesso degli utenti federati

Utilizzando il Pannello di controllo di Skype for Business Server, un amministratore deve configurare uno o più criteri di accesso degli utenti esterni per controllare se gli utenti di Skype possono collaborare con gli utenti interni di Skype for Business Server.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Configurare l'impostazione del provider PIC di Skype

Utilizzando Skype for Business Server Management Shell, un amministratore deve configurare i criteri client Skype for Business per visualizzare Skype come provider PIC aggiuntivo. 
  
> [!NOTE]
> Gli utenti dei provider di servizi PIC (Public Instant Messaging Connectivity) non possono partecipare alla messaggistica istantanea o alle conferenze nell'organizzazione finché non si configura almeno un criterio (passaggio 2, più indietro in questa procedura) per supportare la connettività di messaggistica istantanea pubblica. 
  
Per le nuove installazioni è possibile configurare la connettività Skype abilitando un provider pubblico Skype utilizzando il Pannello di controllo di Skype for Business Server, come illustrato nella figura.
  
![Provider federati SIP](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Per configurare la connettività Skype durante l'aggiornamento a Skype for Business Server, è necessario rimuovere e aggiungere di nuovo il provider pubblico Skype esistente. 
  
La configurazione della connettività Skype può essere eseguita anche utilizzando solo PowerShell. Per configurare la connettività Skype tramite PowerShell:
  
1. Da un Front End Server di Skype for Business Server, aprire Skype for Business Server Management Shell.
    
2. Eseguire i due comandi seguenti:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Se non si dispone già di un provider PIC nell'ambiente e si sta creando un nuovo provider PIC, non è necessario eseguire il cmdlet Remove-CsPublicProvider. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Quali sono le funzioni dei parametri meno ovvi?
    
   - ProxyFqdn: posizione di Skype Federation Edge (di proprietà/gestita da Microsoft)
    
   - IconURL: icona utilizzata dal &amp; client Lync Skype for Business per identificare visivamente i contatti Skype
    
   - NameDecorationRoutingDomain e NameDecorationExcludedDomainList: l'impostazione di queste impostazioni consente agli utenti di immettere gli account microsoft degli utenti Skype senza dover conoscere la "decorazione" di domini non Microsoft con "msn.com". Ciò elimina la necessità di digitare "user(contoso.com)@msn.com" per tutti i domini NON inclusi in ExcludedDomainList. Il client SfB formatterà automaticamente l'account microsoft se il dominio NON è incluso nell'elenco escluso. Abbiamo aggiunto i domini dell'account Microsoft più comuni all'elenco escluso.
    
     > [!NOTE]
     > Il provider pubblico deve essere rimosso e aggiunto nuovo se vengono apportate modifiche. Non sono consentite modifiche sul posto. 
  
     > [!NOTE]
     > Aggiunto nel client desktop Lync di Lync Server &amp; 2013 CU5 in Office 2013 SP1, NameDecorationRoutingDomain e NameDecorationExcludedDomainList migliorano la situazione in cui gli utenti di Lync che aggiungono contatti Skype necessari per "addobbare" domini non Microsoft per identificarli e instradarli a Skype (nel formato di: user(contoso.com)@msn.com). Queste nuove impostazioni consentiranno la formattazione automatica dell'indirizzo immesso dall'utente nella finestra di dialogo "Aggiungi contatto Skype" con NameDecorationRoutingDomain (che deve essere impostato su msn.com) se non contiene i domini in NameDecorationExcludedDomainList (attualmente è possibile supportare msn.com, live.com, Hotmail.com, outlook.com). 
  
3. Da un client Skype for Business gli utenti possono ora cercare e aggiungere un utente Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Client e matrice di interoperabilità

Nella tabella seguente viene descritto lo stato di interoperabilità tra l'ultima versione di Skype consumer e l'ultima versione di Skype for Business.
  

|**Client Skype**|**Aggiungere contatti, messaggistica istantanea, presenza, chiamate audio e video**|**Commento**|
|:-----|:-----|:-----|
|Skype Windows Desktop  <br/> |7.6 o versione successiva, Windows XP e versioni successive  <br/> |**NOVITÀ:** supporto aggiunto per il client Skype Windows in esecuzione in Windows XP e Windows Vista (richiede la versione client più recente **7.26 o successiva)** <br/> |
|Skype Mobile - Telefono e tablet Android  <br/> |6.19 o versione successiva, con sistema operativo Android versione 4.0.3 o successiva  <br/> |I dispositivi con specifiche basse potrebbero non supportare le videochiamate  <br/> |
|Skype Mobile - iOS  <br/> |6.11 o superiore, su IOS 7 o versione successiva  <br/> |Non sono supportati iPhone 4 e versioni precedenti, iPod di quarta generazione e versioni precedenti, iPad di prima generazione  <br/> |
|Skype Mac  <br/> |7.19 o versione successiva, su Mac OS X 10.9 (Maveriks) o versione successiva  <br/> |Richiede Mac OSX 10.9 o versione successiva  <br/> |
|Skype Universal Windows App (Windows 10) Desktop e Mobile  <br/> |Windows 10 (aggiornamento Redstone 1 o versione successiva)  <br/> |App universale di Windows riceverà l'aggiornamento nell'autunno 2016 aggiungendo il supporto per l'interoperabilità  <br/> |
   
Nella tabella seguente viene descritto lo stato di interoperabilità tra l'ultima versione di Skype for Business e l'ultima versione di Skype consumer. 
  
|**Client**|**Ricerca nella directory Skype e aggiunta di contatti**|**Skype A/V, interoperabilità di messaggistica istantanea**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |Sì  <br/> |Sì  <br/> |
|Skype for Business nel Mac  <br/> |Può aggiungere (nessuna ricerca)  <br/> |Sì  <br/> |
|Lync Desktop 2013  <br/> |Può aggiungere (nessuna ricerca)  <br/> |Sì  <br/> |
|Lync Web App - online e locale  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Mobile - Windows Phone  <br/> |Prossimamente  <br/> |Sì  <br/> |
|Lync Mobile - Android  <br/> |Prossimamente  <br/> |Sì  <br/> |
|Lync Mobile - iOS  <br/> |Prossimamente  <br/> |Sì  <br/> |
|Sistema chat room Lync  <br/> |Prossimamente  <br/> |Sì  <br/> |
|Lync Modern App (Win 8.1)  <br/> |Sì  <br/> |Sì  <br/> |
|Lync Mac 2011  <br/> |Può aggiungere (nessuna ricerca)  <br/> |Sì  <br/> |
|Lync Desktop 2010  <br/> |Può aggiungere (nessuna ricerca)  <br/> |Sì  <br/> |
|Lync Phone Edition  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Attendant  <br/> |N/D  <br/> |N/D  <br/> |
   
