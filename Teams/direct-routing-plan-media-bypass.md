---
title: Pianificare il bypass multimediale con Instradamento diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Scopri come pianificare il bypass multimediale con il routing diretto del sistema telefonico, che consente di abbreviare il percorso del traffico multimediale e migliorare le prestazioni.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 638a39a843648ab8fab770c28d92b196201e20f5
ms.sourcegitcommit: c627bd1df17aefdc353bc4da6db169dfe169031e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2022
ms.locfileid: "68680509"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Pianificare il bypass multimediale con Instradamento diretto

## <a name="about-media-bypass-with-direct-routing"></a>Informazioni sul bypass multimediale con routing diretto

Il bypass multimediale consente di abbreviare il percorso del traffico multimediale e ridurre il numero di hop in transito per ottenere prestazioni migliori. Con il bypass multimediale, i supporti vengono mantenuti tra il controller di bordo della sessione (SBC) e il client invece di inviarli tramite Il sistema telefonico Microsoft. Per configurare il bypass multimediale, SBC e il client devono trovarsi nello stesso percorso o nella stessa rete.

È possibile controllare il bypass multimediale per ogni SBC usando il comando **Set-CSOnlinePSTNGateway** con il parametro **-MediaBypass** impostato su true o false. Se si abilita il bypass multimediale, questo non significa che tutto il traffico multimediale rimarrà all'interno della rete aziendale. Questo articolo descrive il flusso delle chiamate in scenari diversi.

I diagrammi seguenti illustrano la differenza nel flusso delle chiamate con e senza bypass multimediale.

Senza bypass multimediale, quando un client effettua o riceve una chiamata, sia il flusso di segnalazione che quello multimediale tra SBC, Microsoft Phone System e il client teams, come illustrato nel diagramma seguente:

> [!div class="mx-imgBorder"]
> ![Mostra il traffico di segnalazione e il flusso multimediale senza bypass multimediale.](media/direct-routing-media-bypass-1.png)


Si supponga però che un utente si trovi nello stesso edificio o nella stessa rete di SBC. Si supponga ad esempio che un utente che si trova in un edificio di Francoforte chiami un utente PSTN: 

- **Senza bypass multimediale**, i media fluiranno via Amsterdam o Dublino (dove vengono distribuiti i data center Microsoft) e torneranno alla SBC di Francoforte. 

  Il data center in Europa è selezionato perché la scheda SBC si trova in Europa e Microsoft usa il data center più vicino alla scheda SBC. Anche se questo approccio non influisce sulla qualità delle chiamate a causa dell'ottimizzazione del flusso del traffico all'interno delle reti Microsoft nella maggior parte delle aree geografiche, il traffico ha un ciclo non necessario.     

- **Con il bypass multimediale**, i supporti vengono mantenuti direttamente tra l'utente di Teams e SBC, come illustrato nel diagramma seguente:

  > [!div class="mx-imgBorder"]
  > ![Mostra il traffico di segnalazione e il flusso multimediale con bypass multimediale.](media/direct-routing-media-bypass-2.png)

Il bypass multimediale sfrutta protocolli denominati Interactive Connectivity Establishment (ICE) sul client Teams e ICE lite su SBC. Questi protocolli consentono all'instradamento diretto di utilizzare il percorso multimediale più diretto per una qualità ottimale. ICE e ICE Lite sono standard WebRTC. Per informazioni dettagliate su questi protocolli, vedere RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Pianificazione del flusso delle chiamate e del firewall

La pianificazione del flusso delle chiamate e del firewall dipende dal fatto che l'utente abbia accesso diretto all'indirizzo IP pubblico di SBC e che l'utente si trova all'interno o all'esterno della rete.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Flusso delle chiamate se l'utente ha accesso diretto all'indirizzo IP pubblico di SBC

Se l'utente ha accesso diretto all'indirizzo IP pubblico di SBC, il flusso delle chiamate è il seguente:

- Per il bypass multimediale, il client Teams deve avere accesso all'indirizzo IP pubblico di SBC anche da una rete interna. Se il supporto diretto non è desiderato, i supporti possono fluire attraverso Transport Relays.If direct media is desired, the media can flow via Transport Relays.

- Questa è la soluzione consigliata quando un utente si trova nello stesso edificio e/o rete di SBC: rimuovere i componenti Microsoft Cloud dal percorso multimediale.

- Il traffico di segnalazione scorre sempre attraverso il cloud Microsoft.

Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è interno e il client può raggiungere l'indirizzo IP pubblico di SBC (file multimediali diretti): 

- Le frecce e i valori numerici dei percorsi sono conformi ai [flussi delle chiamate di Microsoft Teams](./microsoft-teams-online-call-flows.md).

- La segnalazione SIP prende sempre i percorsi 4 e 4' (a seconda della direzione del traffico). Il supporto rimane locale e accetta il percorso 5b.

> [!div class="mx-imgBorder"]
> ![Mostra il flusso delle chiamate con bypass multimediale abilitato, il client è interno.](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico di SBC

Di seguito viene descritto il flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico di SBC. 

Ad esempio, si supponga che l'utente sia esterno e che l'amministratore del tenant abbia deciso di non aprire l'indirizzo IP pubblico di SBC a tutti gli utenti di Internet, ma solo a Microsoft Cloud. I componenti interni del traffico possono scorrere attraverso i relè di trasporto di Teams. Tenere in considerazione gli aspetti seguenti:

- Vengono utilizzati i relè di trasporto di Teams.

- Per il bypass multimediale, Microsoft utilizza una versione di Transport Relays che richiede l'apertura delle porte da 50 000 a 59 999 tra Teams Transport Relays e SBC (in futuro prevediamo di passare alla versione che richiede porte 3478-3481).


Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e il client non può raggiungere l'indirizzo IP pubblico del controller dei confini della sessione (il supporto viene inoltrato da Teams Transport Relay).

- Le frecce e i valori numerici dei percorsi sono conformi ai [flussi delle chiamate di Microsoft Teams](./microsoft-teams-online-call-flows.md).

- Il supporto viene inoltrato tramite i percorsi 3, 3', 4 e 4'

> [!div class="mx-imgBorder"]
> ![Mostra flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico della scheda SBC.](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Flusso delle chiamate se un utente è esterno alla rete e ha accesso all'indirizzo IP pubblico di SBC

> [!NOTE]
> Questa non è una configurazione consigliata perché non sfrutta i relay di trasporto di Teams. Si consideri invece lo scenario precedente in cui l'utente non ha accesso all'indirizzo IP pubblico di SBC. 

Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e il client può raggiungere l'indirizzo IP pubblico di SBC (supporto diretto).

- Le frecce e i valori numerici dei percorsi sono conformi all'articolo [Flussi delle chiamate di Microsoft Teams](./microsoft-teams-online-call-flows.md) .

- Il segnale SIP accetta sempre i percorsi 3 e 3' (a seconda della direzione del traffico). Flussi multimediali che usano il percorso 2.

> [!div class="mx-imgBorder"]
> ![Mostra flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico della scheda SBC.](media/direct-routing-media-bypass-5.png)



## <a name="use-of-media-processors-and-transport-relays"></a>Utilizzo di processori multimediali e relè di trasporto

Ci sono due componenti di Microsoft Cloud che possono essere nel percorso del traffico multimediale: Processori multimediali e Relè di trasporto. 

- Media Processor è un componente pubblico che gestisce i supporti in casi non di bypass e i supporti per le applicazioni vocali.

   I processori multimediali sono sempre nel percorso per le chiamate non bypassate dell'utente finale, ma non sono mai nel percorso per le chiamate ignorate. I processori multimediali sono sempre nel percorso per tutte le applicazioni vocali, ad esempio Parcheggio di chiamata, Operatore automatico organizzazione e Code di chiamata.

- Il Transport Relay viene utilizzato per connettersi al servizio di trasporto più vicino per inviare il traffico in tempo reale.

   I transport relay potrebbero essere o meno nel percorso per le chiamate ignorate, provenienti da o destinate agli utenti finali, a seconda della posizione dell'utente e della configurazione della rete.

Il diagramma seguente mostra due flussi delle chiamate: uno con bypass multimediale abilitato e il secondo con bypass multimediale disabilitato.

> [!NOTE]
> Il diagramma illustra solo il traffico proveniente dagli utenti finali, o destinato agli utenti finali.  

- Media Controller è un microservizio in Azure che assegna processori multimediali e crea offerte SDP (Session Description Protocol).

- Il proxy SIP è un componente che converte il segnale REST HTTP utilizzato in Teams in SIP.    

> [!div class="mx-imgBorder"]
> ![Mostra i flussi delle chiamate con bypass multimediale abilitato e disabilitato.](media/direct-routing-media-bypass-6.png)


La tabella seguente riepiloga la differenza tra processori multimediali e relè di trasporto.

|  &nbsp; | Processori multimediali | Relè di trasporto|
| :--------------|:---------------|:------------|
|Nel percorso multimediale per le chiamate non bypassate per gli utenti finali | Sempre | Se il client non riesce a raggiungere direttamente media processor |
|Nel percorso multimediale per le chiamate ignorate per gli utenti finali | Mai | Se il client non riesce a raggiungere SBC nell'indirizzo IP pubblico |
|Nel percorso multimediale per le applicazioni vocali | Sempre | Mai |
|Can do transcoding (B2BUA)\* | Sì | No, inoltra l'audio solo tra gli endpoint |

Gli intervalli IP sono:
- 52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)
- 52.120.0.0/14 (indirizzi IP da 52.120.0.1 a 52.123.255.254)

\* Spiegazione della transcodifica: 

- Media Processor è B2BUA, il che significa che può modificare un codec (ad esempio, SILK dal client Teams in MP e G.711 tra MP e SBC).

- I relè di trasporto non sono B2BUA, il che significa che il codec non viene mai modificato tra il client e SBC, anche se il traffico scorre attraverso i relè.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>Uso dei processori multimediali di Teams se il trunk è configurato per il bypass multimediale

I processori multimediali di Teams vengono sempre inseriti nel percorso multimediale nei seguenti scenari:

- La chiamata viene inoltrata da 1:1 a una chiamata di gruppo
- La chiamata viene effettuata a un utente federato di Teams
- La chiamata viene inoltrata o trasferita a un utente Skype for Business

Assicurarsi che SBC abbia accesso agli intervalli Media Processors e Transport Relays come descritto di seguito.    


## <a name="sip-signaling-fqdns"></a>Segnalazione SIP: FQDN

Per il segnale SIP, i requisiti fqdn e firewall sono gli stessi dei casi non ignorati. 

Il routing diretto è disponibile nei seguenti ambienti Microsoft 365 o Office 365:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD Scopri di più sugli [ambienti Office 365 e del governo degli Stati Uniti](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government), ad esempio GCC, GCC High e DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambienti Microsoft 365, Office 365 e Office 365 GCC

I punti di connessione per il routing diretto sono i seguenti tre FQDN:

- **sip.pstnhub.microsoft.com** , fqdn globale, deve essere prima provata. Quando SBC invia una richiesta di risoluzione di questo nome, i server DNS di Microsoft Azure restituiscono un indirizzo IP che punta al data center di Azure primario assegnato all'SBC. L'assegnazione si basa sulle metriche delle prestazioni dei data center e sulla prossimità geografica all'SBC.The assignment is based performance metrics of the datacenters and geographical proximity to the SBC. L'indirizzo IP restituito corrisponde all'FQDN primario.

- **sip2.pstnhub.microsoft.com** , FQDN secondario, mappa geograficamente alla seconda area di priorità.

- **sip3.pstnhub.microsoft.com** – FQDN fqdn fqdn : corrisponde geograficamente alla terza area di priorità.

È necessario inserire questi tre FQDN per:

- Offrire un'esperienza ottimale (meno carico e più vicino al data center SBC assegnato eseguendo una query sul primo FQDN).

- Fornire il failover quando viene stabilita una connessione da un server SBC a un data center in cui si verifica un problema temporaneo. Per ulteriori informazioni, vedere Meccanismo di failover di seguito.


Gli FQDN **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** e **sip3.pstnhub.microsoft.com** verranno risolti in indirizzi IP dalle subnet seguenti:
- 52.112.0.0/14
- 52.120.0.0/14

È necessario aprire le porte per tutti questi intervalli IP nel firewall per consentire il traffico in arrivo e in uscita da e verso gli indirizzi per il traffico di segnalazione.

### <a name="office-365-gcc-dod-environment"></a>Office 365 ambiente DoD GCC

Il punto di connessione per routing diretto è il seguente FQDN:

**sip.pstnhub.dod.teams.microsoft.us** : FQDN globale. Poiché l'ambiente DoD Office 365 esiste solo nei data center degli Stati Uniti, non esiste alcun FQDN secondario e terziario.

Il sip.pstnhub.dod.teams.microsoft.us FQDN verrà risolto in un indirizzo IP dalla subnet seguente:

- 52.127.64.0/21

È necessario aprire le porte per tutti questi intervalli IP nel firewall per consentire il traffico in arrivo e in uscita da e verso gli indirizzi per il traffico di segnalazione.  Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.dod.teams.microsoft.us risolve in tutte queste subnet IP. 

### <a name="office-365-gcc-high-environment"></a>Office 365 ambiente GCC High

Il punto di connessione per routing diretto è il seguente FQDN:

**sip.pstnhub.gov.teams.microsoft.us** - FQDN globale. Poiché l'ambiente GCC High esiste solo nei data center degli Stati Uniti, non esiste alcun FQDN secondario e terziario.

Il sip.pstnhub.gov.teams.microsoft.us FQDN verrà risolto in un indirizzo IP dalla subnet seguente:

- 52.127.88.0/21

È necessario aprire le porte per tutti questi intervalli IP nel firewall per consentire il traffico in arrivo e in uscita da e verso gli indirizzi per il traffico di segnalazione.  Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.gov.teams.microsoft.us risolve in tutte queste subnet IP. 

## <a name="sip-signaling-ports"></a>Segnalazione SIP: porte

I requisiti delle porte sono gli stessi per tutti gli ambienti Office 365 in cui è disponibile direct routing:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

È necessario utilizzare le porte seguenti:

| Traffico | Da | A | Porta di origine | Porta di destinazione|
| :-------- | :-------- |:-----------|:--------|:---------|
| SIP/TLS| SIP Proxy | Sbc | 1024 - 65535 | Definito in SBC |
| SIP/TLS | Sbc | SIP Proxy | Definito in SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Traffico multimediale: ip e intervalli di porte

Flussi di traffico multimediale tra il client SBC e Teams se è disponibile la connettività diretta o tramite i relay trasporto di Teams se il client non riesce a raggiungere la scheda SBC utilizzando l'indirizzo IP pubblico.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Requisiti per il traffico multimediale diretto (tra il client Teams e SBC) 

Il client deve avere accesso alle porte specificate (vedere la tabella) nell'indirizzo IP pubblico di SBC. 

> [!NOTE]
> Se il client si trova in una rete interna, il flusso del supporto passa all'indirizzo IP pubblico di SBC. È possibile configurare l'aggiunta dei capelli al dispositivo NAT in modo che il traffico non lasci mai l'apparecchiatura di rete aziendale.

| Traffico | Da | A | Porta di origine | Porta di destinazione|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Client | Sbc | 50000-50019| Definito in SBC |
| UDP/SRTP | Sbc | Client | Definito in SBC | 50000-50019  |


> [!NOTE]
> Se si dispone di un dispositivo di rete che traduce le porte di origine del client, assicurarsi che le porte tradotte vengano aperte tra l'apparecchiatura di rete e il server SBC. 

### <a name="requirements-for-using-transport-relays"></a>Requisiti per l'utilizzo dei relè di trasporto

I relè di trasporto sono nello stesso intervallo dei processori multimediali (per i casi non bypass): 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambienti Microsoft 365, Office 365 e Office 365 GCC

- 52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 ambiente DoD GCC

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 ambiente GCC High

- 52.127.88.0/21


L'intervallo di porte dei Teams Transport Relays (applicabile a tutti gli ambienti) è illustrato nella seguente tabella:


| Traffico | Da | A | Porta di origine | Porta di destinazione|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Transport Relay | Sbc | 50 000 -59 999    | Definito in SBC |
| UDP/SRTP | Sbc | Transport Relay | Definito in SBC | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft consiglia almeno due porte per chiamata simultanea in SBC. Poiché Microsoft ha due versioni di Transport Relays, sono necessarie le seguenti operazioni:
> 
> - v4, che funziona solo con un intervallo di porte compreso tra 50 000 e 59 999
> 
> - v6, che funziona con le porte 3478-3481

Al momento, bypass multimediale supporta solo versione v4 di Transport Relays. Introdurremo il supporto di v6 in futuro. 

È necessario aprire le porte 3478-3481 per la transizione. Quando Microsoft introduce il supporto per i Transport Relay v6 con Media Bypass, non sarà necessario riconfigurare le apparecchiature di rete o gli SBC. 

### <a name="requirements-for-using-media-processors"></a>Requisiti per l'utilizzo di processori multimediali

I processori multimediali sono sempre nel percorso multimediale per le applicazioni vocali e per i client Web (ad esempio, i client di Teams in Edge o Google Chrome). I requisiti sono gli stessi della configurazione non bypass.


L'intervallo IP per il traffico multimediale è 

### <a name="office-365-and-office-365-gcc-environments"></a>ambienti GCC Office 365 e Office 365

- 52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 ambiente DoD GCC

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 ambiente GCC High

- 52.127.88.0/21

L'intervallo di porte dei processori multimediali (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:

| Traffico | Da | A | Porta di origine | Porta di destinazione|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Media Processor | Sbc | 3478-3481 e 49 152 – 53 247    | Definito in SBC |
| UDP/SRTP | Sbc | Media Processor | Definito in SBC | 3478-3481 e 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>Configurare trunk separati per bypass multimediale e bypass non multimediale  

Se si esegue la migrazione al bypass multimediale da bypass non multimediale e si vuole confermare la funzionalità prima di eseguire la migrazione di tutto l'uso al bypass multimediale, è possibile creare un trunk separato e criteri di routing vocale online separati per il routing al trunk di bypass multimediale e assegnarli a utenti specifici. 

Passaggi di configurazione di alto livello:

- Identificare gli utenti per testare il bypass multimediale.

- Crea due trunk separati con FQDN diversi: uno abilitato per il bypass multimediale; l'altro no. 

  Entrambi i trunk puntano allo stesso SBC. Le porte per la segnalazione SIP TLS devono essere diverse. Le porte per gli elementi multimediali devono essere le stesse.

- Creare un nuovo criterio routing vocale online e assegnare il trunk di bypass multimediale alle route corrispondenti associate all'utilizzo PSTN per questo criterio.

- Assegnare il nuovo criterio Routing vocale online agli utenti identificati per testare il bypass multimediale.

L'esempio seguente illustra questa logica.

| Set di utenti | Numero di utenti | FQDN trunk assegnato in OVRP | Bypass multimediale abilitato |
| :------------ |:----------------- |:--------------|:--------------|
| Utenti con bypass trunk non multimediale | 980 | sbc1.contoso.com:5061 | false |
| Utenti con trunk di bypass multimediale | 20 | sbc2.contoso.com:5060 | true | 

Entrambi i trunk possono puntare allo stesso SBC con lo stesso indirizzo IP pubblico. Le porte di segnalazione TLS in SBC devono essere diverse, come illustrato nel diagramma seguente. Tenere presente che è necessario verificare che il certificato supporti entrambi i trunk. In SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o disporre di un certificato con caratteri jolly.

> [!div class="mx-imgBorder"]
> ![Mostra entrambi i trunk che possono puntare allo stesso SBC con lo stesso indirizzo IP pubblico.](media/direct-routing-media-bypass-7.png)

Per informazioni su come configurare due trunk nella stessa scheda SBC, vedere la documentazione fornita dal fornitore di SBC:

 - [Documentazione sulla distribuzione AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentazione relativa alla distribuzione di Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentazione sulla distribuzione di comunicazioni sulla barra multifunzione](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentazione sulla distribuzione di TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Endpoint client supportati con bypass multimediale

Il bypass multimediale è supportato con tutti i client desktop di Teams autonomi, i client Android e iOS e i dispositivi Telefonici di Teams. 

Per tutti gli altri endpoint che non supportano il bypass multimediale, la chiamata verrà convertita in non bypass anche se è stata avviata come bypass. Ciò si verifica automaticamente e non richiede alcuna azione da parte dell'amministratore. Sono inclusi Skype for Business telefoni 3PIP e client Web di Teams che supportano le chiamate direct routing (client basati su WebRTC in esecuzione su Microsoft Edge, Google Chrome, Mozilla Firefox). 
 
## <a name="see-also"></a>Vedere anche

[Configurare il bypass multimediale con Instradamento diretto](direct-routing-configure-media-bypass.md)
