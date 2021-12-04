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
description: Informazioni su come pianificare il bypass multimediale con Sistema telefonico routing diretto, che consente di abbreviare il percorso del traffico multimediale e migliorare le prestazioni.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1fb9eff518232f53868752a297775369af13713a
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306331"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Pianificare il bypass multimediale con Instradamento diretto

## <a name="about-media-bypass-with-direct-routing"></a>Informazioni sul bypass multimediale con Routing diretto

Il bypass multimediale consente di abbreviare il percorso del traffico multimediale e ridurre il numero di hop in transito per migliorare le prestazioni. Con il bypass multimediale, i supporti multimediali vengono mantenuti tra session border controller (SBC) e il client invece di inviarli tramite Telefono Microsoft System. Per configurare il bypass multimediale, SBC e il client devono essere nella stessa posizione o rete.

È possibile controllare il bypass multimediale per ogni SBC usando il **comando Set-CSOnlinePSTNGateway** con il **parametro -MediaBypass** impostato su true o false. Se si abilita il bypass multimediale, questo non significa che tutto il traffico multimediale rimarrà all'interno della rete aziendale. Questo articolo descrive il flusso delle chiamate in diversi scenari.

I diagrammi seguenti illustrano la differenza nel flusso delle chiamate con e senza bypass multimediale.

Senza bypass multimediale, quando un client effettua o riceve una chiamata, sia la segnalazione che il flusso multimediale tra SBC, il sistema Telefono Microsoft e il client Teams, come illustrato nel diagramma seguente:

> [!div class="mx-imgBorder"]
> ![Mostra la segnalazione e il flusso multimediale senza bypass multimediale.](media/direct-routing-media-bypass-1.png)


Si supponga però che un utente si trova nello stesso edificio o nella stessa rete di SBC. Si supponga ad esempio che un utente che si trova in un edificio di Francoforte esempli una chiamata a un utente PSTN: 

- **Senza bypass multimediale,** i supporti multimediali fluiranno tramite Amsterdam o Dublino (dove sono distribuiti i data center Microsoft) e di nuovo alla SBC di Francoforte. 

  Il data center in Europa è selezionato perché il database SBC è in Europa e Microsoft usa il data center più vicino a SBC. Anche se questo approccio non influisce sulla qualità delle chiamate a causa dell'ottimizzazione del flusso di traffico all'interno delle reti Microsoft nella maggior parte delle aree geografiche, il traffico ha un ciclo non necessario.     

- **Con il bypass** multimediale, i supporti multimediali vengono mantenuti direttamente tra Teams utente e SBC, come illustrato nel diagramma seguente:

  > [!div class="mx-imgBorder"]
  > ![Mostra la segnalazione e il flusso multimediale con bypass multimediale.](media/direct-routing-media-bypass-2.png)

Il bypass multimediale usa protocolli chiamati Interactive Connectivity Establishment (ICE) sul client Teams e ICE lite sul SBC. Questi protocolli consentono al routing diretto di usare il percorso multimediale più diretto per una qualità ottimale. ICE e ICE Lite sono standard WebRTC. Per informazioni dettagliate su questi protocolli, vedere RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Pianificazione del flusso delle chiamate e del firewall

La pianificazione del flusso delle chiamate e del firewall dipende dal fatto che l'utente abbia accesso diretto all'indirizzo IP pubblico dell'SBC e se l'utente si trova all'interno o all'esterno della rete.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Flusso delle chiamate se l'utente ha accesso diretto all'indirizzo IP pubblico dell'SBC

Se l'utente ha accesso diretto all'indirizzo IP pubblico del SBC, il flusso di chiamata è il seguente:

- Per il bypass multimediale, Teams client deve avere accesso all'indirizzo IP pubblico della SBC anche da una rete interna. Se non si desidera supporti diretti, i supporti multimediali possono fluire tramite i relè di trasporto.

- Questa è la soluzione consigliata quando un utente si trova nello stesso edificio e/o rete di SBC, rimuovendo i componenti Microsoft Cloud dal percorso multimediale.

- La segnalazione fluisce sempre tramite il cloud Microsoft.

Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è interno e il client può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto): 

- Le frecce e i valori numerici dei percorsi sono conformi ai flussi Microsoft Teams [chiamate.](./microsoft-teams-online-call-flows.md)

- La segnalazione SIP accetta sempre i percorsi 4 e 4' (a seconda della direzione del traffico). Il supporto rimane locale e prende il percorso 5b.

> [!div class="mx-imgBorder"]
> ![Mostra il flusso delle chiamate con Bypass multimediale abilitato, il client è interno.](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico dell'SBC

Di seguito viene descritto il flusso delle chiamate se l'utente non ha accesso all'indirizzo IP pubblico del servizio SBC. 

Si supponga ad esempio che l'utente sia esterno e che l'amministratore del tenant abbia deciso di non aprire l'indirizzo IP pubblico della SBC a tutti gli utenti di Internet, ma solo a Microsoft Cloud. I componenti interni del traffico possono fluire tramite Teams di trasporto. Tenere in considerazione gli aspetti seguenti:

- Teams vengono usati i relè di trasporto.

- Per il bypass multimediale, Microsoft usa una versione di Transport Relays che richiede l'apertura delle porte da 50 000 a 59 999 tra gli inoltri di trasporto di Teams e SBC (in futuro si prevede di passare alla versione che richiede 3478-3481 porte).


Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e il client non riesce a raggiungere l'indirizzo IP pubblico del Session Border Controller (i supporti vengono inoltrati da Teams Transport Relay).

- Le frecce e i valori numerici dei percorsi sono conformi ai flussi Microsoft Teams [chiamate.](./microsoft-teams-online-call-flows.md)

- I file multimediali vengono inoltrati tramite i percorsi 3, 3', 4 e 4'

> [!div class="mx-imgBorder"]
> ![Mostra flusso di chiamata se l'utente non ha accesso all'IP pubblico del SBC.](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Flusso delle chiamate se un utente si trova all'esterno della rete e ha accesso all'IP pubblico dell'SBC

> [!NOTE]
> Questa configurazione non è consigliata perché non sfrutta i Teams di trasporto. È invece consigliabile considerare lo scenario precedente in cui l'utente non ha accesso all'indirizzo IP pubblico dell'SBC. 

Il diagramma seguente mostra il flusso delle chiamate quando è abilitato il bypass multimediale, il client è esterno e il client può raggiungere l'indirizzo IP pubblico del SBC (supporto diretto).

- Le frecce e i valori numerici dei percorsi sono conformi all'articolo Microsoft Teams [flussi di](./microsoft-teams-online-call-flows.md) chiamate.

- La segnalazione SIP accetta sempre i percorsi 3 e 3' (a seconda della direzione del traffico). Flussi multimediali usando il percorso 2.

> [!div class="mx-imgBorder"]
> ![Mostra flusso di chiamata se l'utente non ha accesso all'IP pubblico del SBC.](media/direct-routing-media-bypass-5.png)



## <a name="use-of-media-processors-and-transport-relays"></a>Uso di processori multimediali e relay di trasporto

In Microsoft Cloud sono disponibili due componenti che possono essere nel percorso del traffico multimediale: Processori multimediali e Relay di trasporto. 

- Il Processore multimediale è un componente pubblico che gestisce i supporti multimediali in casi non di bypass e gestisce gli elementi multimediali per le applicazioni vocali.

   I processori multimediali sono sempre nel percorso per le chiamate non bypassate da parte dell'utente finale, ma mai nel percorso per le chiamate ignorate. I processori multimediali sono sempre nel percorso per tutte le applicazioni vocali, ad esempio il parcheggio di chiamata, l'organizzazione Operatore automatico e le code di chiamata.

- L'inoltro di trasporto viene usato per connettersi al servizio di trasporto più vicino per inviare traffico in tempo reale.

   Gli inoltri di trasporto potrebbero essere o meno nel percorso per le chiamate ignorate, provenienti da o destinate agli utenti finali, a seconda della posizione dell'utente e della configurazione della rete.

Il diagramma seguente mostra due flussi di chiamata: uno con il bypass multimediale abilitato e il secondo con bypass multimediale disabilitato.

> [!NOTE]
> Il diagramma illustra solo il traffico proveniente da o destinato agli utenti finali.  

- Il Controller multimediale è un microservizio in Azure che assegna processori multimediali e crea offerte SDP (Session Description Protocol).

- Il proxy SIP è un componente che converte la segnalazione REST HTTP usata Teams in SIP.    

> [!div class="mx-imgBorder"]
> ![Mostra i flussi delle chiamate con Bypass multimediale abilitato e disabilitato.](media/direct-routing-media-bypass-6.png)


La tabella seguente riepiloga la differenza tra processori multimediali e relay di trasporto.

|  &nbsp; | Processori multimediali | Relè di trasporto|
| :--------------|:---------------|:------------|
|Percorso multimediale per le chiamate non bypassate per gli utenti finali | Sempre | Se il client non riesce a raggiungere direttamente il Processore multimediale |
|Percorso multimediale per le chiamate ignorate per gli utenti finali | Mai | Se il client non riesce a raggiungere SBC nell'indirizzo IP pubblico |
|Percorso multimediale per le applicazioni vocali | Sempre | Mai |
|Può eseguire la trascodtura (B2BUA)\* | Sì | No, solo l'inoltro audio tra endpoint |
|Numero di istanze in tutto il mondo e località | 10 in totale: 2 negli Stati Uniti orientali e occidentali; 2 ad Amsterdam e Dublino; 2 a Hong Kong e Singapore; 2 in Giappone ; 2 in Australia Est e Sudest | Multiplo|

Gli intervalli IP sono:
- 52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)
- 52.120.0.0/14 (indirizzi IP da 52.120.0.1 a 52.123.255.254)

\* Spiegazione trascodico: 

- Processore multimediale è B2BUA, che significa che può modificare un codec,ad esempio SILK da client Teams Teams MP e G.711 tra MP e SBC.

- Gli inoltri di trasporto non sono B2BUA, il che significa che il codec non viene mai modificato tra il client e il SBC, anche se il traffico scorre tramite relay.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>Uso dei processori Teams multimediali se il trunk è configurato per il bypass multimediale

Teams processori multimediali vengono sempre inseriti nel percorso multimediale negli scenari seguenti:

- La chiamata viene riassegnata dall'1:1 a una chiamata di gruppo
- La chiamata è in corso a un utente Teams federato
- La chiamata viene inoltrata o trasferita a un Skype for Business utente

Verificare che SBC abbia accesso agli intervalli Media Processors e Transport Relays come descritto di seguito.    


## <a name="sip-signaling-fqdns"></a>Segnalazione SIP: FQDN

Per la segnalazione SIP, i requisiti di FQDN e firewall sono gli stessi dei casi non bypassati. 

Il routing diretto è disponibile negli ambienti Microsoft 365 o Office 365 seguenti:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC Alta
- Office 365 DoD Altre informazioni sugli ambienti [Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) enti pubblici degli Stati Uniti come GCC, GCC High e DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 e Office 365 GCC ambienti

I punti di connessione per il routing diretto sono i tre FQDN seguenti:

- **sip.pstnhub.microsoft.com,** fqdn globale, deve essere provato prima di tutto. Quando il servizio SBC invia una richiesta di risoluzione del nome, i server DNS Microsoft Azure restituiscono un indirizzo IP che punta al data center di Azure primario assegnato a SBC. L'assegnazione si basa sulle metriche delle prestazioni dei data center e sulla vicinanza geografica al SBC. L'indirizzo IP restituito corrisponde all'FQDN primario.

- **sip2.pstnhub.microsoft.com** , FQDN secondario, mappato geograficamente alla seconda area di priorità.

- **sip3.pstnhub.microsoft.com** , FQDN terziario, viene mappato geograficamente alla terza area prioritaria.

È necessario inserire questi tre FQDN per:

- Offrire un'esperienza ottimale, meno caricata e più vicina al data center SBC assegnato tramite query sul primo FQDN.

- Fornire il failover quando viene stabilita una connessione da un SBC a un data center in cui si verifica un problema temporaneo. Per altre informazioni, vedere Meccanismo di failover più avanti.


I nomi FQDN **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** e sip3.pstnhub.microsoft.com verranno  risolti in indirizzi IP dalle subnet seguenti:
- 52.112.0.0/14
- 52.120.0.0/14

È necessario aprire le porte per tutti questi intervalli IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD

Il punto di connessione per il routing diretto è il seguente FQDN:

**sip.pstnhub.dod.teams.microsoft.us** : FQDN globale. Poiché l'Office 365 DoD esiste solo nei data center degli Stati Uniti, non sono disponibili FQDN secondari e terziari.

Il nome fqdn sip.pstnhub.dod.teams.microsoft.us verrà risolto in un indirizzo IP dalla subnet seguente:

- 52.127.64.0/21

È necessario aprire le porte per tutti questi intervalli IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.  Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.dod.teams.microsoft.us viene risolto in tutte queste subnet IP. 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC ambiente High

Il punto di connessione per il routing diretto è il seguente FQDN:

**sip.pstnhub.gov.teams.microsoft.us:** FQDN globale. Poiché l'GCC high è presente solo nei data center degli Stati Uniti, non sono disponibili fqdn secondari e terziari.

Il nome sip.pstnhub.gov.teams.microsoft.us fqdn verrà risolto in un indirizzo IP dalla subnet seguente:

- 52.127.88.0/21

È necessario aprire le porte per tutti questi intervalli IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.  Se il firewall supporta i nomi DNS, l'FQDN sip.pstnhub.gov.teams.microsoft.us viene risolto in tutte queste subnet IP. 

## <a name="sip-signaling-ports"></a>Segnalazione SIP: Porte

I requisiti di porta sono gli stessi per tutti gli Office 365 in cui è disponibile il routing diretto:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC Alta
- Office 365 DoD

È necessario usare le porte seguenti:

| Traffico | Da | A | Porta di origine | Porta di destinazione|
| :-------- | :-------- |:-----------|:--------|:---------|
| SIP/TLS| SIP Proxy | SBC | 1024 - 65535 | Definito nell'SBC |
| SIP/TLS | SBC | SIP Proxy | Definito nell'SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Traffico multimediale: intervalli ip e porte

Il traffico multimediale fluisce tra il client SBC e il client Teams se è disponibile la connettività diretta o tramite gli inoltri di trasporto Teams se il client non riesce a raggiungere SBC usando l'indirizzo IP pubblico.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Requisiti per il traffico multimediale diretto (tra Teams client e SBC) 

Il client deve avere accesso alle porte specificate (vedere la tabella) nell'indirizzo IP pubblico dell'SBC. 

> [!NOTE]
> Se il client si trova in una rete interna, il contenuto multimediale passa all'indirizzo IP pubblico del servizio SBC. È possibile configurare l'aggiunta di capelli nel dispositivo NAT in modo che il traffico non lasci mai l'apparecchiatura di rete aziendale.

| Traffico | Da | A | Porta di origine | Porta di destinazione|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Client | SBC | 3478-3481 e porte configurate dall'amministratore tenant per il client (l'impostazione predefinita è 50000-50020)| Definito nell'SBC |
| UDP/SRTP | SBC | Client | Definito nell'SBC | 3478-3481 e porte configurate dall'amministratore tenant per il client (l'impostazione predefinita è 50000-50020)  |


> [!NOTE]
> Se si dispone di un dispositivo di rete che traduce le porte di origine del client, assicurarsi che le porte tradotte siano aperte tra l'apparecchiatura di rete e la SBC. 

### <a name="requirements-for-using-transport-relays"></a>Requisiti per l'uso degli inoltri di trasporto

I relè di trasporto sono nello stesso intervallo dei processori multimediali (per i casi non di bypass): 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 e Office 365 GCC ambienti

- 52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC ambiente High

- 52.127.88.0/21


L'intervallo di porte dei Teams di trasporto (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:


| Traffico | Da | A | Porta di origine | Porta di destinazione|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Inoltro di trasporto | SBC | 50 000 -59 999    | Definito nell'SBC |
| UDP/SRTP | SBC | Inoltro di trasporto | Definito nell'SBC | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft consiglia almeno due porte per ogni chiamata simultanea su SBC. Poiché Microsoft ha due versioni di Inoltro di trasporto, sono necessarie le operazioni seguenti:
> 
> - v4, che può funzionare solo con l'intervallo di porte da 50 000 a 59 999
> 
> - v6, che funziona con le porte 3478-3481

Al momento, il bypass multimediale supporta solo la versione v4 di Transport Relays. Verrà introdotto il supporto della versione 6 in futuro. 

È necessario aprire le porte 3478-3481 per la transizione. Quando Microsoft introduce il supporto per i relay di trasporto v6 con Media Bypass, non sarà necessario riconfigurare le apparecchiature di rete o gli SBC. 

### <a name="requirements-for-using-media-processors"></a>Requisiti per l'uso di processori multimediali

I processori multimediali sono sempre nel percorso multimediale per le applicazioni vocali e per i client Web(ad esempio, i client Teams in Edge o Google Chrome). I requisiti sono gli stessi per la configurazione non bypass.


L'intervallo IP per il traffico multimediale è 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 e Office 365 GCC di lavoro

- 52.112.0.0 /14 (indirizzi IP da 52.112.0.1 a 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC ambiente High

- 52.127.88.0/21

L'intervallo di porte dei processori multimediali (applicabile a tutti gli ambienti) è illustrato nella tabella seguente:

| Traffico | Da | A | Porta di origine | Porta di destinazione|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Processore multimediale | SBC | 3478-3481 e 49 152 – 53 247    | Definito nell'SBC |
| UDP/SRTP | SBC | Processore multimediale | Definito nell'SBC | 3478-3481 e 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>Configurare trunk separati per bypass multimediale e bypass non multimediale  

Se si esegue la migrazione al bypass multimediale da un bypass non multimediale e si vuole confermare la funzionalità prima di eseguire la migrazione di tutti gli utilizzi al bypass multimediale, è possibile creare un trunk separato e un criterio di routing vocale online separato da instradare al trunk di bypass multimediale e assegnare a utenti specifici. 

Passaggi di configurazione di alto livello:

- Identificare gli utenti per testare il bypass multimediale.

- Creare due trunk separati con fqdn diversi: uno abilitato per il bypass multimediale; l'altro no. 

  Entrambi i trunk puntano allo stesso SBC. Le porte per la segnalazione SIP TLS devono essere diverse. Le porte per i supporti multimediali devono essere uguali.

- Creare un nuovo criterio routing vocale online e assegnare il trunk di bypass multimediale alle route corrispondenti associate all'utilizzo PSTN per questo criterio.

- Assegnare il nuovo criterio Routing vocale online agli utenti identificati per testare il bypass multimediale.

L'esempio seguente illustra questa logica.

| Set di utenti | Numero di utenti | FQDN trunk assegnato in OVRP | Bypass multimediale abilitato |
| :------------ |:----------------- |:--------------|:--------------|
| Utenti con trunk di bypass non multimediali | 980 | sbc1.contoso.com:5061 | false |
| Utenti con trunk bypass multimediale | 20 | sbc2.contoso.com:5060 | true | 

Entrambi i trunk possono puntare allo stesso SBC con lo stesso indirizzo IP pubblico. Le porte di segnalazione TLS nel SBC devono essere diverse, come illustrato nel diagramma seguente. Si noti che è necessario assicurarsi che il certificato supporti entrambi i trunk. Nella rete SAN è necessario avere due nomi (**sbc1.contoso.com** e **sbc2.contoso.com**) o avere un certificato con caratteri jolly.

> [!div class="mx-imgBorder"]
> ![Mostra che entrambi i trunk possono puntare allo stesso SBC con lo stesso ip pubblico.](media/direct-routing-media-bypass-7.png)

Per informazioni su come configurare due trunk nello stesso SBC, vedere la documentazione fornita dal fornitore SBC:

 - [Documentazione sulla distribuzione di AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentazione sulla distribuzione Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentazione sulla distribuzione di Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentazione sulla distribuzione di TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Endpoint client supportati con bypass multimediale

Il bypass multimediale è supportato con tutti i client desktop Teams, i client Android e iOS e i Teams Telefono dispositivi. 

Per tutti gli altri endpoint che non supportano il bypass multimediale, la chiamata verrà convertita in non bypass anche se è stata avviata come chiamata di bypass. Questa operazione viene eseguita automaticamente e non richiede alcuna azione da parte dell'amministratore. Sono inclusi Skype for Business telefoni 3PIP e client Web Teams che supportano le chiamate di routing diretto (client basati su WebRTC in esecuzione su Microsoft Edge, Google Chrome, Mozilla Firefox). 
 
## <a name="see-also"></a>Vedere anche

[Configurare il bypass multimediale con Instradamento diretto](direct-routing-configure-media-bypass.md)
