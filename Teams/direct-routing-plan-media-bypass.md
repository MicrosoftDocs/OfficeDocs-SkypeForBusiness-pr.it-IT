---
title: Pianificare il bypass multimediale con Instradamento diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come pianificare il bypass multimediale con l'instradamento diretto del sistema telefonico, che consente di abbreviare il percorso del traffico multimediale e migliorare le prestazioni.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: efd6d4275d1e83df7821f178ddac8027039b6fce
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790658"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Pianificare il bypass multimediale con Instradamento diretto

## <a name="about-media-bypass-with-direct-routing"></a>Informazioni sul bypass multimediale con routing diretto

Il bypass multimediale consente di abbreviare il percorso del traffico multimediale e ridurre il numero di hop in transito per migliorare le prestazioni. Con il bypass multimediale, gli elementi multimediali vengono mantenuti tra il session border controller (SBC) e il client invece di inviarli tramite il Sistema telefonico Microsoft. Per configurare il bypass multimediale, SBC e il client devono essere nella stessa posizione o rete.

È possibile controllare il bypass multimediale per ogni SBC usando il comando **Set-CSOnlinePSTNGateway** con il parametro **-MediaBypass** impostato su true o false. Se abiliti il bypass multimediale, ciò non significa che tutto il traffico multimediale resterà all'interno della rete aziendale. Questo articolo descrive il flusso delle chiamate in diversi scenari.    

I diagrammi seguenti illustrano la differenza nel flusso delle chiamate con e senza bypass multimediale.

Senza bypass multimediale, quando un client effettua o riceve una chiamata, sia il traffico di segnalazione che il flusso multimediale tra SBC, Il Sistema telefonico Microsoft e il client Teams, come illustrato nel diagramma seguente:

> [!div class="mx-imgBorder"]
> ![Mostra il traffico di segnalazione e il flusso multimediale senza bypass multimediale](media/direct-routing-media-bypass-1.png)


Si supponga però che un utente si trova nello stesso edificio o rete del database SBC. Si supponga, ad esempio, che un utente che si trova in un edificio di Gateway effettua una chiamata a un utente PSTN: 

- **Senza bypass multimediale,** gli elementi multimediali fluiranno attraverso Amsterdam o Dublino (in cui sono distribuiti i data center Microsoft) e tornano alla SBC in Avi. 

  Il data center in Europa è selezionato perché il database SBC si trova in Europa e Microsoft usa il data center più vicino a SBC. Anche se questo approccio non influisce sulla qualità delle chiamate a causa dell'ottimizzazione del flusso del traffico all'interno delle reti Microsoft nella maggior parte delle aree geografiche, il traffico presenta un ciclo non necessario.     

- **Con il bypass** multimediale, i contenuti multimediali vengono mantenuti direttamente tra l'utente di Teams e il controller SBC, come illustrato nel diagramma seguente:

  > [!div class="mx-imgBorder"]
  > ![Mostra il traffico di segnalazione e il flusso multimediale con bypass multimediale](media/direct-routing-media-bypass-2.png)

Il bypass multimediale utilizza protocolli chiamati Interactive Connectivity Connectivity (ICE) sul client Teams e ICE lite sul sistema SBC. Questi protocolli consentono di usare il percorso multimediale più diretto per una qualità ottimale. ICE e ICE Lite sono standard WebRTC. Per informazioni dettagliate su questi protocolli, vedere RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Flusso delle chiamate e pianificazione del firewall

Il flusso delle chiamate e la pianificazione del firewall dipendono dal fatto che l'utente abbia accesso diretto all'indirizzo IP pubblico del database SBC e che l'utente sia all'interno o all'esterno della rete.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Flusso delle chiamate se l'utente ha accesso diretto all'indirizzo IP pubblico del servizio SBC

Se l'utente ha accesso diretto all'indirizzo IP pubblico del servizio SBC, il flusso delle chiamate è il seguente:

- Per il bypass multimediale, il client Teams deve avere accesso all'indirizzo IP pubblico del servizio SBC anche da una rete interna. Se non si desidera utilizzare elementi multimediali diretti, il flusso degli elementi multimediali può essere inoltrato tramite Transport Relays.

- Questa è la soluzione consigliata quando un utente si trova nella stessa edificio e/o rete del servizio SBC, rimuovendo i componenti Microsoft Cloud dal percorso multimediale.

- Il traffico di segnalazione fluisce sempre attraverso il cloud Microsoft.

Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è interno e può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto): 

- Le frecce e i valori numerici dei percorsi sono conformi ai flussi delle [chiamate di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)

- Il traffico di segnalazione SIP prende sempre i percorsi 4 e 4' (a seconda della direzione del traffico). L'elemento multimediale rimane locale e prende il percorso 5b.

> [!div class="mx-imgBorder"]
> ![Mostra il flusso delle chiamate con il bypass multimediale abilitato, il client è interno](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico del servizio SBC

Di seguito viene descritto il flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico del servizio SBC. 

Ad esempio, si supponga che l'utente sia esterno e che l'amministratore del tenant abbia deciso di non aprire l'indirizzo IP pubblico del servizio SBC a tutti gli utenti in Internet, ma solo a Microsoft Cloud. I componenti interni del traffico possono essere trasmessi tramite i Relay di trasporto di Teams. Tenere in considerazione gli aspetti seguenti:

- Vengono usati i Relay di trasporto di Teams.

- Per il bypass multimediale, Microsoft usa una versione di Transport Relays che richiede l'apertura delle porte da 50 000 a 59 999 tra i Inoltro di trasporto di Teams e SBC (in futuro prevede di passare alla versione che richiede solo 3478 e 3479 porte).


Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e il client non può raggiungere l'indirizzo IP pubblico del controller dei confini della sessione (il supporto viene inoltrato da Teams Transport Relay).

- Le frecce e i valori numerici dei percorsi sono conformi ai flussi delle [chiamate di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)

- Gli elementi multimediali vengono inoltrati tramite percorsi 3, 3', 4 e 4'

> [!div class="mx-imgBorder"]
> ![Mostra il flusso delle chiamate se l'utente non ha accesso all'IP pubblico di SBC](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Flusso delle chiamate se un utente è esterno alla rete e ha accesso all'indirizzo IP pubblico dell'SBC

> [!NOTE]
> Questa non è una configurazione consigliata perché non sfrutta i servizi di inoltro di trasporto di Teams. È invece opportuno considerare lo scenario precedente in cui l'utente non ha accesso all'indirizzo IP pubblico del database SBC. 

Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto).

- Le frecce e i valori numerici dei percorsi sono conformi all'articolo flussi delle chiamate [di Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)

- Il traffico di segnalazione SIP prende sempre i percorsi 3 e 3' (a seconda della direzione del traffico). Flussi multimediali utilizzando il percorso 2.

> [!div class="mx-imgBorder"]
> ![Mostra il flusso delle chiamate se l'utente non ha accesso all'IP pubblico di SBC](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>Uso dei processori multimediali e degli inoltri di trasporto

Nel cloud Microsoft possono essere presenti due componenti nel percorso del traffico multimediale: Processori multimediali e Inoltro di trasporto. 

- Il processore multimediale è un componente pubblico che gestisce gli elementi multimediali in casi di bypass e gestisce gli elementi multimediali per le applicazioni vocali.

   I processori multimediali sono sempre nel percorso per le chiamate senza bypass da parte dell'utente finale, ma mai nel percorso per le chiamate bypassate. I processori multimediali sono sempre presenti nel percorso per tutte le applicazioni vocali, ad esempio Il Parco chiamate, l'organizzazione Operatore automatico e le code di chiamata.

- L'inoltro di trasporto viene usato per connettersi al servizio di trasporto più vicino per inviare il traffico in tempo reale.

   I Transport Relay possono essere o meno nel percorso per le chiamate ignorate, provenienti o destinate agli utenti finali, a seconda di dove si trova l'utente e di come è configurata la rete.

Il diagramma seguente mostra due flussi delle chiamate: uno con il bypass multimediale abilitato e il secondo con il bypass multimediale disabilitato. Si noti che il diagramma illustra solo il traffico proveniente da, o destinato a, gli utenti finali.  
- Il controller multimediale è un microservice in Azure che assegna processori multimediali e crea offerte SDP (Session Description Protocol).

- Il proxy SIP è un componente che traduce il traffico REST HTTP utilizzato in Teams in SIP.    

> [!div class="mx-imgBorder"]
> ![Mostra i flussi delle chiamate con il bypass multimediale abilitato e disabilitato](media/direct-routing-media-bypass-6.png)


La tabella seguente riepiloga la differenza tra processori multimediali e inoltro di trasporto.

|    | Processori multimediali | Inoltro di trasporto|
| :--------------|:---------------|:------------|
Percorso multimediale per chiamate senza bypass per gli utenti finali | Sempre | Mai | 
Percorso multimediale per le chiamate ignorate per gli utenti finali | Mai | Se il client non riesce a raggiungere SBC nell'indirizzo IP pubblico | 
Percorso multimediale per le applicazioni vocali | Sempre | Mai | 
Può eseguire la trascodtura (B2BUA)\* | Sì | No, l'audio viene inoltrato solo tra gli endpoint | 
Numero di istanze in tutto il mondo e località | 10 totale: 2 negli Stati Uniti orientali e orientali; 2 ad Amsterdam e Dublino; 2 a Hong Kong e Singapore; 2 in Giappone ; 2 in Australia orientale e sud-orientale | Multiplo

Gli intervalli IP sono:
- 52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)
- 52.120.0.0/14 (indirizzi IP da 52.120.0.1 a 52.123.255.254)

\* Spiegazione trascrittura: 

- Processore multimediale è B2BUA, il che significa che può modificare un codec (ad esempio, SILK dal client Teams a MP e G.711 tra MP e SBC).

- I inoltro di trasporto non sono B2BUA, il che significa che il codec non viene mai modificato tra il client e SBC, anche se il traffico passa attraverso gli inoltri.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>Uso dei processori multimediali di Teams se è configurato il trunk per il bypass multimediale

I processori multimediali di Teams vengono sempre inseriti nel percorso multimediale negli scenari seguenti:

- La chiamata viene inoltrata da una chiamata 1:1 a una chiamata di gruppo
- La chiamata è per un utente di Teams federato
- La chiamata viene inoltrata o trasferita a un utente Skype for Business

Assicurarsi che SBC abbia accesso agli intervalli Media Processors e Transport Relays come descritto di seguito.    


## <a name="sip-signaling-fqdns"></a>Segnalazione SIP: FQDN

Per il traffico di segnalazione SIP, i requisiti di FQDN e firewall sono gli stessi dei casi non bypassati. 

Il routing diretto è offerto nei seguenti ambienti Microsoft 365 o Office 365:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD Altre informazioni sugli ambienti di [Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) e US Government come GCC, GCC High e DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambienti Microsoft 365, Office 365 e Office 365 GCC

I punti di connessione per il routing diretto sono i tre FQDN seguenti:

- **sip.pstnhub.microsoft.com,** nome di dominio completo globale, devono essere provati prima. Quando SBC invia una richiesta di risoluzione di questo nome, i server DNS di Microsoft Azure restituiscono un indirizzo IP che punta al data center primario di Azure assegnato a SBC. L'assegnazione si basa sulle metriche di prestazioni dei data center e sulla prossimità geografica del centro dati per SBC. L'indirizzo IP restituito corrisponde all'FQDN principale.

- **sip2.pstnhub.microsoft.com** - FQDN secondario: corrisponde geograficamente alla seconda area geografica di priorità.

- **sip3.pstnhub.microsoft.com-** FQDN terziario: corrisponde geograficamente alla terza area geografica con priorità.

È necessario inserire questi tre FQDN per:

- Offrire un'esperienza ottimale, ovvero meno caricata e più vicina al data center SBC assegnato mediante query sul primo FQDN.

- Fornire il failover quando viene stabilita una connessione da un database SBC a un data center in cui si verifica un problema temporaneo. Per altre informazioni, vedere il meccanismo di failover seguente.


I nomi di **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** **e** sip3.pstnhub.microsoft.com verranno risolti in uno degli indirizzi IP seguenti:
- 52.114.148.0
- 52.114.132.46
- 52.114.16.74
- 52.114.20.29
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

Devi aprire le porte di tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione. Se il firewall supporta i nomi DNS, l'FQDN **sip-all.pstnhub.microsoft.com** risolve in tutti questi indirizzi IP. 

### <a name="office-365-gcc-dod-environment"></a>Ambiente DoD GCC di Office 365

Il punto di connessione per il routing diretto è il seguente FQDN:

**sip.pstnhub.dod.teams.microsoft.us:** FQDN globale. Poiché l'ambiente DoD di Office 365 esiste solo nei data center degli Stati Uniti, non sono presenti FQDN secondari e terziari.

I nomi di sip.pstnhub.dod.teams.microsoft.us sono stati risolti in uno degli indirizzi IP seguenti:

- 52.127.64.33
- 52.127.68.34

Devi aprire le porte di tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione.  Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.dod.teams.microsoft.us risolve in tutti questi indirizzi IP. 

### <a name="office-365-gcc-high-environment"></a>Ambiente Office 365 GCC High

Il punto di connessione per il routing diretto è il seguente FQDN:

**sip.pstnhub.gov.teams.microsoft.us:** FQDN globale. Poiché l'ambiente GCC High esiste solo nei data center degli Stati Uniti, non sono presenti FQDN secondari e terziari.

I nomi di sip.pstnhub.gov.teams.microsoft.us sono stati risolti in uno degli indirizzi IP seguenti:

- 52.127.88.59
- 52.127.92.64

Devi aprire le porte di tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione.  Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.gov.teams.microsoft.us risolve in tutti questi indirizzi IP. 

## <a name="sip-signaling-ports"></a>Segnalazione SIP: Porte

I requisiti di porta sono gli stessi per tutti gli ambienti di Office 365 in cui è offerto il routing diretto:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

È necessario usare le porte seguenti:

| Traffico | Da | A | Porta di origine | Porta di destinazione|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP Proxy | SBC | 1024 - 65535 | Definito nell'SBC |
| SIP/TLS | SBC | SIP Proxy | Definito nell'SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Traffico multimediale: intervalli ip e di porta

Il traffico multimediale passa tra il client SBC e il client Teams se la connettività diretta è disponibile o tramite i Relay di trasporto di Teams se il client non può raggiungere sBC usando l'indirizzo IP pubblico.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Requisiti per il traffico multimediale diretto (tra il client Teams e SBC) 

Il client deve avere accesso alle porte specificate (vedere la tabella) nell'indirizzo IP pubblico del servizio SBC. 

Nota: se il client si trova in una rete interna, il flusso degli elementi multimediali viene indirizzato all'indirizzo IP pubblico del servizio SBC. Puoi configurare il blocco dei capelli nel tuo dispositivo NAT in modo che il traffico non lasci mai l'apparecchiatura di rete aziendale.

| Traffico | Da | A | Porta di origine | Porta di destinazione|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Client | SBC | 50 000 – 50 019  | Definito nell'SBC |
| UDP/SRTP | SBC | Client | Definito nell'SBC | 50 000 – 50 019  |


> [!NOTE]
> Se si dispone di un dispositivo di rete che traduce le porte di origine del client, assicurarsi che le porte tradotte siano aperte tra l'apparecchiatura di rete e SBC. 

### <a name="requirements-for-using-transport-relays"></a>Requisiti per l'uso degli inoltri di trasporto

Gli Inoltro di trasporto sono nello stesso intervallo dei processori multimediali (per i casi non bypass): 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambienti Microsoft 365, Office 365 e Office 365 GCC

- 52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)

## <a name="office-365-gcc-dod-environment"></a>Ambiente DoD GCC di Office 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Ambiente Office 365 GCC High

- 52.127.88.0/21


L'intervallo di porta dei relay di trasporto di Teams (applicabili a tutti gli ambienti) è illustrato nella tabella seguente:


| Traffico | Da | A | Porta di origine | Porta di destinazione|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Inoltro di trasporto | SBC | 50 000 -59 999    | Definito nell'SBC |
| UDP/SRTP | SBC | Inoltro di trasporto | Definito nell'SBC | 50 000 – 59 999, 3478, 3479     |


> [!NOTE]
> Microsoft consiglia almeno due porte per ogni chiamata simultanea sull'SBC. Poiché Microsoft ha due versioni di Inoltro di trasporto, sono necessarie le operazioni seguenti:
> 
> - v4, che può funzionare solo con l'intervallo di porte da 50 000 a 59 999
> 
> - v6, che funziona con le porte 3478, 3479

Al momento, il bypass multimediale supporta solo la versione v4 dei transport relay. In futuro verrà introdotto il supporto della v6. 

È necessario aprire le porte 3478 e 3479 per la transizione. Quando Microsoft introduce il supporto per i Transport Relay v6 con Media Bypass, non sarà necessario riconfigurare le apparecchiature di rete o i dispositivi di rete. 

### <a name="requirements-for-using-media-processors"></a>Requisiti per l'uso dei processori multimediali

I processori multimediali sono sempre nel percorso multimediale per le applicazioni vocali e per i client Web (ad esempio, i client Teams in Edge o Google Chrome). I requisiti sono gli stessi della configurazione senza bypass.


L'intervallo IP per il traffico multimediale è 

### <a name="office-365-and-office-365-gcc-environments"></a>Ambienti GCC di Office 365 e Office 365

- 52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)

## <a name="office-365-gcc-dod-environment"></a>Ambiente DoD GCC di Office 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Ambiente Office 365 GCC High

- 52.127.88.0/21

L'intervallo di porta dei processori multimediali (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:

| Traffico | Da | A | Porta di origine | Porta di destinazione|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Processore multimediale | SBC | 3478, 3479 e 49 152 – 53 247    | Definito nell'SBC |
| UDP/SRTP | SBC | Processore multimediale | Definito nell'SBC | 3478, 3479 e 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>Configurare trunk separati per il bypass multimediale e il bypass non multimediale  

Se si esegue la migrazione al bypass multimediale da un bypass non multimediale e si vuole confermare la funzionalità prima di eseguire la migrazione di tutto l'utilizzo al bypass multimediale, è possibile creare un trunk separato e criteri di routing vocale separati da instradare al trunk di bypass multimediale e assegnarlo a utenti specifici. 

Passaggi di configurazione di alto livello:

- Identificare gli utenti per testare il bypass multimediale.

- Creare due trunk separati con fqdn diversi: uno abilitato per il bypass multimediale; l'altra no. 

  Entrambi i trunk puntano allo stesso SBC. Le porte per il traffico di segnalazione SIP TLS devono essere diverse. Le porte dei supporti multimediali devono essere uguali.

- Creare un nuovo criterio di routing vocale online e assegnare il trunk di bypass multimediale alle route corrispondenti associate all'utilizzo di PSTN per questo criterio.

- Assegnare il nuovo criterio Routing vocale online agli utenti identificati per testare il bypass multimediale.

L'esempio seguente illustra questa logica.

| Set di utenti | Numero di utenti | FQDN trunk assegnati in OVRP | Bypass multimediale abilitato |
| :------------ |:----------------- |:--------------|:--------------|
Utenti con trunk di bypass non multimediale | 980 | sbc1.contoso.com:5060 | true
Utenti con trunk del bypass multimediale | 20 | sbc2.contoso.com:5061 | false | 

Entrambi i trunk possono puntare allo stesso SBC con lo stesso indirizzo IP pubblico. Le porte di segnalazione TLS nell'SBC devono essere diverse, come illustrato nel diagramma seguente. Tenere presente che è necessario verificare che il certificato supporti entrambi i trunk. In SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o un certificato con caratteri jolly.

> [!div class="mx-imgBorder"]
> ![Mostra che entrambi i trunk possono puntare allo stesso SBC con lo stesso IP pubblico](media/direct-routing-media-bypass-7.png)

Per informazioni su come configurare due trunk nello stesso SBC, vedere la documentazione fornita dal fornitore di SBC:

 - [Documentazione sulla distribuzione di AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentazione della distribuzione Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentazione sulla distribuzione di Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentazione sulla distribuzione di TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Endpoint client supportati con bypass multimediale

Il bypass multimediale è supportato con tutti i client autonomi di Teams Desktop, i client Android e iOS e i dispositivi telefonici di Teams. 

Per tutti gli altri endpoint che non supportano il bypass multimediale, la chiamata verrà convertita in non bypass anche se è stata avviata come chiamata di bypass. Questa operazione viene eseguita automaticamente e non richiede alcuna azione da parte dell'amministratore. Sono inclusi i telefoni 3PIP di Skype for Business e i client Web di Teams che supportano le chiamate di routing diretto (client basati su WebRTC in esecuzione su Microsoft Edge, Google Chrome, Mozilla Firefox). 
 
## <a name="see-also"></a>Vedere anche

[Configurare il bypass multimediale con Instradamento diretto](direct-routing-configure-media-bypass.md)


