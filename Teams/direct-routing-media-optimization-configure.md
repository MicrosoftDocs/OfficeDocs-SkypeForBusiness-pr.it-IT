---
title: Ottimizzazione del supporto locale per il routing diretto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Configurare l'ottimizzazione del supporto locale per il routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576988"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>Configurare l'ottimizzazione del supporto locale per il routing diretto

La configurazione dell'ottimizzazione del supporto locale si basa sulle impostazioni di rete comuni ad altre caratteristiche vocali del cloud, come il routing Location-Based e le chiamate di emergenza dinamiche. Per altre informazioni sulle aree geografiche di rete, i siti di rete, le subnet di rete e gli indirizzi IP attendibili, vedere Impostazioni di rete [per le funzionalità vocali nel cloud.](cloud-voice-network-settings.md)

Prima di configurare l'ottimizzazione del supporto locale, vedere [Ottimizzazione supporto locale per il routing diretto.](direct-routing-media-optimization.md)  

Per configurare l'ottimizzazione del supporto locale, sono necessari i passaggi seguenti. È possibile usare l'interfaccia di amministrazione di Teams o PowerShell. Per informazioni dettagliate, vedere [Gestire la topologia della rete.](manage-your-network-topology.md)

1. Configurare l'utente e i siti SBC come descritto in questo articolo.
2. Configurare gli SBC per l'ottimizzazione degli elementi multimediali locali (in base alle specifiche del fornitore di SBC).

Il diagramma seguente illustra la configurazione della rete usata negli esempi di questo articolo.

![Diagramma che illustra la configurazione della rete per esempi](media/direct-routing-media-op-9.png "Configurazione della rete per esempi")


## <a name="configure-the-user-and-the-sbc-sites"></a>Configurare l'utente e i siti SBC

Per configurare l'utente e i siti SBC, è necessario:

1. [Gestire indirizzi IP attendibili esterni.](#manage-external-trusted-ip-addresses)  

2. [Definire la topologia della rete](#define-the-network-topology) configurando le aree di rete, i siti di rete e le subnet di rete.

3. [Definire la topologia di rete virtuale](#define-the-virtual-network-topology) assegnando Ibc ai siti con le modalità pertinenti e i valori SBC del proxy.


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Configurare SBC per l'ottimizzazione degli elementi multimediali locali in base alle specifiche del fornitore di SBC

Questo articolo descrive la configurazione per i componenti Microsoft. Per informazioni sulla configurazione di SBC, vedere la documentazione del fornitore di SBC.

L'ottimizzazione degli elementi multimediali locali è supportata dai fornitori di SBC seguenti:

| Fornitore | Prodotto |    Versione software |
|:------------|:-------|:-------|
| [Audiocodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20A.256 | 
|            |  Mediant 800 SBC |   7.20A.256 | 
|            |  Mediant 2600 SBC |  7.20A.256 | 
|            |  Mediant 4000 SBC |  7.20A.256 | 
|            |  Mediant 1000B SBC | 7.20A.256 | 
|            |  Mediant 9000 SBC |  7.20A.256 | 
|            |  Mediant Virtual Edition SBC |   7.20A.256 | 
|            |  Mediant Cloud Edition SBC | 7.20A.256 |
| [Barra multifunzione SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [Bordo SBC della barra multifunzione](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>Gestire indirizzi IP attendibili esterni

Gli IP attendibili esterni sono gli IP esterni Internet della rete aziendale. Questi indirizzi IP sono gli indirizzi IP usati dai client di Microsoft Teams quando si connettono a Microsoft 365. È necessario aggiungere questi IP esterni per ogni sito in cui gli utenti usano l'ottimizzazione degli elementi multimediali locali.

Per aggiungere gli indirizzi IP pubblici per ogni sito, usare il cmdlet New-CsTenantTrustedIPAddress public. È possibile definire un numero illimitato di indirizzi IP attendibili per un tenant. Se gli IP esterni visti da Microsoft 365 sono indirizzi IPv4 e IPv6, è necessario aggiungere entrambi i tipi di indirizzi IP. Per IPv4, usare la maschera 32. Per IPv6, usare la maschera 128. È possibile aggiungere sia singoli indirizzi IP esterni che subnet IP esterne specificando MaskBit diversi nel cmdlet.

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


Esempio di aggiunta di indirizzi IP attendibili.

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>Definire la topologia della rete

Questa sezione descrive come definire le aree di rete, i siti di rete e le subnet di rete per la topologia della rete.

Tutti i parametri fa distinzione tra maiuscole e minuscole, quindi è necessario assicurarsi di usare lo stesso tipo di maiuscole/minuscole usato durante l'installazione.  Ad esempio, i valori GatewaySiteID "Vietnam" e "Vietnam" verranno trattati come siti diversi.

### <a name="define-network-regions"></a>Definire le aree di rete

Per definire le aree geografiche di rete, usare New-CsTenantNetworkRegion cmdlet. Il parametro RegionID è un nome logico che rappresenta la geografia dell'area geografica e non ha dipendenze o restrizioni. Il parametro CentralSite <site ID> è facoltativo.

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

L'esempio seguente crea un'area di rete denominata APAC:

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>Definire i siti di rete

Per definire i siti di rete, usare New-CsTenantNetworkSite cmdlet. Ogni sito di rete deve essere associato a un'area geografica di rete.

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

L'esempio seguente crea tre nuovi siti di rete, Vietnam, Indonesia e Singapore, nell'area APAC:

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Definire le subnet di rete

Per definire le subnet di rete e associarle ai siti di rete, usare il cmdlet New-CsTenantNetworkSubnet rete. Ogni subnet di rete può essere associata a un solo sito. 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

L'esempio seguente definisce tre subnet di rete e le associa ai tre siti di rete: Vietnam, Indonesia e Singapore:

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>Definire la topologia della rete virtuale 

Prima di tutto, l'amministratore del tenant crea una nuova configurazione SBC per ogni SBC pertinente usando il cmdlet New-CsOnlinePSTNGateway tenant.
L'amministratore del tenant definisce la topologia di rete virtuale specificando i siti di rete per gli oggetti gateway PSTN usando il cmdlet Set-CsOnlinePSTNGateway:

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Tenere presente quanto segue: 
   - Se il cliente ha un singolo valore SBC, il parametro -ProxySBC deve essere obbligatorio $null o un valore FQDN SBC (central SBC con trunk centralizzati).
   - Il parametro -MediaBypass deve essere impostato su $true per supportare l'ottimizzazione di elementi multimediali locali.
   - Se per SBC non è impostato il parametro -BypassMode, le intestazioni X-MS non vengono inviate. 
   - Tutti i parametri fa distinzione tra maiuscole e minuscole, quindi è necessario assicurarsi di usare lo stesso tipo di maiuscole/minuscole usato durante l'installazione.  Ad esempio, i valori GatewaySiteID "Vietnam" e "Vietnam" verranno trattati come siti diversi.

L'esempio seguente aggiunge tre SBC ai siti di rete Vietnam, Indonesia e Singapore nell'area APAC con la modalità Bypass sempre:

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

Nota: per garantire operazioni ininterrotte durante la configurazione contemporaneamente dell'ottimizzazione degli elementi multimediali locali e del Location-Based Routing (LBR), è necessario abilitare le SBC a valle per LBR impostando il parametro GatewaySiteLbrEnabled su $true per ogni SBC a valle. Questa impostazione non è obbligatoria per il proxy SBC.

In base alle informazioni precedenti, l'instradamento diretto includerà tre intestazioni SIP proprietarie per gli inviti SIP e i nuovi inviti, come illustrato nella tabella seguente.

X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:

| Nome intestazione | Valori | Commenti | 
|:------------|:-------|:-------|
| X-MS-UserLocation | interno/esterno | Indica se l'utente è interno o esterno |
| Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0 | SBC FQDN | L'FQDN mirato per la chiamata anche se SBC non è connesso direttamente al routing diretto |
| X-MS-MediaPath | Esempio: proxysbc.contoso.com, VNsbc.contoso.com | Ordine degli SBC da usare per il percorso multimediale tra l'utente e il sito SBC di destinazione. Il valore SBC finale è sempre l'ultimo |
| X-MS-UserSite | usersiteID | Stringa definita dall'amministratore del tenant |

## <a name="call-flows"></a>Flussi delle chiamate 

Di seguito sono illustrati i flussi delle chiamate per due modalità:

- [Ignora sempre](#always-bypass-mode)
- [Solo per gli utenti locali](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Modalità bypass sempre

La modalità bypass è l'opzione più semplice da configurare. L'amministratore tenant può configurare un singolo sito per tutti gli utenti e gli SBC se tutti gli SBC sono raggiungibili da qualsiasi sito.

Gli esempi mostrano la modalità bypass sempre per gli scenari seguenti:

- [Chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Chiamate in ingresso e l'utente si trova nella stessa posizione del controller SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Chiamate in uscita e l'utente è esterno](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Chiamate in ingresso e l'utente è esterno](#inbound-calls-and-the-user-is-external-with-always-bypass)

La tabella seguente mostra l'FQDN e gli indirizzi IP usati negli esempi:

| FQDN | Indirizzo IP esterno SBC | Indirizzo IP interno SBC | Subnet interna | Posizione | NAT esterno (IP attendibile) |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | Nessuno | 192.168.1.5 | 192.168.1.0/24 | Vietnam | 172.16.240.110 |
| IDsbc.contoso.com | Nessuno | 192.168.2.5 | 192.168.2.0/24 | Indonesia | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | Singapore | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Le chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC con Always Bypass

| Modalità |    Utente |  Posizione |  Direzione della chiamata |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    Interno |  Lo stesso sito di SBC |  In uscita |

La tabella seguente mostra la configurazione e l'azione dell'utente finale:

| Posizione fisica dell'utente| Un utente effettua o riceve una chiamata a/da un numero | Numero di telefono utente  | Criteri per l'instradamento vocale online | Modalità configurata per SBC |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 | +84 4 5555 5555   | Priorità 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Priorità 2: .* - proxysbc.contoso.com   | VNsbc.contoso.com - Ignora sempre <br> proxysbc.contoso.com - Ignora sempre


Il diagramma seguente mostra il profilo SIP di una chiamata in uscita con la modalità bypass sempre e l'utente nella stessa posizione del controller SBC.

![Diagramma che illustra le chiamate in uscita](media/direct-routing-media-op-10.png "Chiamate in uscita")

La tabella seguente mostra le intestazioni X-MS inviate dal routing diretto:

| Parametro | Spiegazione |
|:------------|:-------|
| Invita +8443926300@VNsbc.contoso.com | L'FQDN di destinazione del servizio SBC definito nel criterio di routing vocale online viene inviato nell'URI richiesta | 
| X-MS-UserLocation: interno | Il campo indica che l'utente si trova all'interno della rete aziendale |
| X-MS-MediaPath: VNsbc.contoso.com |   Specifica quale SBC deve attraversare il client fino al valore SBC di destinazione. In questo caso, se l'opzione Bypass è sempre ignorata e il client è interno, il nome di destinazione inviato è l'unico nome nell'intestazione. | 
|X-MS-UserSite: Vietnam |   Il campo indicato all'interno del sito in cui si trova l'utente. |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Chiamate in entrata e l'utente si trova nella stessa posizione del controller SBC con Bypass sempre

| Modalità |    Utente |  Posizione |  Direzione della chiamata |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    Interno | Lo stesso sito di SBC | In ingresso |


Durante una chiamata in ingresso, la posizione dell'utente è sconosciuta e il servizio SBC deve indovinare dove si trova l'utente. Se l'ipotesi non è corretta, sarà richiesto un nuovo invito. In questo caso si presuppone che l'utente sia interno, che il flusso dei contenuti multimediali sia diretto e che non siano necessarie altre azioni (invitarlo di nuovo).
Il servizio SBC connesso al servizio di instradamento diretto segnala la posizione SBC di origine fornendo i campi Record-Route contatti. In base a questi campi, il percorso del supporto viene calcolato tramite routing diretto.

Nota: dato che un utente può avere più endpoint, il supporto di 183 non è possibile. In questo caso, l'instradamento diretto userà sempre lo squillo 180. 

Il diagramma seguente illustra la proprietà SIP per le chiamate in ingresso con la modalità AlwaysBypass e l'utente si trova nella stessa posizione del controller SBC.

![Diagramma che mostra la sip](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Chiamate in uscita e l'utente è esterno con Bypass sempre

| Modalità |    Utente |  Sito |  Direzione della chiamata
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Esterna |  N/D | In uscita |


Il diagramma seguente mostra la classe SIP per una chiamata in uscita con la modalità AlwaysBypass e l'utente è esterno:

![Diagramma che mostra la sip](media/direct-routing-media-op-12.png)

La tabella seguente mostra le intestazioni X-MS inviate dal servizio di routing diretto:

| Parametro |   Spiegazione |
|:------------|:-------|
|Invita +8443926300@VNsbc.contoso.com | L'FQDN di destinazione del servizio SBC definito nel criterio di routing vocale online viene inviato nell'URI richiesta.|
| X-MS-UserLocation: esterna | Il campo indica che l'utente si trova all'esterno della rete aziendale. |
| X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com    | Specifica quale SBC deve attraversare il client fino al valore SBC di destinazione. In questo caso, poiché è sempre stato ignorato, il client è esterno. |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Chiamate in ingresso e l'utente è esterno con Bypass sempre

| Modalità | Utente | Sito |  Direzione della chiamata |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Esterna |  N/D |   In ingresso |

Per una chiamata in ingresso, l'SBC connesso al routing diretto deve inviare un nuovo invito (per impostazione predefinita, i candidati per i supporti locali sono sempre offerti) se la posizione dell'utente è esterna.  X-MediaPath viene calcolato in base Record-Route'utente SBC specificato.

Il diagramma seguente illustra il profilo SIP per una chiamata in ingresso con la modalità AlwaysBypass e l'utente è esterno.

![Diagramma che mostra la sip](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>Solo per la modalità utenti locali

I candidati per gli elementi multimediali locali del sito SBC di destinazione verranno offerti solo se un utente si trova nella stessa posizione del database SBC. In tutti gli altri casi, il flusso degli elementi multimediali verrà attraverso un INDIRIZZO IP interno o esterno del proxy SBC.

Sono descritti gli scenari seguenti:

- [Chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Chiamate in ingresso e l'utente si trova nella stessa posizione del controller SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [L'utente non si trova nella stessa posizione del database SBC ma si trova nella rete aziendale](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Chiamate in ingresso e l'utente è interno, ma non si trova nella stessa posizione del controller SBC](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

La tabella seguente mostra la configurazione e l'azione degli utenti finali:

| Posizione fisica dell'utente |  Un utente effettua o riceve una chiamata a/da un numero |  Numero di telefono utente | Criteri per l'instradamento vocale online |   Modalità configurata per SBC |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 |  +84 4 5555 5555 | Priorità 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Priorità 2: .* - proxysbc.contoso.com | VNsbc.contoso.com - OnlyForLocalUsers Proxysbc.contoso.com – Bypass sempre |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Chiamate in uscita e l'utente si trova nella stessa posizione del servizio SBC con Solo per gli utenti locali

| Modalità | Utente | Sito | Direzione della chiamata |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Interno |Come SBC   | In uscita |

Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione del database SBC. Si tratta dello stesso flusso mostrato nelle chiamate in uscita quando l'utente si trova nella [stessa posizione del servizio SBC.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![Diagramma che mostra la sip](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Chiamate in ingresso e l'utente si trova nella stessa posizione del servizio SBC con Solo per gli utenti locali

| Modalità | Utente | Sito | Direzione della chiamata |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Interno | Come SBC | In ingresso |

Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione del database SBC. Si tratta dello stesso flusso illustrato nelle chiamate in ingresso quando l'utente si trova nella stessa [posizione del servizio SBC.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![Diagramma che mostra la sip](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>L'utente non si trova nella stessa posizione del database SBC, ma si trova nella rete aziendale con l'account solo per gli utenti locali

| Modalità | Utente | Sito |Direzione della chiamata |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | Interno |   Diverso da SBC | In uscita |

Il routing diretto calcola X-MediaPath in base alla posizione segnalata dell'utente e alla modalità configurata nel database SBC.


Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione del database SBC.

![Diagramma che mostra la sip](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>Chiamata in ingresso e l'utente è interno, ma non si trova nella stessa posizione del database SBC con solo per gli utenti locali

| Modalità |    Utente |  Sito |  Direzione della chiamata |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | Interno |    Diverso da SBC |    In ingresso |

Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione del database SBC.

![Diagramma che mostra la sip](media/direct-routing-media-op-17.png)









